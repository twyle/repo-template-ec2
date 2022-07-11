# A Template For Creating Repositories

> This flask application enables enables an admin to register then authorizes them to create new users.

<p align="center">
  <img title="Bandit badge" alt="Bandit badge" src="https://github.com/twyle/flask-ec2-deployment/actions/workflows/feature-development-workflow.yml/badge.svg" />
  <img title="Bandit badge" alt="Bandit badge" src="https://github.com/twyle/flask-ec2-deployment/actions/workflows/development-workflow.yml/badge.svg" />
  <img title="Bandit badge" alt="Bandit badge" src="https://img.shields.io/badge/security-bandit-yellow.svg" />
  <img title="Bandit badge" alt="Bandit badge" src="https://img.shields.io/badge/%20imports-isort-%231674b1?style=flat&labelColor=ef8336" />
  <img title="Bandit badge" alt="Bandit badge" src="https://img.shields.io/badge/Made%20with- Python-1f425f.svg" />
  <img title="Bandit badge" alt="Bandit badge" src="https://img.shields.io/github/license/Naereen/StrapDown.js.svg" />
  <img title="Bandit badge" alt="Bandit badge" src="https://img.shields.io/badge/Medium-12100E?style=flat&logo=medium&logoColor=white" />
  <img title="Bandit badge" alt="Bandit badge" src="https://img.shields.io/badge/github%20actions-%232671E5.svg?style=flat&logo=githubactions&logoColor=white" />
  <img title="Bandit badge" alt="Bandit badge" src="https://img.shields.io/badge/flask-%23000.svg?style=flat&logo=flask&logoColor=white" />
  <img title="Bandit badge" alt="Bandit badge" src="https://img.shields.io/badge/Visual%20Studio%20Code-0078d7.svg?style=flat&logo=visual-studio-code&logoColor=white" />
  <img title="Bandit badge" alt="Bandit badge" src="https://img.shields.io/badge/Ubuntu-E95420?style=flat&logo=ubuntu&logoColor=white" />
  <img title="Bandit badge" alt="Bandit badge" src="https://img.shields.io/badge/gunicorn-%298729.svg?style=flat&logo=gunicorn&logoColor=white" />
</p>

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

![](resources/videos/header.gif)

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

```sh
repo-template/
│   
└───.github/
│     │   
│     └───workflows/ 
|             |
|             └───feature-development-workflow.yml
|             |
|             └───development-workflow.yml
|             |
|             └───staging-workflow.yml
|             |
|             └───release-workflow.yml
|             |
|             └───production-workflow.yml
│   
└───resources/       
│     |   
│     └───images/  
│     |     |
|     |     └───header.jpg
|     └───videos/
|           |
|           └───header.gif
|
└───services/       
│     |   
│     └───database/  
│     |     |
|     |     └───.env
|     |     |
|     |     └───database-compose.yml
|     |
|     └───web/
|           |
|           └───api/
|           |    |
|           |    └───blueprints/
|           |    |
|           |    └───config
|           |
|           └───tests/
|           |
|           └───.env
|           |
|           └───Dockerfile.dev
|           |
|           └───Dockerfile.prod
|           |
|           └───manage.py
|           |
|           └───requirements.txt
|
└───.gitignore
|
└───.pre-commit-config.yaml
|
└───.pylintrc
|
└───docker-compose.yml
|
└───LICENSE
|
└───Makefile
|
└───pytest.ini
|
└───README.md
|
└───requirements-dev.txt
|
└───setup.cfg
```

* **repo-template/.github/workflows** </br>
  *Holds the GitHub Action workflow files.*

* **repo-template/resources** </br>
  *Holds the resources used to describe this project.*

* **repo-template/services/database** </br>
  *Holds the database compose file and the database environment variables.*

* **repo-template/services/web** </br>
  *Holds the web application.*
  
* **repo-template/services/web/api** </br>
  *Holds the api code*

* **repo-template/services/web/api/config** </br>
  *Holds the application configuration.*

* **repo-template/services/web/api/blueprints** </br>
  *Holds the flask blueprints.*

* **repo-template/services/web/api/blueprints/default** </br>
  *Holds the default blueprint.*

* **repo-template/services/web/tests** </br>
  *Holds the api tests.*

## Local Setup

Here is how to set up the application locally:

  1. Clone the application repo:</br>
   
      ```sh
      git clone https://github.com/twyle/repo-template.git
      ```

  2. Navigate into the cloned repo:
   
      ```sh
      cd repo-template
      ```

  3. Create a Virtual environment:
   
      ```sh
      python3 -m venv venv
      ```
   
  4. Activate the virtual environmnet:
   
      ```sh
      source venv/bin/activate
      ```

  5. Install the project dependancies:
   
      ```sh
      make update # update the package manager 
      make install-dev  # install the development requirements
      make install  # install the runtime requirements
      make pre-commit # initialize pre-commit
      ```

  6. Create the environment variables:
   
      ```sh
      cd services/web
      touch .env
      ```

      Then paste the following into the file:

      ```sh
        FLASK_APP=api/__init__.py
        FLASK_ENV=development
        SECRET_KEY=supersecretkey
        POSTGRES_HOST=<YOUR-IP-ADDRESS>
        POSTGRES_DB=lyle
        POSTGRES_PORT=5432
        POSTGRES_USER=postgres
        POSTGRES_PASSWORD=lyle
        MAIL_HOST=<YOUR-MAIL-HOST>
        MAIL_PORT=<YOUR-MAIL-PORT>
        MAIL_USERNAME=<YOUR-USER-NAME>
        MAIL_PASSWORD=<YOUR-PASSWORD>
        FIREHOSE_DELIVERY_STREAM=flask-logging-firehose-stream
      ```

      Then create the database secrets:

      ```sh
      cd services/database
      touch .env
      ```

      Then paste the following into the file:

      ```sh
        POSTGRES_DB=lyle
        POSTGRES_PORT=5432
        POSTGRES_USER=postgres
        POSTGRES_PASSWORD=lyle
      ```

  7. Start the database containers:
   
      ```sh
      make start-db-containers
      ```

  8. Start the application:
   
      ```sh
      make run
      ```


## Development

 #### 1. Application Design
 
  1. **Database**
   
      The database was designed to store the Admin details as well as the users details. These are stored in the tables admin and users.
  
  2. **Routes**
   
      Here are the application routes:

      | Route       | Method      | Description      |
      | ----------- | ----------- |----------------- |
      | '/'         | GET         | Get the home page |
        
  3. **Logging**
   
      The application logs to the standard output as well as to AWS OpnSearch using AWS Firehose. Both logging options use custom loggers.
  
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
