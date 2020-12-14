# LogMe
A web based app to provide login-as-a-service.

## Background
While making multi-user full-stack apps, I realised that, in all projects authentication is a requisite.<br>
So to make the job of developers easier, LogMe takes the responsibility of providing authorization to the user, from the developer, thereby scaling their from single-user system to multiple user with ease.

## Features
- User-End Application
   - Login for existing user
   - Register for new user
   - Forgot Password for changing it
- Developer-End Application
  - Build project
  - Deploy
  - Administrator Dashboard

## Use Cases for User-End Application
1. User logs in (default case): Show login page
   1. User logs in with wrong userId and password - Show login Page with link to register and forgot password
2. User wants to register: Show register page
   1. User enters different password: Show register page with password field reset to null.
3. User forgot their password: Send OTP to e-mail, urge user to enter(OTP Page), and direct the user to change password (Change Password)
   1. User gives un-registered e-mail ID: Show forgot password page with comment "Email Is not registered" and link register.
   2. User gives wrong OTP: Show forgot password page with comment "wrong OTP" and link to Resend OTP.
   
## User-end Specification
1. Login page: 
   1. Input- User Id, password
   2. Button- login action, third-party authorisation, register, forgot password
   3. Label- for use case 1.1
2. Register Page:
   1. Input- First Name, Last Name, User Id, Password, Confirm Password
   2. Button- Register, Go back to Login Page
   3. Label- for use case 2.1
3. Forgot Password Page:
   1. Input- email ID
   2. Button- send OTP, go to login
4. Verify OTP Page: 
   1. Input- OTP
   2. Button- confirm, resend OTP
   3. Label- time limit
5. Change Password:
   1. Input- new password, confirm new password
   2. Button- change password
   3. Label- for use case 3.1 and 3.2
6. Success Page
7. Failure Page
8. Error Page

## Dev-end specification
1. Build page: 
   1. Input- Project Name, DB Name
   2. Button- Build
   3. Label- Developer user ID
2. Deploy Page:
   1. Display the iframes of various user-end pages
   2. Display the link of iframes
   3. Display key of DB, DB Name
   4. Display information on integration
3. Dev-Dashboard Page: 
   1. Profile- User Name, User Id, User Password
   2. View Project- Ongoing project
   3. Build Project- link to build page
4. Project Page for each project:
   1. View total user registered, 
   2. Active user based on time(current, day, week, month, 6-month, year ago),
   3. other analytics