# Angular-Spring Boot Study Notes
Udemy course. Github of the tutor : darbyluv2code/fullstack-angular-and-springboot

## Front End
### Create Angular Component
```ng generate component components/product-list```
```
CREATE src/app/components/product-list/product-list.component.html (27 bytes)
CREATE src/app/components/product-list/product-list.component.spec.ts (662 bytes)
CREATE src/app/components/product-list/product-list.component.ts (298 bytes)
CREATE src/app/components/product-list/product-list.component.css (0 bytes)
UPDATE src/app/app.module.ts (429 bytes)
```
### Create product constructor
```ng generate class common/product```
```
CREATE src/app/common/product.spec.ts (158 bytes)
CREATE src/app/common/product.ts (25 bytes)
```
### Create product service
```ng generate service services/product```
```
CREATE src/app/services/product.service.spec.ts (362 bytes)
CREATE src/app/services/product.service.ts (136 bytes)
```

### Use components in app.component
#### Edit the product constructor value
Find product.ts in ```myproject->src->app->common->product.ts```</br>
Edit the product content with Json form key: type```</br>
```
    sku: string;
    name: string;
    description: string;
    unitPrice: number;
    imageUrl: string;
    active: boolean;
    unitsInStock: number;
    dateCreated: Date;
    lastUpdated: Date;
```

#### Find the component name
Find app.component.html in ```myproject->src->app->app.component.html```</br>
Copy the value of @Component->selector: </br>
The value should be 'app-product-list'.</br>
#### Use the component name tag
Find product-list.component.ts in ```myproject->src->app->components\product-list->product-list.component.ts```</br>
Paste the components name as tag name as ```<app-product-list></app-product-list> at the bottom of the page text.</br>
Run the server with ```ng serve --open```. It would show ```product-list works!``` on the web page.
