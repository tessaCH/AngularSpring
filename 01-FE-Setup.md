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
Find index.html in ```myproject->src->index.html```</br>
Visit: [getbootstrap](https://getbootstrap.com/)</br>
Get started->[Starter template](https://getbootstrap.com/docs/4.5/getting-started/introduction/#starter-template)</br>
Copy the lines as follows
```
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">

    <!-- Bootstrap CSS -->
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@4.5.3/dist/css/bootstrap.min.css" integrity="sha384-TX8t27EcRE3e/ihU7zmQxVncDAy5uIKz4rEkgIXeMed4M0jlfIDPvg6uqKI2xXr2" crossorigin="anonymous">
```
paste inside `<head></head>`, and remove the original `viewport` line</br>

### Edit app.component
Find app.component.html in ```myproject->src->app->app.component.html```</br>
Remove all the content and add some div class with text inside.</br>
Type```ng serve --open```in CLI to start server.</br>
If it shows what you have typed, then the first step has been completed.

### Install Bootstrap with npm
Type `npm install bootstrap` in CLI</br>
If it shows vulnerability issue as what I've got :</br>
> found 1 high severity vulnerability</br>
Follow the construction like typing `npm audit fix`

### Install Font Awesome with npm
Type `npm install @fortawesome/fontawesome-free` in CLI</br>
If it shows vulnerability issue as what I've got :</br>
> found 1 high severity vulnerability</br>
Follow the construction like typing `npm audit fix`

### Check Dependencies in package.json
Find package.json in ```myproject->package.json```</br>

### Update angular.json
Find angular.json in ```myproject->angular.json```</br>
Add css of Bootstrap and FontAwesome in "styles"
```
  "styles": [
    "src/styles.css",
    "node_modules/bootstrap/dist/css/bootstrap.min.css",
    "node_modules/@fortawesome/fontawesome-free/css/all.min.css"
  ],
```
