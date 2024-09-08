## Removing write protected folder with content

Terminal: `Ubuntu`  
Command:  
```sh
    sudo chown -R $(whoami):$(whoami) folder_to_remove
    sudo chmod -R u+w folder_to_remove
    rm -r folder_to_remove 
    ls #to check the folder
```