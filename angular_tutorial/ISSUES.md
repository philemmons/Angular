# Tutorial Issues

### Step 6 — Adding Angular Material

- Seperate the import grouping for @angular/material.
- Opting out of Ivy in version 9 due to MatProgressSpinnerModule conflict. 
 - Source https://angular.io/guide/ivy
 - Add to {} tsconfig.app.json
  "angularCompilerOptions": {
    "enableIvy": false
  }

### Step 7 - Mocking a REST API
- npm install --save json-server 
- found 4 vulnerabilities (2 low, 2 high)
run `npm audit fix` to fix them, or `npm audit` for details

run 'npm audit' to display security report

### Step 8 -  Creating a Service for Consuming the REST API with Angular HttpClient

- src/app/api.service.ts  file 
- change line to 
  >>> private SERVER_URL = "http://localhost:3000/products/";

  - src/app/home/home.component.html file
  - comment out line, images do not exist in JSON
  >>> <img style="height:100%; width: 100%;" src="{{ product.imageUrl }}" />

### Step 9 — Adding Error Handling

- src/app/api.service.ts  file
- change line to 
  >>> public get(){  {...}

### Step 10 — Adding Pagination
 - src/app/data.service.ts does not exist, goto src/app/api.service.ts
 - Add the variables to class ApiService.
 - sendGetRequest() function is called public get(){...}
 - import HttpParams from '@angular/common/http'
 - Add import { takeUntil } from 'rxjs/operators';
 - Add import { ReplaySubject } from 'rxjs';
 - Add to class HomeComponent 
  >>> private destroy$: ReplaySubject<boolean> = new ReplaySubject(1);
  >>> source: // https://stackoverflow.com/questions/42490265/rxjs-takeuntil-angular-components-ngondestroy
   - the subscibe() function is the ngOnInit(){...} function.
    - In the src/app/home/home.component.ts file, add the following paganation methods to class HomeComponent.
    


