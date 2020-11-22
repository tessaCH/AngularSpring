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

### Use Bootstrap
find index.html in ```myproject->src->index.html```</br>
visit: [getbootstrap](https://getbootstrap.com/)</br>
Get started->[Starter template](https://getbootstrap.com/docs/4.5/getting-started/introduction/#starter-template)</br>
Copy the lines as follows
```
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">

    <!-- Bootstrap CSS -->
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@4.5.3/dist/css/bootstrap.min.css" integrity="sha384-TX8t27EcRE3e/ihU7zmQxVncDAy5uIKz4rEkgIXeMed4M0jlfIDPvg6uqKI2xXr2" crossorigin="anonymous">
```
paste inside `<head></head>`, and remove the original `viewport` line</br>

### Edit app.component
find app.component.html in ```myproject->src->app->app.component.html```</br>
Remove all the content and add some div class with text inside.</br>
type```ng serve --open```in CLI to start server.</br>
If it shows what you have typed, then the first step has been completed.
