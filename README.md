Angular Project with important files
1. package.json
   1. COntains all standard packages required for development and testing (devDependencies)
   2. All packages those are required during production (depdnencies)
2. tsconfig.json
   1. TypeScript configuration file, this contains the configuration of Angular source file compilations
3. angular.json
   1. Angular Project configurations
      1. Dev. Build
      2. Test Build
      3. Production Build
4. main.ts
   1. Entrypoint of Angular application
5. Ahead-of-Time (AoT)
   1. If aot=true then, Pre-Compiles the angular application on server and generate buil/test/production files whicj can bedelivered to browser
   2. If aot=false, the angular uses JIT compiler, this loads the code in browser and compiled in browser. Slower than Aot
   3. Angular 9+ the aot=true by default uses Ivy compiler, compiles all js and HTML templates into high-compressed production files.
      1. Ivy will be used in production build
======================================================================
Angular Main classes
1. NgModule, applied on class to uses that class as Angular module
2. Component, , applied on class to uses that class as Angular component
3. Injectable, , applied on class to uses that class as Angular Service
4. Directive , applied on class to uses that class as Angular Directive
5. Pipe , applied on class to uses that class as Angular Pipe
  
======================================================================Angular Dev. Build
1. runtime.js
   1. The Angular Runtime JS Object to execute app in browser
2. polifills.js
   1. The interface to execute ES6 methods in browser
3. styles.js
   1. JS object for all internal and external css
4. vendor.js
   1. JS transpilation of all standard Angular Packages
5. main.js
   1. The Develope transpilaed code
======================================================================
Programming with Angular
IMP*** Each Component must be declaraed in 'declarations' array of NgModule 
1. Binding
   1. Interpolation
      1. Read-only binding
      2. {{<PUBLIC-DATA-MEMBER-FROM-COMPONENT>}}
      3. Uses JavaScript's eval() function
         1. {{2+4}} --> 6
   2. Property Binding
      1. HTML DOM is bound with the public datamember of component
         1. <input type="text" [value]="<PUBLIC-DATA-MEMBER-FROM-COMPONENT>">
         2. [href], [checked] [disable], etc
            1. Defined iin BrowserModule
         3. [myval]
   3. Event Binding
      1. <input type="button" (click)="<PUBLIC-METHOD-FROM-COMPONENT>">
   4. Two-Way Binding
      1. Property Binding + Event Binding
      2. Attribute Directive of name 'ngModel'
      3. <input type="text" [(ngModel)]="<PUBLIC-DATA-MEMBER-FROM-COMPONENT>">
      4. To execute ngModel, we need to import 'FormsModule' from @angular/forms package in 'imports' array of NgModule.
      5. ngModel, contains ngModelChanges event, 
         1. watch the default event on DOM element where ngModel is applied e.g. <input>/<select> DOM elemnt's, the default event is 'change'
         2. ngModel will read the updated value of DOM element, and pass the value to component to the currespoing proeprty 
         3. Component will update itself and then update the property and all other properties those are depending on property bi=eing updated.
         4. Send the updated values back to the UI using BInding
2. The Directives
   1. They are the objects those will be used to define Custom Reusable UI and or custom reusable function behavior for HTML DOM elements
   2. Component Directive
      1. To re-use component as reusable directive then use it in the HTML of other component using its selector
   3. Structural Directives
      1. USed to modify DOM elements using iterations, conditional statements
         1. *ngFor, accepts for..of loop and iterates over a collection
         2. *ngIf, accepts boolean condition
         3. *ngSwitch-ngSwitchCase
   4. Attribute Directives
      1. Attributes applied on DOM elements to define ite behavior e.g. ngModel
      2. e.g.
         1. formGroup, formControlName
3. Components Reusability
   1. Input and Output
   2. Component Parent Child Communication 
4. Forms
   1. Reactive Forms
   2. Validations
5. Services
   1. Observers with Components
   2. HTTP Communications
      1. Secure calls 
   3. Interceptor
6. LitElements and Angular Elements
   1. Creating Web Components
7. Micro-FrontEnds
   1. USing Elements with independent libraries
8. Routing
   1. SPA 
   2. Lazy Loading
9.  Testing
   3. Jest
      1. Component
      2. Service
10. Misc
   4.  IOTA CSS
   5.  Gulp
   6.  Custom Decorators

