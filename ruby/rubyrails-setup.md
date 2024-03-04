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

Code:  
```sh
gem install rails
rails --version
Rails 7.1.3.2
```

**Creating New Rails Projects**
Code:  
```sh
rails new projectName
```

**Running Rails Projects**

- go to your project directory

Code:  
```sh
cd projectName
```

- Starting up the Web Server

Code:  
```sh
rails server
```

**Note**
- If you are using Windows, you have to pass the scripts under the bin folder directly to the Ruby interpreter e.g. ruby bin\rails server.
- Compiling CoffeeScript and JavaScript asset compression requires you have a JavaScript runtime available on your system, in the absence of a runtime you will see an execjs error during asset compilation. Usually macOS and Windows come with a JavaScript runtime installed. Rails adds the therubyracer gem to the generated Gemfile in a commented line for new apps and you can uncomment if you need it. therubyrhino is the recommended runtime for JRuby users and is added by default to the Gemfile in apps generated under JRuby. You can investigate all the supported runtimes at ExecJS.
- https://github.com/rails/execjs#readme

