# Tutorial Issues

### Step 6 — Adding Angular Material

- Seperate the import grouping for @angular/material.
- Opting out of Ivy in version 9 due to MatProgressSpinnerModule conflict. 
    - source https://angular.io/guide/ivy
 - Add to {} tsconfig.app.json file:

```
  "angularCompilerOptions" : {
  "enableIvy": false
  }
```

### Step 7 - Mocking a REST API
- After npm install --save json-server, 4 vulnerabilities (2 low, 2 high) were identified.
  - run `npm audit fix` to fix them, or `npm audit` for details.
  - run 'npm audit' to display security report.

### Step 8 - Creating a Service for Consuming the REST API with Angular HttpClient

- In src/app/api.service.ts file change line to:

```
private SERVER_URL = "http://localhost:3000/products/";
```

- In src/app/home/home.component.html file, comment out the 
images, as they do not exist.
```
<img style="height:100%; width: 100%;" src="{{ product.imageUrl }}"/>
```
### Step 9 — Adding Error Handling

- In src/app/api.service.ts file change line to:
  ```
  public get(){...};
  ``` 

### Step 10 — Adding Pagination
- The src/app/data.service.ts file does not exist, goto src/app/api.service.ts file.
- Add the variables to class ApiService constructor.
- The public sendGetRequest() function is referring to public get() function.
- Add import HttpParams from '@angular/common/http';
- Add import { takeUntil } from 'rxjs/operators';
- Add import { ReplaySubject } from 'rxjs';
- Add the following to class HomeComponent:
  - source: // https://stackoverflow.com/questions/42490265/rxjs-takeuntil-angular-components-ngondestroy
```
private destroy$: ReplaySubject<boolean> = new ReplaySubject(1);
```
- The subscibe() function is referring to ngOnInit() function.
- In the src/app/home/home.component.ts file, add the paganation methods 
to class HomeComponent constructor.



