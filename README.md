# Angular-Spring Boot Study Notes
Udemy course. Github of the tutor : darbyluv2code/fullstack-angular-and-springboot

## Angular
### Installation
Pre-install: Vidual Studio Code, Node.js, TypeScript(via npm)</br></br>
For the installation guide, visit: [install-ms-windows.md](https://github.com/tessaCH/fullstack-angular-and-springboot/blob/master/install-angular-tools/ms-windows/install-ms-windows.md)</br>

Windows 10 trouble-shooting with VS Code
> Run Visual Studio Code as Administrator</br>
> In the Terminal Window of VS Code, run `Set-ExecutionPolicy RemoteSigned` on PowerShell.

### File Type
.tsc -> .js

### Compile and Output
Transfer .tsc into .js: ```tsc xxx.ts``` </br>
Run code: ```node xxx.js```

### Define Variables
`let <variableName> : <type> = <initial value>;`</br>
ex:</br>
```
Type restricted:
  let found: boolean = true;
  let grade: number = 99.1;
  let carBrand: string = "Benz";
  let scooterType: string = 'Yamaha';
 Type free:  
  let myData: any = 'TV';
  myData = false; myData=50.0;
```

### String Concatenation
```
console.log("The grade of the car " + carBrand + "is" + grade);
console.log(`The grade of the car ${carBrand} is ${grade}`);
```
Both output: `The grade of the car Benz is 99.1`

### Arrays
declare: `let sports: string[] = ["Golf", "Cricket", "Tennis"];`</br>
remove the last element: `sports.pop();`</br>
add an element: `sports.push("Baseball");`</br>
iterate through the array:
```
sports.forEach(function(tempSport){
    console.log(tempSport);
});
```
output: Golf Cricket Baseball

### For Loops
let reviews: number[] = [5, 4.5, 3, 2.5, 1];</br>
let total: number = 0;
#### For (conditional)
```
for(let i=0; i < reviews.length; i++){
    total += reviews[i];
}
```
#### For ... of (iterate)
```
for(let tempNum of reviews){
    total += tempNum;    
}
```
#### For ... in (iterate)
```
for(let tempNum in reviews){
    total += tempNum;    
}
```
let average: number = total / reviews.length;</br>
console.log(\`Review total = ${total}, average = ${average}\`);</br>
output: Review total = 16, average = 3.2
