## Ruby and Rails Setup

Tags: installation
https://www.ruby-lang.org/en/documentation/installation/

Code:  
```sh
ruby -v
ruby 2.3.1p112
```

**Sqlite3 installation**
- go to https://www.sqlite.org/download.html
- download precompiled binaries for windows .zip
- create a folder inside C:\Program Files named sqlite. Extract the downloaded zip and put all three binary files in this folder.
- Go to environment variables, chose Path variable and add C:\Program Files\sqlite to the path.

Code:  
```sh
sqlite3 --version
3.45.1 2024-01-30 16:01:20 e876e51a0ed5c5b3126f52e532044363a014bc594cfefa87ffb5b82257cc467a (64-bit)
```
