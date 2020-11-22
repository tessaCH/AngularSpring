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

### Update app.module.ts
1. Add `HttpClientModule` in @NgModule->imports </br>
  Add `import { HttpClientModule } from '@angular/common/http';`</br>
2. Add `ProductService` in @NgModule->providers </br>
  (Auto-imported) `import { ProductService } from './services/product.service';`

### Update product-list.component.ts & Test run
#### Find the component name
Find app.component.html in ```myproject->src->app->app.component.html```</br>
Copy the value 'app-product-list' in @Component->selector: </br>
#### Use the component name tag
Find product-list.component.ts in ```myproject->src->app->components\product-list->product-list.component.ts```</br>
Paste the components name as tag name as ```<app-product-list></app-product-list> !``` at the bottom of the page text.</br>
Run the server with ```ng serve --open```. It would show ```product-list works!``` on the web page.

### Update product.service.ts
Find product.service.ts in ```myproject->src->app->services->product.service.ts```</br>
Update `class ProductService` with:</br>
1. Add baseUrl(Spring Data REST route)</br>
2. Update constructor(inject `HttpClient`)</br>
  (Auto-imported) `import { HttpClient } from '@angular/common/http';`</br>
3. Observable(mappng the JSON data from Spring Data REST to Product array)</br>
  (Auto-imported) `import { Observable } from 'rxjs';`</br>
  Add `import { map } from 'rxjs/operators';`</br>
```
  private baseUrl = 'http://localhost:8080/api/products';

  constructor(private httpClient: HttpClient) { }

  getProductList(): Observable<Product[]>{
    return this.httpClient.get<GetResponse>(this.baseUrl).pipe(
      map(response => response._embedded.products)
    );
  }
```
Add `interface GetResponse` (unwraps the JSON from Spring Data REST to `_embedded` entry)</br>
  (Auto-imported) `import { Product } from '../common/product';`</br>
```
interface GetResponse {
  _embedded: {
    products: Product[];
  }
}
```

### Update product.ts
Find product.ts in ```myproject->src->app->common->product.ts```</br>
Add key: type content in `class Product`</br>
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

### Update product-list.component.ts
Find product-list.component.ts in ```myproject->src->app->component\product-list->product-list.component.ts```</br>
Update `class ProductListComponent implements OnInit` with:</br>
1. Add `product` array (以`Product[]`格式存放listProducts資料)</br>
  (Auto-imported)`import { Product } from 'src/app/common/product';`</br>
2. Update constructor(inject `ProductService`)
  (Auto-imported)`import { ProductService } from 'src/app/services/product.service';`</br>
3. Add `listProducts()` (subscribe以調用 `productService.getProductList()`)</br>
4. ngOnInit(call `listProducts`)(非同步Asynchronous， similar to @PostConstruct)</br>
```
  products: Product[];

  constructor(private productService: ProductService) { }

  ngOnInit() {
    this.listProducts();
  }

  listProducts(){
    this.productService.getProductList().subscribe(
      data => {
        this.products = data;
      }
    )
  }
```

### Update product-list.component.html & Test run
Find product-list.component.html in ```myproject->src->app->components\product-list->product-list.component.html```</br>
Replace the contnet as follows:</br>
```
<p *ngFor="let tempProduct of products">
    {{tempProduct.name}}: {{ tempProduct.unitPrice | currency: 'USD'}}
</p>
```
