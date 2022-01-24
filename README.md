# AngularTodo

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 13.1.2.

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The app will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via a platform of your choice. To use this command, you need to first add a package that implements end-to-end testing capabilities.

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI Overview and Command Reference](https://angular.io/cli) page.
































<!-- 

->  create a folder 'angular'
->  open 'cmd' in that folder
->  type 'npm install -g @angular/cli' in cmd
->  this will install angular in your sytem
->  now type 'ng new angular-todo' to create a new angular app in your system
->  ? Would you like to add Angular routing? Yes
->  ? Which stylesheet format would you like to use? CSS
->  type 'cd angular-todo' in cmd to go inside the project directory
->  type 'code .' in cmd to open project in vs code text editor 
->  type 'ng serve' in cmd tp run the application
->  details and how to change this setting, see https://angular.io/analytics. (y/N) No
->  open browser and type 'http://localhost:4200/' in a new tab to see the output
->  In 'src -> app -> index.html', you can change title if you want to
->  Let's change title to 'Angular Todo List App' in the 'index.html' file
->  on reloading the webpage, we can see changes in the tilte
->  Actual content of the webpage is coming from 'app.component.html', make any modifications if
    required
->  Go to 'app.component.ts' file, and in the export class of AppComponent, add a message as shown  
    below
    [
            export class AppComponent {
            title = 'angular-todo';
            message = 'Welcome to Social Prachar';
            }
    ]
->  Now go to the 'app.component.html' file, and add {{message}} as shown below
    [
         <span>{{ message }}</span>
    ]
->  Now, go to 'app.component.html' file, and add an additional <div> element as shown below
    [
         <div>Component Content</div>
    ]
->  Now, GoTo 'index.html' file and add a <div> element as shown below
    [
          <div>Index HTML Content</div>
    ]
->  Now, Let's start styling the divs, goto 'app.component.css' file and add the below styling
    [
                div{
                background-color: beige;
            }
    ]
->  In the browser output, we can see that only component content is getting the background color as
    'beige'
->  The Content in the 'index.html' does not get the background color
->  We can comment out the code in 'app.component.css' after seeing the changes as shown below
    [
        /* div{
            background-color: beige;
        } */
    ]
->  Let's create a new component 'Welcome Component'
->  goto cmd and type 'ng generate component welcome'
->  'app.module.ts' file is updated and in declarations, we can see 'WelcomeComponent' is added
->  In the 'app -> welcome', we can find all the files of welcome component, created just now
->  Goto 'app.component.html', and include the tag '  <app-welcome></app-welcome>' to include 
    the welcome component 
->  In the browser, upon reload,we can see the output saying 'welcome works'
->  To make things very clearly visible, Let's comment out rest of code in 'app.component.html'
->  Now, Let's crate a Login page with username and password
->  In cmd, type 'ng g c login' to create the login component
->  Now, include <app-login> in 'app.component.html' file
->  If we reload the webpage, we can find the 'login works' message 
->  Let's modify the 'app.component.html' as shown below
    [
        <app-login></app-login>
    ]
->  Now go to 'index.html' file and comment out teh div ekement we have created
    [
          <!-- <div>Index HTML Content</div> 
    ]
->  Now, go to the browser and reload the webpage to see the output, we can see the below code
    [
        login works!
    ]
->  Goto 'login.component.html' file, and write the code given below 
    [
        User Name : <input type="text" name="username">
        Password  : <input type="password" name="password" id="">
    ]
->  Let's create a button in the 'app.component.html' as shown below 
    [
        <button>Login</button>
    ]
->  Now, goto 'login.component.ts' file, and create a default name to username and default password
    [
          username = 'ADMIN'
          password = 'ADMIN'
    ]
->  Now, GoTo, 'login.component.html' file, and add that default value as shown below
    [
        User Name : <input type="text" name="username" value="{{username}}">
        Password  : <input type="password" name="password" value="{{password}}">
    ]
->  Let's try to print the username when the button is clicked, modify the button as shown below
    in the 'login.component.html' file
    [
        <button (click)="handleLogin()">Login</button>
    ]
->  In the 'login.component.ts' file, declare the 'handleLogin()' as shown below
    [
          handleLogin(){
            console.log(this.username);
            }
    ]
->  Now, go to the browser, reload the webpage, and give a username and password and click on the 
    login button
->  Inspect the page to see the username being printed in the console
->  Now let's take the data from the view and populate it into the component data
->  Go To 'login.component.html' file, and modify it as shown below
    [
        User Name : <input type="text" name="username" [(ngModel)]="username">
    ]
->  Now, it will throw an error 'Can't bind to 'ngModel' since it isn't a known property of 'input'.
->  To Resolve this issue, we need to go 'app.module.ts' file, import the FormsModule as shown below
    [
          imports: [
            BrowserModule,
            AppRoutingModule,
            FormsModule
        ],
    ]
->  All Errors will be gone and you can see implementation of two way data binding by giving 
    different usernames and checking in the consloe of the browser
->  Let's add some hardcoded authentication to Login Component i.e if we give wrong credentials to 
    login form, go to 'login.component.html', add the below line of code at the top of the page
    as shown below
->  [
        <small>{{errorMessage}}</small>
    ]
->  Let's go to the 'login.component.ts' file, and add an error message as shown below
    [
         errorMessage = 'Invalid Credentials'
         invalidLogin = false
    ]
->  modify the 'handleLogin' in the 'login.component.ts' file, as shown below
    [
          handleLogin(){
                // console.log(this.username);
                if(this.username==="ADMIN" && this.password ==="ADMIN"){
                    this.invalidLogin = false
                } else {
                this.invalidLogin = true
                }
            }
    ]
->  To show 'Invalid Credentials' only invalidCredentials = true, we can go to the 
    'login.component.html' as shown below
    [
        <small *ngIf="invalidLogin">{{errorMessage}}</small>
    ]
->  Now, you will notice that only if 'User Name' and 'Password' are both having valuies as 'ADMIN'
    you will get authentication, for any value other than 'ADMIN' in both 'User Name' and 'Password'
    you will get 'Invalid Credentials' in the browser output

---------------------------------------------------------------------------------------------------
->  Now, Let's start implementing Routes for Login, Welcome and Error Components


->  Please GoTo 'app-routing.module.ts' file, and let's add routes in it as sohwn below
    [
        const routes: Routes = [
        { path:'login', component: LoginComponent},
        { path:'welcome', component: WelcomeComponent}
        ];
    ]
->  GoTo 'app.component.html' and uncomment the routeroutlet as shown below
    [
        <router-outlet></router-outlet>
    ]
->  Also, Let's comment out the 'app-login' in the 'app.component.html' as shown below
    [
        <!-- <app-login></app-login> 
    ]
->  Now, go to the browser and type in the search url 'localhost:4200/login' to re redirected
    to login page
->  Now, go to the browser and type in the search url 'localhost:4200/welcome' to re redirected
    to welcome page
->  Also let's set the default path to be set to login component in the  'app-routing.module.ts' 
    file as shown below
    [
        { path:'', component: LoginComponent},
    ]
->  Now, if you go to the browser, and type 'http://localhost:4200/' in the url searchbar,
    you will be redirected to login page
->  Now, Let's create an error component.
->  Go to cmd and type 'ng g c error'
->  Now, Go to the 'error.component.ts' and type the below code 
    [
         errorMessage = 'An Error Occured! Please Contact The Support Team At Social Prachar' 
    ]
->  Then, Go To the 'error.component.html' file and change it as shown below
    [
        {{errorMessage}}
    ]
->  Now, Let's add this error component to the routing. So, go to the 'app-routing.module.ts' file,
    and add the error component as shown below (** means anything other than paths given above)
    [
          { path:'**', component: ErrorComponent}
    ]
->  Now go to your browser, type 'http://localhost:4200/todos' in the search url bar
    you will see 'An Error Occured! Please Contact The Support Team At Social Prachar' as output

->  Now, Let's try to implement routing from login component to welcome component when you give 
    correct username and password
->  Go To 'login.component.ts', we want to redirect to welcome page, so we need an instance of the 
    router with the help of concept of 'Dependency Injection'. 
->  So, in the constructor, we'll add router: Router [which will find the router and inject it to 
    this component]
->  All of these code changes to be made in the 'login.component.ts' file are shown below 
    [
          constructor(private router:Router) { }
    ]
->  After, hitting enter we can see that 'import { Router } from '@angular/router';' is done
    automatically by angular
->  In the 'login.component.ts' file, Inside the handleLogin(), add the below 
    [
        // Redirect to Welcome Page
        this.router.navigate(['welcome'])
    ]
->  Go to your browser, give correct credentails, and you will navigate to the welcome component

---------------------------------------------------------------------------------------------------
->  Now, let's try adding route parameter for welcome component


->  Go to 'app-routing.module.ts' file, change welcome component as shown below
    [
         { path:'welcome/:name', component: WelcomeComponent},
    ]
->  Now, go to the 'welcome.component.ts' file and edit the constructor as shown below
    [
        constructor(private route:ActivatedRoute) {
    ]
->  Also, in the same file, modify the 'ngOnInit' as shown below
    [
          ngOnInit(): void {
            this.route.snapshot.params['name']
        }
    ]
->  Now, Go To the browser, and in the search url type 'http://localhost:4200/welcome/ADMIN' to 
    the output
    you will get 'welcome works' as the output
->  Now, go to 'login.component.ts' file, and make the below modifications
    [
        this.router.navigate(['welcome',this.username])
    ]
->  Now, go to 'welcome.component.ts' file,  and add a variable as shown below
    [
          name= ''
    ]
->  Again in the 'welcome.component.ts' file, modify the ngoninit() as shown below
    [
         this.name = this.route.snapshot.params['name'];
    ]
->  Now, go to 'welcome.component.html' and add the below code
    [
        Welcome {{name}} to Social Prachar
    ]
->  In the browser, type 'http://localhost:4200/welcome/ADMIN' in the search url
    to see 'Welcome ADMIN to Social Prachar' AS OUTPUT
->  We have successfully added routing parameter. We have added a routing paramter to the 
    welcome route
->  we had to enhance the login component to pass in the parameter which is entered in by the user

---------------------------------------------------------------------------------------------------
->  Now, we are going to create a 'list todos component with ng generate'

->  In cmd type 'ng g c listTodos' to generate the component
->  Typically, after creating a component, we add the route. So, go to 'app-routing.module.ts' file
    [
         { path:'todos', component: ListTodosComponent},
    ]
    make sure you add it above **
->  Now to test it, go to your browser, type 'http://localhost:4200/todos' to see 
    'list-todos works!' as output
->  Goto 'list-todos.component.ts' file, and create simple todo objects as shown below
    [
          todos = [
            {id: 1, description: 'Master Angular'},
            {id: 2, description: 'Master Angular Material'},
            {id: 3, description: 'Master Angular MDB'},
        ]  
    ]
->  Goto 'list-todos.component.html' file, and edit it as shown below
    [
            <table border="3" style="margin-left:500px;">
                <caption>Angular Todo's</caption>
                <thead>
                    <tr>
                        <th>Id</th>
                        <th>Description</th>
                    </tr>
                </thead>
                <tbody>
                    <tr *ngFor="let todo of todos">
                        <td>{{todo.id}}</td>
                        <td>{{todo.description}}</td>
                    </tr>
                </tbody>
            </table>
    ]
-> Now, If we go to the browser, and type 'http://localhost:4200/todos' in the search url, 
    we'll get a table of list of todos as the output


----------------------------------------------------------------------------------------------------
->  Let's create a link to todos in welcome component

->  Go to 'welcome.component.html', and edit it as shown below
    [
        <div>
        Welcome {{name}}
        <br>
        Welcome to Angular Todo's App 
        </div>
        <div>
        <br>
        You Can Manage Your Todos <a routerLink="/todos">Here</a>
        </div>
    ]
->  Now, go to browser, type 'http://localhost:4200/', login, you go to trhe welcome page, 
    click on "here" to go to todos page        
->  Now, we have complete navigation in our App
->  With this we have successfully built in the login page, the welcome page and the todos page
--------------------------------------------------------------------------------------------------


->  Now let's create a todo class to represent the todo structure.
->  The best practice is to create a todo class to represent this structure and to that to create 
    the todos 
->  Go to 'list-todos.component.ts' file and create a todo class as shown below
    [
            export class Todo {
            constructor(
                public id: number,
                public description: string,
                public done: boolean,
                public targetDate: Date
            ){}
            }
    ]
->  Now, in the same 'list-todos.component.ts' file, edit the todos as shown below
    [
          todos = [
          new Todo(1, 'Master Angular', false, new Date() ),
          new Todo(2, 'Master Angular Material', false, new Date() ),
          new Todo(3, 'Master Angular MDB', false, new Date() )
        ]  
    ]
->  Go to 'list-todos.component.html' file, and edit it as shown below
    [
            <table border="3" style="margin-left:450px;">
                <caption>Angular Todo's List App</caption>
                <thead>
                    <tr>
                        
                        <th>Description</th>
                        <th>Target Completion Date</th>
                        <th>Is Completed ?</th>
                    </tr>
                </thead>
                <tbody>
                    <tr *ngFor="let todo of todos">
                        <td>{{todo.description}}</td>
                        <td>{{todo.targetDate | date | uppercase}}</td>
                        <td>{{todo.done}}</td>
                    </tr>
                </tbody>
            </table>
    ]
---------------------------------------------------------------------------------------------------


->  Let's start bootstraping our angular application
->  Goto 'app.component.html', and edit as shown below
    [
        Todo Application Header/Menu
        <br>

        <router-outlet></router-outlet>

        <br>
        Todo Application Footer
    ]
->  In the output we can see that the 'Angular Todo Application' is present along with 
    router-outlet output
->  Header and Footer position is commonly visible in the output and router-outlet will display 
    different content
--------------------------------------------------------------------------------------------------


->  Now, let us make use of bootstrap in our angular project
->  Go to any one of your favourite browser and search for 'unpkg bootstrap 5' an go to the
    'https://unpkg.com/bootstrap@4.1.0/dist/css/bootstrap.min.css' url and paste it in styles.css
    file as shown below
    [
        @import url(https://unpkg.com/bootstrap@4.1.0/dist/css/bootstrap.min.css)
    ]
->  Let's create a menu component
->  In cmd, type 'ng g c menu'
->  Let's also create a footer component
->  In cmd, type 'ng g c footer'
->  Now, Go to 'menu.component.html', and modify it as shown below
    [
        TOP MENU ELEMENTS   <br><br>
    ]
->  Now, let's go to 'footer.component.html', and modify it as shown below
    [
            <br><br>
            FOOTER
    ]
->  Let's go to 'app.component.html', and modify it as shown below
    [
            <app-menu></app-menu>
            <router-outlet></router-outlet>
            <app-footer></app-footer>
    ]
--------------------------------------------------------------------------------------------------


->  Now, Let's use bootstrap to create a menu with navigation links
->  First, we'll start wiith 'menu.component.html', and modify it as shown below
    [
        <header>
            <nav class="navbar navbar-expand-md navbar-dark bg-dark">
                <div><a href="https://www.socialprachar.com" class="navbar-brand">SocialPrachar</a></div>
                <ul class="navbar-nav">
                    <li><a href="/welcome/ADMIN" class="nav-link">Home</a></li>
                    <li><a href="/todos" class="nav-link">Todos</a></li>
                </ul>
                <ul class="navbar-nav navbar-collapse justify-content-end">
                    <li><a href="/login" class="nav-link">Login</a></li>
                    <li><a href="/logout" class="nav-link">Logout</a></li>
                </ul>
            </nav>
        </header>
    ]
---------------------------------------------------------------------------------------------------


->  Now let's start styling Footer and other components with CSS and Bootstrap
->  So, let's go to 'footer.component.html' file, and modify it as shown below
    [
        <footer>
            <div class="container">
                All Rights Reserved 2022 @SocialPrachar
            </div>
        </footer>
    ]
->  Now, go to 'footer.component.css' file, and add the below lines of code
    [
            <footer class="footer">
                <div class="container">
                    <span class="text-muted">All Rights Reserved 2022 @SocialPrachar</span>
                </div>
            </footer>
    ]
->  Now, Let's go to 'app.component.html' and modify it as shown below
    [
        <app-menu></app-menu>

        <div class="container">
            <router-outlet></router-outlet>
        </div>


        <app-footer></app-footer>
    ]
->  Go to 'list-todos.component.html' file, and add a class name to table as todos as shown below
    [
        <h1>Angular Todo's List App</h1>
        <div class="container">
        <table class="table">
            <thead>
                <tr>
                    
                    <th>Description</th>
                    <th>Target Completion Date</th>
                    <th>Is Completed ?</th>
                </tr>
            </thead>
            <tbody>
                <tr *ngFor="let todo of todos">
                    <td>{{todo.description}}</td>
                    <td>{{todo.targetDate | date | uppercase}}</td>
                    <td>{{todo.done}}</td>
                </tr>
            </tbody>
        </table>
        </div>
    ]
->  Similarly, let's also modify the 'login.component.html' file as shown below to bootstrap it
    [
            <h1>Please Login!</h1>
            <div class="container">
            <div class="alert alert-warning" *ngIf="invalidLogin">{{errorMessage}}</div>
            <div>
            User Name : <input type="text" name="username" [(ngModel)]="username">
            <br>
            <br>
            Password  : <input type="password" name="password" value="{{password}}">
            <br>
            <br>
            <button (click)="handleLogin()" class="btn btn-success">Login</button>
            </div>
            </div>
    ]
->  Finally, go to the 'welcome.component.html' file, and modify it as shown below
    [
        <h1>Welcome!</h1>
        <div class="container">
        Welcome {{name}}. You Can Manage Your Todos <a routerLink="/todos">Here</a>
        </div>
    ]
---------------------------------------------------------------------------------------------------

->  As of now, if we click on home or login in the webpage output, the entire page is getting   
    refreshed, we dont want that to happen.
->  Go to 'menu.component.html', and replace all 'href's with 'routerLinks' as shown below
    [
            <header>
                <nav class="navbar navbar-expand-md navbar-dark bg-dark">
                    <div><a href="https://www.socialprachar.com" class="navbar-brand">SocialPrachar</a></div>
                    <ul class="navbar-nav">
                        <li><a routerLink="/welcome/ADMIN" class="nav-link">Home</a></li>
                        <li><a routerLink="/todos" class="nav-link">Todos</a></li>
                    </ul>
                    <ul class="navbar-nav navbar-collapse justify-content-end">
                        <li><a routerLink="/login" class="nav-link">Login</a></li>
                        <li><a routerLink="/logout" class="nav-link">Logout</a></li>
                    </ul>
                </nav>
            </header>
    ]
->  Now, you'll notice that we have a single page web application that doesn't reload every time
---------------------------------------------------------------------------------------------------


->  Now, Let's setup more authenticatication by creating an authentication service
->  When we want to create some logic which is common across multiple components, we would create a
    service in angular
->  In cmd, type 'ng generate service service/hardcodedAuthentication'
->  Open the 'hardcoded-authentication.service.ts' file, and add an authentication method as shown
    below
    [
          authenticate(username: any, password: any){
            if(username==="ADMIN" && password ==="ADMIN"){
            return true;
            }
            return false;
            }
    ]
->  In the 'login.component.ts' file, we need to add the hardcodedAuthenticationService as shown 
    below in the constructor 
    [
        private hardcodedAuthenticationService: HardcodedAuthenticationService
    ]
->  After injecting the hardcodedAuthenticationService, we will use it for authenticating the login 
    component as shown below again in the 'login.component.ts' file
    [
        if(this.hardcodedAuthenticationService.authenticate(this.username, this.password)){
    ]
    With this we have successfully moved the authentication logic from login component to hardcodedAuthenticationService 
->  We can now check if the authentication is working  or not in the browser by logging in
->  Let's start using session storage to store user authentication token 
->  Go to 'hardcoded-authentication.service.ts' file, and add a session storage as shown below
    [
        sessionStorage.setItem('authenticateUser', username)
    ]
->  Go To the browser, login, go to google inspect tool, go to storage, expand session storage, 
    we will find a url, if we click on it, we can find a value is stored in the local storage
->  In the 'hardcoded-authentication.service.ts' file, let's create a simple method, as shown 
    [
        isUserLoggedIn(){
        let user = sessionStorage.getItem('authenticateUser')
        return !(user === null)
        }
    ]
----------------------------------------------------------------------------------------------------


->  Enabling Links based on user authentication token
->  Let's go to 'menu.component.ts' and add the athentication service as shown below
    [
        import { Component, OnInit } from '@angular/core';
        import { HardcodedAuthenticationService } from './../service/hardcoded-authentication.service'
        @Component({
        selector: 'app-menu',
        templateUrl: './menu.component.html',
        styleUrls: ['./menu.component.css']
        })
        export class MenuComponent implements OnInit {
        isUserLoggedIn: boolean = false;

        constructor(private hardcodedAuthenticationService
            : HardcodedAuthenticationService) { }

        ngOnInit(): void {
            this.isUserLoggedIn = this.hardcodedAuthenticationService.isUserLoggedIn();
        }

        }
    ]
->  Now, Let's use the 'isUserLoggedIn' component property in the view
->  Go to 'menu.component.html', and modigy it a as shown below
    [
        <header>
            <nav class="navbar navbar-expand-md navbar-dark bg-dark">
                <div><a href="https://www.socialprachar.com" class="navbar-brand">SocialPrachar</a></div>
                <ul class="navbar-nav">
                    <li><a *ngIf="hardcodedAuthenticationService.isUserLoggedIn()" routerLink="/welcome/ADMIN" class="nav-link">Home</a></li>
                    <li><a *ngIf="hardcodedAuthenticationService.isUserLoggedIn()" routerLink="/todos" class="nav-link">Todos</a></li>
                </ul>
                <ul class="navbar-nav navbar-collapse justify-content-end">
                    <li><a *ngIf="!hardcodedAuthenticationService.isUserLoggedIn()" routerLink="/login" class="nav-link">Login</a></li>
                    <li><a *ngIf="hardcodedAuthenticationService.isUserLoggedIn()" routerLink="/logout" class="nav-link">Logout</a></li>
                </ul>
            </nav>
        </header>
    ]
->  Now, go to 'menu.component.ts' file, and change private to public as shown below
    [
            constructor(public hardcodedAuthenticationService
        : HardcodedAuthenticationService) { }
    ]
->  Also, in the same 'menu.component.ts' file, let's comment out things we did'nt use
    [
            export class MenuComponent implements OnInit {
            // isUserLoggedIn: boolean = false;

            constructor(public hardcodedAuthenticationService
                : HardcodedAuthenticationService) { }

            ngOnInit(): void {
                // this.isUserLoggedIn = this.hardcodedAuthenticationService.isUserLoggedIn();
            }

            }
    ]
->  In this step, we enabled the menu items based on whether user is logged in or not 
---------------------------------------------------------------------------------------------------


->  Implementing logout to remove user authentication token
->  So, Let's create a logout component
->  In cmd, type 'ng g c logout'
->  Let's add routing for the logout component, go to 'app-routing.module.ts' file, and add 
    the below line od code as shown below
    [
        { path:'logout', component:LogoutComponent},
    ]
->  Now, go to 'logout.component.html', and modify it as shown below
    [
        <h1>You are logged out</h1>
        <div class="container">
            Thank you for visiting your todo's app
        </div>
    ]
->  Now, go to 'hardcoded-authentication.service.ts' file, and let's create a logout method as
    shown below
    [
        logout(){
        sessionStorage.removeItem('authenticateUser')
        }  
    ]
->  Now, go to 'logout.component.ts' file,  and inject the hardcodedAuthenticationService as 
    shown below
    [
        export class LogoutComponent implements OnInit {

        constructor( public hardcodedAuthenticationService: HardcodedAuthenticationService) { }

        ngOnInit(): void {
            this.hardcodedAuthenticationService.logout();
        }

        }
    ]
->  Go to the browser and check the functionality of logout component
---------------------------------------------------------------------------------------------------


->  Securing components using route guards
->  we are able to see all the components, without logging in
->  So, Let's make the components secure by making sure that you can only view the components
    only if you are logged in
->  Go to 'app-routing.module.ts' file, and let's add a routegaurd service with canactivate
->  In cmd, type 'ng g s service/routeGaurd'
->  Go to that 'route-gaurd.service.ts' file, and modify it as shown below
    [
        import { Injectable } from '@angular/core';
        import { CanActivate,ActivatedRouteSnapshot,RouterStateSnapshot } from '@angular/router';
        import { HardcodedAuthenticationService } from './hardcoded-authentication.service';

        @Injectable({
        providedIn: 'root'
        })
        export class RouteGaurdService implements CanActivate {

        constructor(public hardcodedAuthenticationService: HardcodedAuthenticationService) {

        }

        canActivate(route: ActivatedRouteSnapshot, state: RouterStateSnapshot){
            if(this.hardcodedAuthenticationService.isUserLoggedIn())
            return true;
            return false;  

        }
        }

    ]
-> In this step, we quickly activated the route gaurd service
---------------------------------------------------------------------------------------------------

->  Now that we have set up our route-gaurd service, let's start using it
->  Go to the 'app-routing.module.ts' file and add the attribute 'CanActivate' as shown below
    [
        import { RouteGaurdService } from './service/route-gaurd.service';

          { path:'welcome/:name', component: WelcomeComponent, canActivate:[RouteGaurdService]},
          { path:'todos', component: ListTodosComponent, canActivate:[RouteGaurdService]},
          { path:'logout', component:LogoutComponent, canActivate:[RouteGaurdService]},
    ]
->  You will get an empty page when you try to access components without loggin in or after logging 
    out of the app
->  Now, instead of returning an empty page, let's redirect to login page in the above case
->  Go to 'route-gaurd.service.ts' file, and before retuning flase let's reroute the user to the
    login page
    [
        export class RouteGaurdService implements CanActivate {

        constructor(
            public hardcodedAuthenticationService: HardcodedAuthenticationService,
            public router:Router
            ) {

        }

        canActivate(route: ActivatedRouteSnapshot, state: RouterStateSnapshot){
            if(this.hardcodedAuthenticationService.isUserLoggedIn())
            return true;

            this.router.navigate(['login']);
            return false;  

        }
        }
    ]
->  Now, we can see in the output that before login or after logout we dont see a blank screen whenever we try to access components of our app rather we will be redirected to login page.

-> THE END
-->