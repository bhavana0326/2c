# 2c

**home component
~~home.html
<h2>Welcome to my travel site</h2>
<p>This is some basic information about the our site</p>
<button (click)="navigateToRegister()">Next</button>
<a routerLink="/register">Next</a>
~~home.ts
import { Component } from '@angular/core';
import { Router } from '@angular/router';

@Component({
  selector: 'app-home',
  templateUrl: './home.component.html',
  styleUrls: ['./home.component.css']
})
export class HomeComponent {
  constructor(private router: Router) {}

  navigateToRegister() {
    this.router.navigate(['/register']);
  }
}


**login component
~~login.css


form {
    margin-bottom: 20px;
  }
  
  label {
    display: block;
    margin-bottom: 5px;
  }
  
  input[type="text"],
  input[type="password"] {
    width: 100%;
    padding: 8px;
    margin-bottom: 10px;
    border-radius: 5px;
    border: 1px solid #ccc;
  }
  
  button[type="submit"] {
    padding: 10px 20px;
    background-color: #007bff;
    color: #fff;
    border: none;
    border-radius: 5px;
    cursor: pointer;
  }
  
  button[type="submit"]:hover {
    background-color: #0056b3;
  }
  
  .logged-in-message {
    margin-top: 20px;
  }
  ~~login.html
  <div>
    <h1>Login</h1>
    
    <form (ngSubmit)="onSubmit()">
      <div>
        <label for="username">Username:</label>
        <input type="text" id="username" name="username" [(ngModel)]="username" required>
      </div>
      <div>
        <label for="password">Password:</label>
        <input type="password" id="password" name="password" [(ngModel)]="password" required>
      </div>
      <button type="submit">Login</button>
    </form>
  
    <div *ngIf="submitted">
      <p>Welcome, {{ username }}!</p>
    </div>
  </div>
  ~~login.ts
  

import { Component } from '@angular/core';

@Component({
  selector: 'app-login',
  templateUrl: './login.component.html',
  styleUrls: ['./login.component.css']
})
export class LoginComponent {
  username: string = '';
  password: string = '';
  submitted: boolean = false;

  constructor() { }

  onSubmit() {
    
    this.submitted = true;
  }
}


**profile componant
~~profile.css

form {
    margin-bottom: 20px;
  }
  
  label {
    display: block;
    margin-bottom: 5px;
  }
  
  input[type="text"],
  input[type="email"],
  textarea {
    width: 100%;
    padding: 8px;
    margin-bottom: 10px;
    border-radius: 5px;
    border: 1px solid #ccc;
  }
  
  button[type="submit"] {
    padding: 10px 20px;
    background-color: #007bff;
    color: #fff;
    border: none;
    border-radius: 5px;
    cursor: pointer;
  }
  
  button[type="submit"]:hover {
    background-color: #0056b3;
  }
  
  .profile-info {
    margin-top: 20px;
  }
  
  .profile-info p {
    margin-bottom: 10px;
  }
  ~~profile.html
  <div>
    <h1>User Profile</h1>
    
    <form (ngSubmit)="onSubmit()">
      <div>
        <label for="fullName">Full Name:</label>
        <input type="text" id="fullName" name="fullName" [(ngModel)]="fullName" required>
      </div>
      <div>
        <label for="email">Email:</label>
        <input type="email" id="email" name="email" [(ngModel)]="email" required>
      </div>
      <div>
        <label for="bio">Bio:</label>
        <textarea id="bio" name="bio" [(ngModel)]="bio"></textarea>
      </div>
      <button type="submit">Submit</button>
    </form>
  
~~profile.ts

import { Component } from '@angular/core';

@Component({
  selector: 'app-profile',
  templateUrl: './profile.component.html',
  styleUrls: ['./profile.component.css']
})
export class ProfileComponent {
  fullName: string = '';
  email: string = '';
  bio: string = '';
  submitted: boolean = false;

  constructor() { }

  onSubmit() {
    
    this.submitted = true;
  }
}


**register component
~~register.css

form {
    margin-bottom: 20px;
  }
  
  label {
    display: block;
    margin-bottom: 5px;
  }
  
  input[type="text"],
  input[type="email"],
  input[type="password"] {
    width: 100%;
    padding: 8px;
    margin-bottom: 10px;
    border-radius: 5px;
    border: 1px solid #ccc;
  }
  
  button[type="submit"] {
    padding: 10px 20px;
    background-color: #007bff;
    color: #fff;
    border: none;
    border-radius: 5px;
    cursor: pointer;
  }
  
  button[type="submit"]:hover {
    background-color: #0056b3;
  }

  ~~register.html
  <h2>Register</h2>
<form>
  <label for="firstName">First Name:</label>
  <input type="text" id="firstName" name="firstName" [(ngModel)]="firstName"><br><br>
  <label for="lastName">Last Name:</label>
  <input type="text" id="lastName" name="lastName" [(ngModel)]="lastName"><br><br>
  <label for="password">Password:</label>
  <input type="password" id="password" name="password" [(ngModel)]="password"><br><br>
  <button (click)="reserve()">Reserve</button>
</form>

~~register.ts
import { Component } from '@angular/core';
import { Router } from '@angular/router';

@Component({
  selector: 'app-register',
  templateUrl: './register.component.html',
  styleUrls: ['./register.component.css']
})
export class RegisterComponent {
  firstName: string = '';
  lastName: string = '';
  password: string = '';

  constructor(private router: Router) {}

  reserve() {
    
    this.router.navigate(['/profile']);
  }
}

***app.component.html
<header>
  <h1>Welcome to My Angular App!</h1>
  <p>This is a demo Angular application.</p>
</header>

<nav>
  <ul>
    <li><a routerLink="/">Home</a></li>
    <li><a routerLink="/login">Login</a></li>
    <li><a routerLink="/register">Register</a></li>
    <li><a routerLink="/profile">Profile</a></li>
  </ul>
</nav>

<router-outlet></router-outlet>

<footer>
  <p>&copy; 2024 My Angular App</p>
</footer>
<h1>My Angular Project</h1>
<nav>
  <a routerLink="/">Home</a>
  <a routerLink="/register">Register</a>
  <a routerLink="/profile">Profile</a>
  <a routerLink="/login">Login</a>
</nav>
<router-outlet></router-outlet>



***app.component.ts
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  title = 'My Angular App';
}

***app-routing.module.ts
import { NgModule } from '@angular/core';
import { RouterModule, Routes } from '@angular/router';
import { HomeComponent } from './home/home.component';
import { LoginComponent } from './login/login.component';
import { ProfileComponent } from './profile/profile.component';
import { RegisterComponent } from './register/register.component';

const routes: Routes = [
  { path: '', component: HomeComponent },
  { path: 'register', component: RegisterComponent },
  { path: 'profile', component: ProfileComponent },
  { path: 'login', component: LoginComponent },
  { path: '**', redirectTo: '' } 
];

@NgModule({
  imports: [RouterModule.forRoot(routes)],
  exports: [RouterModule]
})
export class AppRoutingModule { }
