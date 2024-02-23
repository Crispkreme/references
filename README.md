## SSH Key Generation for Github
Copy & paste the generated SSH key to your GitHub account
Terminal: `Ubuntu`  
  
Command:  
```sh
ssh-keygen -f ~/.ssh/id_rsa -P "" && clear && echo -e "Copy and paste the public key below to your GitHub account:\n\n\e[32m$(cat ~/.ssh/id_rsa.pub) \e[0m\n" # Green
```

## Test SSH Connection
Terminal: `Ubuntu`  
  
Command:  
```sh
ssh -T git@github.com -o StrictHostKeyChecking=no
```

Expected output:
```
Hi <username>! You've successfully authenticated, but GitHub does not provide shell access.
```
