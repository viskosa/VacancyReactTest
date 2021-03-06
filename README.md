# ReactJS Junior developer Vacancy test #


![geeks](https://github.com/geeksteam/VacancyFrontendTest/raw/master/logo-git.png)
<img src="https://upload.wikimedia.org/wikipedia/commons/4/42/Love_Heart_SVG.svg" width="80">
<img src="https://react-mdl.github.io/react-mdl/react.svg" width="250">

We are looking for a junior `React and Mobx` reactive :rocket: developer.

If you have any questions, welcome to our Gitter Chat 
[![https://gitter.im/geeksteam/Vacancies](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/geeksteam/Vacancies)

#### Please send your CV and link to your github repo with resolved test challenge to gitter or vacancy @ geeks.team. ####

## Small and simple challenge to test your HTML, CSS, React basic skills: ##

Asume we have up and running backend server wich listen for `POST` requests in `JSON` format (default React post format), at `/login` URL and reply to our frontend in `JSON` format too.

We suggest to use `mockserver-grunt` or ther mock server for testing your app: https://www.npmjs.com/package/mockserver-grunt. But you can test as you wish.

### Create Login form
Create Login form view using Bootstrap:

![alt tag](https://raw.githubusercontent.com/geeksteam/VacancyFrontendTest/master/sketch/LoginPage.png)

Our backend server have several reponses to your React frontend:
```
- /login
 |- 1. "Login Denied"
 |- 2. "Success"
```

### 1. Login Denied.
We `POST` request to `/login` with incorrect (`foo,bar` in our case) `Username` and `Password` from our Login form.
Our backend server respond:
```
{"Auth":"Denied"}
```
So we are denied to enter the app. Make `red` Login field of the form:

![alt](https://raw.githubusercontent.com/geeksteam/VcFrontendTest/master/sketch/LoginFailed.png)


If you use mock server to emulate backend, there is mock for testing and developing:

```
mockServerClient("localhost", 8080).mockAnyResponse({
    "httpRequest": {
        "method": "POST",
        "path": "/login",
        "body": {
            "type": "JSON",
            "value": JSON.stringify({ Username: "foo", Password: "bar" }),
            "matchType": "STRICT"
        }
    },
    "httpResponse": {
        "statusCode": 200,
        "headers": [
            {
                "name": "Content-Type",
                "values": ["application/json; charset=utf-8"]
            },
            {
                "name": "Cache-Control",
                "values": ["public, max-age=86400"]
            }
        ],
        "body": JSON.stringify({ Auth: "Denied" }),
        "delay": {
            "timeUnit": "SECONDS",
            "value": 1
        }
    }
});
```

### 2. Auth succcess
We `POST` request to `/login` with correct (User:Password in our case) `Username` and `Password` from our Login form.
Out backend server respond:
```
{
	"Auth":"Logged",
	"Language":"EN"
}
```

We are succesfull logged to your Application, and you must show this to the user:

![alt](https://raw.githubusercontent.com/geeksteam/VcFrontendTest/master/sketch/Success.png)

If you use mock server to emulate backend, there is mock for testing and developing:
```
mockServerClient("localhost", 8080).mockAnyResponse({
    "httpRequest": {
        "method": "POST",
        "path": "/login",
        "body": {
            "type": "JSON",
            "value": JSON.stringify({ Username: "User", Password: "Password" }),
            "matchType": "STRICT"
        }
    },
    "httpResponse": {
        "statusCode": 200,
        "headers": [
            {
                "name": "Content-Type",
                "values": ["application/json; charset=utf-8"]
            },
            {
                "name": "Cache-Control",
                "values": ["public, max-age=86400"]
            }
        ],
        "body": JSON.stringify({ Auth: "Logged", Language: "EN" }),
        "delay": {
            "timeUnit": "SECONDS",
            "value": 1
        }
    }
});
```

### Project manifest (optional but can make your life easy):
- [x] Read our best practices and code rules for React and Mobx: https://github.com/geeksteam/CodeRules#react,

- [x] Bootstrap React from react-create-app: https://github.com/facebookincubator/create-react-app,

- [x] Using MobX would be + in your karma,
- [x] Activate decorators for MobX and react-create-app: https://github.com/geeksteam/CodeRules/blob/master/React/Readme.md#mobx

- [x] Use `CamelCase` names,
- [x] Use feauture-based directory structure.

If any questions about task, join the chat at our Gitter [![https://gitter.im/geeksteam/Vacancies](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/geeksteam/Vacancies) or mailto _vacancy @ geeks.team_.
