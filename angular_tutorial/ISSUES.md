##Tutorial Issues

###Step 6 — Adding Angular Material

- Seperate the import grouping for @angular/material.
- Opting out of Ivy in version 9 due to MatProgressSpinnerModule conflict. 
 - Source https://angular.io/guide/ivy
-- Add to {} tsconfig.app.json
  "angularCompilerOptions": {
    "enableIvy": false
  }

  -Step 7, Mocking a REST API
  - npm install --save json-server 
  - found 4 vulnerabilities (2 low, 2 high)
  run `npm audit fix` to fix them, or `npm audit` for details

  run 'npm audit' to display security report

  