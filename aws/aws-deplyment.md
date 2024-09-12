## App Deployment

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
