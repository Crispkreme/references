## App Deployment (Normal Deployment)

Terminal: `Ubuntu`  
Command:  
```sh

    # push all the changes first into your repository
    # connect to your aws first from your pc
    # then go to the mongodb
    # create a new database
    # Create bookingAPI
    # collection name "courses"
    # connect to your aws-instance using ssh in your pc
    # go to your repository in git

    # inside the ssh cmd in your computer
    git clone https://git.zuitt.co/marvinmramos.zuitt/B478-Aws.git

    # then put your credential if needed like password or username
    cd B478-Aws
    cd server # this is a sub-folder
    less .env # less - display the file content without updating the file.
    
    # in the .env update the CONNECTION_STRING based on your mongodb connection string.
    # go to the mongodb
    # click overview
    # in dashboard find and click the connect button
    # select drivers
    # copy the connection string with this format "CONNECTION_STRING=<mongodb_connections_tring>/bookingAPI?retryWrites=true&w=majority"
    # back to your computer ssh command
    # update the .env file

    nano .env
    
    # then save the file
    # check the .env file if updated successfully

    less .env
    cd ..
    cd client # sub-folder
    less .env
    nano .env

    # then save the file
    # check the .env file if updated successfully

    less .env
    npm run dev

    cd ..
    cd server
    npm install

    # go back to your aws-instances
    # find the Public IPv4 DNS
    # then paste the public ipv4 dns into the .env file in the front-end
    # if finish

    nano .env
    less .env
    ls -A
    node index.js

    # go back to the aws instance
    # copy your pblic ip address
    # go to the security group 
    # look for inbound card
    # edit inbound rule
    # add rule
    
    # backend setup
    # type=custom tcp | port = 4000 | source = anywhere ipv4

    # frontend setup
    # type=custom tcp | port = 3000 | source = anywhere ipv4
    
```

## App Deployment (Nginx and PM2)
Terminal: `Ubuntu`  
Command:  
```sh

    # installing the PM2
    mkdir ~/.npm-global
    ls -A
    npm config set prefix '~/.npm-global' # setting this globally accessible
    sudo nano ~/.profile # updating the profile access

    # go to the very bottom of the .profile file
    # just paste it in the bottom of profile
    export PATH=~/.npm-global/bin:$PATH

    less .profile # viewing if the file is updated
    source ~/.profile

    # install PM2 depedencies
    npm install pm2 -g
    
    # go into the index.js of the server file inside the server folder
    cd server
    ls
    # it would run your vm on the server once started
    pm2 start index.js # starting server
    pm2 stop index.js # stoping server
    pm2 status # viewing server status
    pm2 delete index.js # deleting server
    pm2 restart index.js # restarting server

    #install nginx
    sudo apt-get update
    sudo apt-get install nginx
    cd /etc/nginx/sites-available/

    # check if default file is available
    ls -A
    nano default

    # look for this keyword and in updating
    # replace the keyword with this
    # listen:80;
    # listen[::]:80;
    # root /var/www/html/build
    # try_files $uri $uri/ /index.html;

    # save the file
    # ctrl+o
    # ctrl+x

    # go back to the frontend folder
    cd ../../../
    cd client
    npm run build

    # check if build is created
    ls 
    sudo cp -r build/ /var/www/html/
    cd /var/www/html 

    # checking if build is existed in this location
    ls

    # starting nginx 
    sudo systemctl start nginx
    
    # check for the nginx if it is running
    sudo systemctl status nginx

    # set up the security group
    # go to aws console
    # ec2/security groups/
    # type=custom tcp | port = 80 | source = anywhere ipv4

    # restarting nginx 
    sudo systemctl restart nginx
```

## STATIC WEB HOSTING

Terminal: `Ubuntu`  
Command:  
```sh

    # go to aws 
    # find the s3
    # click create a bucket

    # go to general purpose
    # bucket tyepe = general purpose
    # bucket name = any (based on you want)

    # go to object ownership
    # ACLs enable
    # uncheck all block all access
    # check check the yellow dialog card

    # go inside the bucket

    # go to properties
    # static web hosting 
    # click edit
    # click enable
    # index document = index.html
    # save changes

    # go to objects
    # go to upload
    # drag all the files
    # go to action button dropdown 
    # look for "Make public ACL"

```