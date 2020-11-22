# Angular-Spring Boot Study Notes
Udemy course. Github of the tutor : darbyluv2code/fullstack-angular-and-springboot

## Front End
### Installation
Pre-install: Vidual Studio Code, Node.js</br>
npm-install:  TypeScript(```npm install -g typescript```), Angular(```npm install -g @angular/cli```)</br>

For the installation guide, visit: [install-ms-windows.md](https://github.com/tessaCH/fullstack-angular-and-springboot/blob/master/install-angular-tools/ms-windows/install-ms-windows.md)</br>

Windows 10 trouble-shooting with VS Code
> Run Visual Studio Code as Administrator</br>
> In the Terminal Window of VS Code, run `Set-ExecutionPolicy RemoteSigned` on PowerShell.

### TypeScript
#### File Type
.tsc -> .js

#### Compile and Output
Transfer .tsc into .js: ```tsc xxx.ts``` </br>
(Avoid file generation with any compliation error: ```tsc --noEmitOnError xxx.ts```)</br>
Run code: ```node xxx.js```

#### Config
Generate the tsconfig.json file: ```tsc --init```</br>
To add "--noEmitOnError" as a default option during compliation,</br>
add a new line: ```"noEmitOnError": true, ``` in ```"complilerOptions":{}```

#### Define Variables
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

#### String Concatenation
```
console.log("The grade of the car " + carBrand + "is" + grade);
console.log(`The grade of the car ${carBrand} is ${grade}`);
```
Both output: `The grade of the car Benz is 99.1`

#### Arrays
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

#### For Loops
let reviews: number[] = [5, 4.5, 3, 2.5, 1];</br>
let total: number = 0;
##### For (conditional)
```
for(let i=0; i < reviews.length; i++){
    total += reviews[i];
}
```
##### For ... of (iterate)
```
for(let tempNum of reviews){
    total += tempNum;    
}
```
##### For ... in (iterate)
```
for(let tempNum in reviews){
    total += tempNum;    
}
```
let average: number = total / reviews.length;</br>
console.log(\`Review total = ${total}, average = ${average}\`);</br>
output: Review total = 16, average = 3.2

#### Class
defining the constructor:
```
class Customer {
  private _firstname: string;
  private _lastName: string;
  constructor(theFirst: string, theLast: string){
    this._firstName = theFirst;
    this,_lastName = theLast;
  }
  //accessors: get/set
  ...
}
```
defining the constructor:(short cut): 
```
class Customer {
  constructor(private _firstName: string, private _lastName: string){
  }
  //accessors: get/set
  ...
}
```
defining accessors:
```
class Customer {
  //constructor
  ...
  public get firstName(): string{
    return this._firstName;
  }
  public set firstName(value: string){
    this._firstName = value;
  }
  //accessors for lastName
   ...
}
```
use:
```
let newCustomer = new Customer("Sue","Goodman");
console.log(newCustomer.firstName);
console.log(newCustomer.lastName);
```
#### Import / Export
export (add "export" before class declaration):
```export class Customer { ... }```
import (add the declaration on top of other .ts file):
```import { Customer } from './Customer';```

#### Inheritance
Parent Class (Shape.ts): 
```
export class Shape {
  constructor(private _x: number, private _y: number){  
  }
  //accessors: get/set
  ...
  getInfo(): string {
    return `x=${this._x}, y=${this._y}`;
  }
}
```
Child Class (Circle.ts):
```
import { Shape } from './Shape';
export class Circle extends Shape {
  constructor(theX: number, theY: number, private _radius: number){  
    super(theX, theY);
  }
  //accessors: get/set
  ...
  getInfo(): string {
    return super.getInfo() + `, radius=${this._radius}`;
  }
}
```
output with an array (ArrayShapes.ts):
```
import { Shape } from './Shape';
import { Circle } from './Circle';
let myShape = new Shape(10, 15);
let myCircle = new Circle(5, 10, 20);
//declare an array of shapes
let theShapes: Shape[] = [];
//add the shapes to the array
theShapes.push(myShape);
theShapes.push(myCircle);
//out put result
for(let tempShape of theShapes){
  console.log(tempShape.getInfo());
}
```
> `tsc` -> `node ArrayShapes.ts`</br>
> x=10, y=15</br>
> x=5, y=10, radius=20</br>

#### Abstract
Abstract Class (Vihecal.ts): 
```
export abstract class Vihecal {
  constructor(private _tankVolume: number, private _fuelConsumption: number){
  }
  //accessors: get/set
  ...
  enduranceInfo(): string {
    return `tankVolume=${this._tankVolume}, fuelConsumption=${this._fuelConsumption}`;
  }
  abstract calculateMile(): number;
}
```
Abstract subclass (Car.ts):
```
import { Vihecal } from './Vihecal';
export class Car extends Vihecal {
  constructor(theTankVolume: number, theFuelConsumption: number, private _consumptionBias: number){  
    super(theTankVolume, theFuelConsumption);
  }
  //accessors: get/set
  ...
  enduranceInfo(): string {
    return super.enduranceInfo() + `, consumptionBias=${this._consumptionBias}`;
  }
  calculateMile(): number {
    return theTankVolume * theFuelConsumption * Math.pow(this._consumptionBias, 2);
  }
}
```
output with an array (ArrayShapes.ts):
```
import { Shape } from './Shape';
import { Circle } from './Circle';
let myShape = new Shape(10, 15);
let myCircle = new Circle(5, 10, 20);
//declare an array of shapes
let theShapes: Shape[] = [];
//add the shapes to the array
theShapes.push(myShape);
theShapes.push(myCircle);
//out put result
for(let tempShape of theShapes){
  console.log(tempShape.getInfo());
}
```
> `tsc` -> `node ArrayShapes.ts`</br>
> x=10, y=15</br>
> x=5, y=10, radius=20</br>
### Angular
