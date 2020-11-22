## Back End
### Installation
Pre-install: IntelliJ, Java, Tomcat, MySQL(8.0.4)</br>
For the MySQL Reference Manual, visit: [MySQL Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/caching-sha2-pluggable-authentication.html)</br>

### Create MySQL User
```
CREATE USER 'angularspringapp'@'localhost' IDENTIFIED BY 'angularspringapp';
GRANT ALL PRIVILEGES ON * . * TO 'angularspringapp'@'localhost';
ALTER USER 'angularspringapp'@'localhost' IDENTIFIED WITH mysql_native_password BY 'angularspringapp';
```

## Front End
### Installation
Pre-install: Vidual Studio Code, Node.js</br>
npm-install:  TypeScript(```npm install -g typescript```), Angular(```npm install -g @angular/cli```)</br>

For the installation guide, visit: [install-ms-windows.md](https://github.com/tessaCH/fullstack-angular-and-springboot/blob/master/install-angular-tools/ms-windows/install-ms-windows.md)</br>

Windows 10 trouble-shooting with VS Code
> Run Visual Studio Code as Administrator</br>
> In the Terminal Window of VS Code, run `Set-ExecutionPolicy RemoteSigned` on PowerShell.

### Create Angular Project
```ng new myproject```
```
? Would you like to add Angular routing? (y/N)
? Which stylesheet format would you like to use? (Use arrow keys)
> CSS
  SCSS   [ http://sass-lang.com   ]
  SASS   [ http://sass-lang.com   ]
  LESS   [ http://lesscss.org     ]
  Stylus [ http://stylus-lang.com ]
```
Use VS Code to start coding
```File->Open Folder->myproject->Choose Folder```
