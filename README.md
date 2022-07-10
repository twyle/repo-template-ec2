# A Template For Creating Repositories

> This flask application enables enables an admin to register then authorizes them to create new users.

[![security: bandit][bandit-image]][bandit-url]
[![Imports: isort][isort-image]][isort-url]
[![made-with-python](https://img.shields.io/badge/Made%20with-Python-1f425f.svg)](https://www.python.org/)
[![GitHub license](https://img.shields.io/github/license/Naereen/StrapDown.js.svg)](https://github.com/Naereen/StrapDown.js/blob/master/LICENSE)
![Medium](https://img.shields.io/badge/Medium-12100E?style=flat&logo=medium&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/github%20actions-%232671E5.svg?style=flat&logo=githubactions&logoColor=white)
![Flask](https://img.shields.io/badge/flask-%23000.svg?style=flat&logo=flask&logoColor=white)
![Visual Studio Code](https://img.shields.io/badge/Visual%20Studio%20Code-0078d7.svg?style=flat&logo=visual-studio-code&logoColor=white)
![Ubuntu](https://img.shields.io/badge/Ubuntu-E95420?style=flat&logo=ubuntu&logoColor=white)
![Gunicorn](https://img.shields.io/badge/gunicorn-%298729.svg?style=flat&logo=gunicorn&logoColor=white)


![](resources/images/header.jpg)

## Project Overview

This is a User managementsystem that enables an admin user to register and then authorizes them to create other non-admin users. The admin registers using a unique email address and user then has to confirm their account via a link sent to their email. Once their account is confirmed,they can then log into the application, upon which they receive an authorization token. Using this token, the admin can then create other non-admin users.

## Working

It's pretty easy to use the application. On the home page (http://localhost:5000/apidocs):

 1. Register as an admin, using a unique email address, unique name and a password. 
 2. Head over to the email address that you provided and click on the confirmation link.
 3. At the application home page, log in with the email address and password, to get back a token.
 4. Use the token, to authorize the user.
 5. Make requests to the user routes to create, update, view or delete a user.

Here's a video showing how to use the application:

<video src="https://github.com/twyle/repo-template/blob/development/resources/videos/header.mkv"></video>

## Features

This application has several features including:
 1. Deployed to an AWS Instance using a custom domain language.
 2. Versioned using Git and Hosted on GitHub.
 3. Auto-deployed to AWS using GitHub Actions.
 4. Uses gunicorn as the application server and nginx as the proxy.
 5. Uses AWS SES to send emails.
 6. Uses AWS Opensearch and Firehose for logging as filebeats.
 7. Uses AWS Secrets manager to manage the application secrets and AWS KMS for key management.
 8. Uses PostgreSQL for data storage.
 9. Uses JSON Web Tokens to authorize users.
 10. Uses AWS Route53 to route traffic to the application.
 11. Built using flask, flask-mail, flask-jwt
 12. Documented using swagger

## Application Structure

```
project
│   README.md
│   file001.txt    
│
└───folder1
│   │   file011.txt
│   │   file012.txt
│   │
│   └───subfolder1
│       │   file111.txt
│       │   file112.txt
│       │   ...
│   
└───folder2
    │   file021.txt
    │   file022.txt
```

* **Folder** </br>
  *Folder content description*

* **Folder** </br>
  *Folder content description*

* **Folder** </br>
  *Folder content description*

* **Folder** </br>
  *Folder content description*
  
* **Folder** </br>
  *Folder content description*

* **Folder** </br>
  *Folder content description*

* **Folder** </br>
  *Folder content description*

* **Folder** </br>
  *Folder content description*

## Local Setup

Here is how to set up the application locally:

  1. Clone the application repo:
  2. Navigate into the cloned repo
  3. Create a Virtual environment
  4. Activate the virtual environmnet
  5. Install the project dependancies
  6. Create the environment variables
  7. Start the database containers
  8. Start the application

## Development

 #### 1. Application Design
 
  1. **Database**
  
  2. **Routes**
  
  3. **Logging**
  
  4. **Security**
  
 #### 2. Project Management
 
   1. **Coding standards** </br>
      The application had to adhere to the following coding standards:
      1. Variable names
      2. Function names
      3. Test driven developmnt
      4. CI/CD pipeline
      5. Commit messages
      6. Releases
 
 #### 3. Development Workflow

## Deployment

The deployemt process for this application can be devided into two groups:

 * Initial Deployment
 * Incremental deployment

The initial deployment describes the first dployment to the AWS EC2 instance. The process involves the following steps:

 1. Setting up an AWS EC2 instance
 2. Clong the project
 3. Setting up the application
 4. Creating a service
 5. Setting up the application domain
 6. Setting up the application server with the domain
 7. Launching the application

The incremental deployment describes the process of deploying new changes to the already deployed application. It involves the following steps:

 1. Tunelling into the deployment server
 2. Pulling the latest changes
 3. Running database migrations
 4. Restarting the application

## Releases

## Contribution

1. Fork it https://github.com/twyle/flask-linode-deployment/fork
2. Create your feature branch (`git checkout -b feature/fooBar`)
3. Commit your changes (`git commit -am 'Add some fooBar'`)
4. Push to the branch (`git push origin feature/fooBar`)
5. Create a new Pull Request

## Developer

Lyle Okoth – [@lylethedesigner](https://twitter.com/lylethedesigner) on twitter </br>

[lyle okoth](https://medium.com/@lyle-okoth) on medium </br> 

My email is lyceokoth@gmail.com </br>

Here is my [GitHub Profile](https://github.com/twyle/)

You can also find me on [LinkedIN](https://www.linkedin.com/feed/)

## License

Distributed under the MIT license. See ``LICENSE`` for more information.


[bandit-image]: https://img.shields.io/badge/security-bandit-yellow.svg
[bandit-url]: https://github.com/PyCQA/bandit

[isort-image]: https://img.shields.io/badge/%20imports-isort-%231674b1?style=flat&labelColor=ef8336
[isort-url]: https://pycqa.github.io/isort/
