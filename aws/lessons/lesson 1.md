## Lesson 1: Monolith Deployment (Manually)

- ## Module 1: Provision Infrastructure in AWS

  - VPC (Virtual Private Cloud) is your own private network inside AWS where you deploy your cloud resources.
  - Your own isolated mini-data center inside AWS.
  - It is the foundation for deploying servers, databases, and other resources.
  - is the private network environment where you deploy and manage your AWS resources, such as EC2 instances, RDS databases, load balancers, Lambdas, etc.

    - ## You control:

      - IP addresses
      - Subnets
      - Firewalls (security groups)
      - Gateways
      - Routing

    - ## Purpose:

      - Deploying your EC2 server
      - Creating a secure environment for your database
      - Controlling access from Vercel → AWS
      - Connecting EC2 → RDS
      - Setting up load balancers, NAT, or gateways later

  - ## Steps: Creating VPC

    - go to aws console
    - search for VPC
    - create VPC
    - go to VPC Setting look for [VPC and more]
    - [VPC Setting]: Name tag auto-generation (change based on your preferrence)
    - [VPC Setting]: leave the default settings
    - [VPC Setting]: create VPC
    - Click view VPC
    - go back to AWS Console
    - search EC2
    - go to instance
    - launch instance
    - [instance settings]: Name and tags - create a instance name
    - [instance settings]: Application and OS Images (Amazon Machine Image) - select ubuntu
    - [instance settings]: select free tier or any based on your preference
    - [instance settings]: Architecture -leave it based on the OS image
    - [instance settings]: Create key pair
      - input key pair name
      - select RSA
      - select .pem
      - create key pair
      - save the file to the secure location becuase it is very needed in instances for credentials
    - [instance settings]: network setting - select edit
      - [network setting]: select the VPC that you created earlier
      - [network setting]: subnet - select the subnet-public1
      - [network setting]: Auto-assign public IP - select Enable
      - [network setting]: Firewall (security groups) - select create security group
      - [network setting]: Security group name - input Security group name
      - [network setting]: Description - use the Security group name as a prefix for the description
      - [Inbound Security Group Rules]: Type - SSH
      - [Inbound Security Group Rules]: Source type - Anywhere
      - [Inbound Security Group Rules]: click add security group rule
      - [Inbound Security Group Rules]: Type - HTTP
      - [Inbound Security Group Rules]: Source type - Anywhere
      - [Inbound Security Group Rules]: Type - HTTPS
      - [Inbound Security Group Rules]: Source type - Anywhere
      - [Configure storage]: use default config
      - [instance settings]: Launch instance

- ## Module 2: Prepare Ubuntu Instance

  - open the gitbash terminal
  - go back to instances
  - look for public IPV4 address
    Terminal: `Ubuntu`  
    Command:

    ```sh
        # use the .pem file that you download earlier
        ssh -i your-pem-file.pem ubuntu@your-aws-public-ip

        # change the permission
        sudo chmod 0600 marvin-ramos.pem

        sudo apt update
        sudo apt upgrade -y

        # go back to EC2 instances then go to instance state->reboot instance
        sudo apt install -y nginx
        sudo add-apt-repository ppa:ondrej/php
        sudo apt install php8.3-fpm

        # test the php
        php --version

        # test the nginx
        # go to the public ip
        # http://your-public-ip/

        # installing all laravel extension
        sudo apt install -y \ php8.3 \ php8.3-cli \ php8.3-fpm \ php8.3-common \ php8.3-mbstring \ php8.3-xml \ php8.3-curl \ php8.3-zip \ php8.3-mysql \ php8.3-pgsql \ php8.3-sqlite3 \ php8.3-intl \ php8.3-redis \ php8.3-gd \ php8.3-bcmath \ php8.3-fileinfo \ php8.3-opcache

        #install composer
        # you can go to there website to download latest version
        php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
        php -r "if (hash_file('sha384', 'composer-setup.php') === 'c8b085408188070d5f52bcfe4ecfbee5f727afa458b2573b8eaaf77b3419b0bf2768dc67c86944da1544f06fa544fd47') { echo 'Installer verified'.PHP_EOL; } else { echo 'Installer corrupt'.PHP_EOL; unlink('composer-setup.php'); exit(1); }"
        php composer-setup.php
        php -r "unlink('composer-setup.php');"

        # move the composer to global directory
        sudo mv ~/composer.phar /usr/local/bin/composer

        #check it
        composer --version

        #install node.js
        curl -fsSL https://deb.nodesource.com/setup_22.x | sudo -E bash -
        sudo apt-get install -y nodejs

        # check npm and node
        node --version
        npm --version

        # add deployment user
        sudo adduser marvin-ramos

        # change the user to deployment
        sudo su marvin-ramos

        # create a github deployment key
        ssh-keygen -f /home/marvin-ramos/.ssh/github_rsa -t rsa

        nano ~/.ssh/config

        # CONFIG FILE
        # copy this to the config file
        Host github.com
            IdentityFile ~/.ssh/github_rsa
            IdentitiesOnly yes

        # change permission
        chmod 700 ~/.ssh
        chmod 600 ~/.ssh/*
    ```

- ## Module 3: Deploy Web

  Terminal: `Ubuntu`  
   Command:

  ```sh
      # copy the .pub file into you github account
      cat ~/.ssh/github_rsa.pub

      # go to github.com
      # look for the repository of your desired project
      # go to setting of that repositoy
      # go to deploy keys
      # add deploy keys
      # clone your repository into your aws ubuntu
      git clone https://github.com/Crispkreme/freelance-portfolio-app.git

      # installation dependencies
      composer install
      npm install --legacy-peer-deps

      # copy the .env
       cp .env.example .env

       # go to the nginx
       cd /etc/nginx/

       # go back to ubuntu user for administration access
       # remove the default file in site-enable
       sudo rm sites-enabled/default

       # copy this
       # marvin-ramos.conf file
        server {
            listen 80 default_server;
            listen [::]:80 default_server;
            server_name _;
            root /home/marvin-ramos/freelance-portfolio-app/public;

            index index.html index.htm index.php;

            charset utf-8;

            location / {
                try_files $uri $uri/ /index.php?$query_string;
            }

            location ~ \.php$ {
                fastcgi_pass unix:/var/run/php/php8.3-fpm.sock;
                fastcgi_index index.php;
                fastcgi_param SCRIPT_FILENAME $realpath_root$fastcgi_script_name
                include fastcgi_params;
            }

            location ~ /\.(?!well-known).* {
                deny all;
            }
        }

        # connecting the sites-available to sites-enable
        sudo ln -s /etc/nginx/sites-available/marvin-ramos.conf /etc/nginx/sites-enabled/

        # test the nginx and reload it
        sudo nginx -t
        sudo service nginx reload

        # for checking if there are nginx error
        nano /var/log/nginx/error.log

        # if you encounter permission denied in nginx log error.log
        # go to nginx config file
        nano /etc/nginx/nginx.conf

        # connect the www-data to our project
        sudo usermod -a -G marvin-ramos www-data

        # if you encounter FASTCGI error
        # go to php file
        sudo nano /etc/php/8.3/fpm/pool.d/www.conf

        # www.conf
        # look for [www] modify it [www] -> [marvin-ramos]
        # look for user = www-data modify it user = www-data -> user = marvin-ramos
        # look for group = www-data modify it group = www-data -> group = marvin-ramos
        # look for listen.owner = www-data modify it listen.owner = www-data -> listen.owner = marvin-ramos
        # look for listen.group = www-data modify it listen.group = www-data -> listen.group = marvin-ramos

        # after you change it give a proper permission to the project
        sudo chown -R marvin-ramos:marvin-ramos /home/marvin-ramos/freelance-portfolio-app
        sudo chmod -R 755 /home/marvin-ramos/freelance-portfolio-app
        sudo chmod -R 775 /home/marvin-ramos/freelance-portfolio-app/storage
        sudo chmod -R 775 /home/marvin-ramos/freelance-portfolio-app/bootstrap/cache

        # restart the php8.3-fpm and nginx service and re test it
        sudo service php8.3-fpm restart
        sudo systemctl restart nginx
        sudo nginx -t
  ```

- ## Module 4: Deploy Workers

  https://www.youtube.com/watch?v=Srz7rU01cnM&list=PL1tt6av2E5dZyI15I658u_lVhKg3jbtjS&index=5

- ## Module 5: Deploy Scheduler

  https://www.youtube.com/watch?v=WwlII2dQl30&list=PL1tt6av2E5dZyI15I658u_lVhKg3jbtjS&index=6

- ## Module 6: Migrate from SQLite to MySQL

  Terminal: `Ubuntu`  
   Command:

  ```sh
      # install mysql
      # do not use the user use the ubuntu for admin
      # assign new root password
      sudo apt install -y mysql-server
      sudo mysql
      ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'Sample.Data@0896';

      # run mysql installation
      mysql_secure_installation

      # Press y|Y for Yes, any other key for No: y
      # Change the password for root ? ((Press y|Y for Yes, any other key for No) : n
      # Remove anonymous users? (Press y|Y for Yes, any other key for No) : y
      # Disallow root login remotely? (Press y|Y for Yes, any other key for No) : y
      # Remove test database and access to it? (Press y|Y for Yes, any other key for No) : y
      # Reload privilege tables now? (Press y|Y for Yes, any other key for No) : y

      # login to your mysql root user
      mysql -u root -p

      # create a table
      CREATE DATABASE `freelance-portfolio-app` CHARACTER SET utf8 COLLATE utf8_unicode_ci;
      CREATE USER 'freelance-portfolio-app'@'localhost' IDENTIFIED BY 'Sample.Data@0896';
      GRANT ALL PRIVILEGES ON `freelance-portfolio-app`.* TO 'freelance-portfolio-app'@'localhost';
      FLUSH PRIVILEGES;

      # update the .env file based on the mysql credentials above
  ```

- ## Module 7: Setup Domain Name & TLS/SSL
  https://www.youtube.com/watch?v=NZqRBRga3TQ&list=PL1tt6av2E5dZyI15I658u_lVhKg3jbtjS&index=8
