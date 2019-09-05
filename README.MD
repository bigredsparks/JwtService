## JwtService
### Overview
Simple implementation of ASP.NET web service with Java Web Token (JWT) authentication.

This was created using blog: https://jasonwatmore.com/post/2018/08/14/aspnet-core-21-jwt-authentication-tutorial-with-example-api#startup-cs


### Prerequisites
- Microsoft .NET Core 2.2 SDK

### Helpful Tools:
- Postman
- Curl

### Build
To build the project:

```
dotnet restore
dotnet build
```
### Run
To run the project:

```
dotnet run
```

### API

#### Authentication
To login or authenticate, use the following CURL command:

```
curl -XPOST -H "Content-type: application/json" -d '{
	"Id" : 1,
	"FirstName" : "Test",
	"LastName" : "User",
	"UserName" : "test",
	"Password" : "test"
}' 'http://localhost:5000/users/authenticate'
```

  This will return the bearer token which can be used with other APIs.

#### Get Users
To get users, use the following CURL command:

```
curl -XGET -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1bmlxdWVfbmFtZSI6IjEiLCJuYmYiOjE1Njc2OTcyMDcsImV4cCI6MTU2ODMwMjAwNywiaWF0IjoxNTY3Njk3MjA3fQ.4VqKscNKeZBraD0kzUAScP-6IXaGVK7npFAy6QTOc9Y' -H "Content-type: application/json" 'http://localhost:5000/users'
```

> Note that the bearer token value will need to be retrieved from the *authenticate* method before this method will work.
