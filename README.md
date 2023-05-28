# Angular-Tutorial

Angular tutorial and guide for interviews.

| No. | Question                                                                             |
| --- | ------------------------------------------------------------------------------------ |
| 1   | [Benefits of Angular.](#benefits-of-angular)                                         |
| 2   | [Define single page application.](#define-single-page-application)                   |
| 3   | [Discuss angular features.](#discuss-angular-features)                               |
| 4   | [What decorators can be used with class.](#what-decorators-can-be-used-with-class)   |
| 5   | [How angular bootstraps the app.](#how-angular-bootstraps-the-app)                   |
| 6   | [Angular project structure.](#angular-project-structure)                             |
| 7   | [Define component.](#define-component)                                               |
| 8   | [Define data binding.](#define-data-binding)                                         |
| 9   | [Define angular directives.](#define-angular-directives)                             |
| 10  | [Use of \*ngFor directive.](#Use-of-ngFor-directive)                                 |
| 11  | [\*How to use trackBy in \*ngFor.](#how-to-use-trackBy-in-ngFor)                     |
| 12  | [\*Use of ngClass and ngStyle.](#use-of-ngClass-and-ngStyle)                         |
| 13  | [\*Create a custom directive.](#create-a-custom-directive)                           |
| 14  | [Define angular pipes.](#define-angular-pipes)                                       |
| 15  | [Create a custom pipe.](#create-a-custom-pipe)                                       |
| 16  | [\*Define async pipe.](#define-async-pipe)                                           |
| 17  | [\*How to pass data between parent and child component.](#define-async-pipe)         |
| 18  | [\*Define content projection.](#define-content-projection)                           |
| 18  | [\*Define ngOnChanges.](#define-ngOnChanges)                                         |
| 19  | [What are the lifecycle hooks in angular.](#what-are-the-lifecycle-hooks-in-angular) |

1.  ### Benefits of Angular.

    There are multiple benefits of angular over other platforms.

    1. Development platform to build single page applications, hybrid mobile apps.
    2. Comes with lots of inbuilt features like http services, routing, dependency injection, forms, pipes,
       factory design pattern.
    3. Uses Typescript and HTML to build Apps. (Angular is written Typescript).
    4. Provides more structured approach to development.Hence useful in large projects.

2.  ### Define single page application.

    A web app implementation that uses only single web document to display website content. Client does not need to load whole new web page from the server every time. One web document is loaded and then components are updated inside the body of this document. This improves the performance.

3.  ### Discuss angular features.

    Some of the features of angular are :

    1. Component based structure.
    2. Modules.
    3. Dependency Injection.
    4. Powerful templates.
    5. Two-way data binding.
    6. Routing.
    7. Forms.
    8. Http module.
    9. Testing.

4.  ### What decorators can be used with class.

    1. @Component
    2. @Directive
    3. @Injectable
    4. @NgModule
    5. @Pipe

5.  ### How angular bootstraps the app.

    To load the first view, following steps are taken internally by angular.

    1. Load index.html file.
    2. Load Angular & third party libs.
    3. Run the application entry point (main.ts). The path for entry point is mentioned in the angular.json file.
    4. Load the app module mentioned in the main.ts file.
    5. Execute the main app component mentioned in the app module.
    6. Display the main component html file.

6.  ### Angular project structure.

    Following are the important files and folders in angular project.

    1. package.json.
    2. package-lock.json
    3. angular.json
    4. tsconfig.ts
    5. node_modules
    6. src: src/app, src/assets, src/environments, src/styles.css, src/main.ts, src/test.js.
    7. e2e
    8. dist.

7.  ### Define component.

    Angular component contains data and logic of how the view(html) will look and behave. To define a class as component we can use @component decorator. Component metadata consist of 3 main blocks selector, templateUrl, and styleUrls. Others - providers, directives.

8.  ### Define data binding.

    A way to pass and sync data between component and view. There are two types of data binding - one way, two way.\
     One way binding : Data flows in one direction. Component to view or vice versa.\
     To pass data from component to view interpolation, property binding, and attribute binding can be used.\
     Example : interpolation - {{varInComponent}}, property binding - [disabled] = "true", [attr.aria-label]="label".\
     To pass data from view to component event binding can be used. \
     Example : (click) ="handlerFxn()", (keyUp), (change) etc. \
    Two way binding : Data flows in both direction. NgModel directive can be used to achieve this. example : [(ngMOdel)] = "variable".
    [(ngModel)] is converted to [ngModel] and (ngModelChange).

9.  ### Define angular directives.

    Directives are used to manipulate the DOM elements appearance or behavior. Directives are mainly classified into 3 categories: component, structural(*ngFor, *ngIf, \*ngSwitch), attributes(ngModel, ngClass, ngStyle).

10. ### Use of \*ngFor directive.

    Its used to iterate over a collection like array, object. To iterate over the object we can use the |keyvalue :comparatorFxn pipe.
    \*ngFor also provides variables like index, odd, even, trackBy, last, first.

11. ### Define angular pipes.
    Angular pipes are used to transform the data to display in the template. Some of the commonly used pipes are : |date [:format], |uppercase, |lowercase, |decimal, |currency[:currencyCode[:symbolDisplay[:digitInfo]]],|percent[:digitInfo], |number[:digitInfo], |slice:start:end, |async.
12. ### Create a custom pipe.

    Steps to create new custom pipe:

    1.  Create a class for the pipe.
    2.  Decorate it using the @pipe decorator.
    3.  Give name to pipe using the name metadata of @pipe decorator.
    4.  Implement the class using the PipeTransform interface. It only contains one method transform which has first parameter holding the value to be transformed. This value is transformed and returned by the method. The method can have multiple parameters.\

    ```
    import {Pipe, PipeTransform} from '@angular/core';
       @pipe({
          name: 'toUpperCase'
          })
       export class ToUpperCase implements PipeTransform {
          transform(value: string) {
          return  value.toUpperCase();
    }
    }
    ```

13. ### What are the lifecycle hooks in angular.
    Below are the lifecycle hooks in angular:
    1.  ngOnChanges - whenever any input property (defined using @input) of the component or directive changes.
    2.  ngOnInit - during component creation. Child component content is not available at this point. This hook is fired only once.
    3.  ngDoCheck - runs in every change detection cycle. Custom change detection whenever when angular fails to detect changes in input properties.
    4.  ngAfterContentInit - this is called after projected content of the component is initialized.This hook is also raised, even if there is no content to project. Run only once.
    5.  ngAfterContentChecked - similar to ngAfterContentInit but runs during every change detection cycle.
    6.  ngAfterViewInit - runs when components view and all the children are fully initialized. Raised during first change detection cycle.This is a component-only hook.
    7.  ngAfterViewChecked - similar to ngAfterViewInit but runs for every change detection cycle.
    8.  ngOnDestroy - runs when component is destroyed.
