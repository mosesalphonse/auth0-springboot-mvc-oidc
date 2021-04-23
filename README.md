# auth0-springboot-mvc-oidc

## This POC demontrates the below:
```
- Setup Auth0 environemnt including MFA
- Adding authentication with Auth0 to a Spring Boot 2 MVC application
- Accessing profile information of the authenticated user
- Only allowing authenticated users to access restricted resources(/profile) 
- Verify it
```


### Setup Auth0 environemnt:
```
* Singin/Signup into auth0
* Create Application of type 'Regular Web Application'
    * Go to Settings of the above application created in the above step
    * Update  'Allowed Callback URLs' value as 'http://localhost:8080/login/oauth2/code/auth0' because my Client application will be running in localhost port 8080.
    * Update 'Allowed Logout URLs' as 'http://localhost:8080/' and save the changes
* If you want to enable 'Multi-factor Authentication', please follow the below steps
    *  Go to 'Security'->'Multi-factor Auth' section from the left pane
    *  Enable 'One-time Password'
    *  Select 'Always' radio button on the buttom and save the changes
    *  
```
