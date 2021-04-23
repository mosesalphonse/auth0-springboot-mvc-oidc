# auth0-springboot-mvc-oidc

## This POC demontrates the below:
```
- Setup Auth0 environemnt including MFA
- Adding authentication with Auth0 to a Spring Boot 2 MVC application
- Accessing profile information of the authenticated user
- Only allowing authenticated users to access restricted resources(/profile) 
- Verify and test it
```


### Setup Auth0 environemnt:
```
* Singin/Signup into auth0
* Create Application of type 'Regular Web Application'
    * Go to Settings of the above application created in the above step
    * Update  'Allowed Callback URLs' value as 'http://localhost:8080/login/oauth2/code/auth0' because my Client application will be running in localhost port 8080.
    * Update 'Allowed Logout URLs' as 'http://localhost:8080/' and save the changes
 Note: refer 'Client ID', 'Client Secret' and 'Domain' in your Spring Boot MVC app to integrate with Auth0
 
* If you want to enable 'Multi-factor Authentication', please follow the below steps
    *  Go to 'Security'->'Multi-factor Auth' section from the left pane
    *  Enable 'One-time Password'
    *  Select 'Always' radio button on the buttom and save the changes
   
 * If you want to enable Social Logins like google, follow the below steps
    *  Go to 'Authentication'->'Social' section from the left pane
    *  Create new Social Connection
    
    Note: By default, Auth0 will use their own client ID for the social logins. This can be only used in sandbox. for Production go to the respective social identity provider      create your credentials(ClientID and Client secret) update it here.
```

### Integrate Auth0 with Spring Boot:
```
* git clone https://github.com/mosesalphonse/auth0-springboot-mvc-oidc.git
* cd auth0-springboot-mvc-oidc
* Edit application.yml and update 'Client ID', 'Client Secret', 'Domain' (Make sure your application runs on port 8080)
* mvn compile spring-boot:run
```

### Verify:
```
* http://localhost:8080/profile
* Use either social login/internal users. (based on the Auth0 subscription, you may be allowed to register the user as well)
* Allow this app to access your profile. then you can able to access your /profile restricted resource
* http://localhost:8080/logout  (/logout resource will invalidate the login session)

* In case if you enabled the MFA, after login, it will ask you to use any authenticator app to register by scaning the QR code. 
* You may use the 6 digit OTP as an second level of authentication

Note: Based on your subscription, you may allow to access the MFA feature.

```
