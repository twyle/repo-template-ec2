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

## Structure

## Local Setup

## Development

 #### 1. Application Design
 
  1. **Database**
  
  2. **Routes**
  
  3. **Logging**
  
  4. **Security**
  
 #### 2. Project Management
 
 #### 3. Development Workflow

## Deployment

## Releases

## Contribution

## Developer

## License


[bandit-image]: https://img.shields.io/badge/security-bandit-yellow.svg
[bandit-url]: https://github.com/PyCQA/bandit

[isort-image]: https://img.shields.io/badge/%20imports-isort-%231674b1?style=flat&labelColor=ef8336
[isort-url]: https://pycqa.github.io/isort/
