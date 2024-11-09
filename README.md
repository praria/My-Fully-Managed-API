# My-Fully-Managed-API

# Set up the development environment

# Part I: Get Earthquake Data
- download or generate data

# Part II: Build the API Using Amplify

1. Initialize Amplify Project

sudo npm install -g @aws-amplify/cli
sudo amplify configure
sudo amplify init

2. Add the API

amplify add api 
    - add REST API and configure it to 
    - create a new Lambda function each CRUD operation (Get, Post, Update, Destroy
    - set up DynamoDB, define a table schema for storing earthquake data
amplify push 

2. Create a Coginito User Pool

3. Set up App Client to interact with the cognito user pool (eg user sign in)

4. Add authentication to the amplify project (integrate cognito into backend)

amplify add auth
amplify push (deploy authentication service)


5. User registration and authentication
- registration endpoint: Create a Lambda function or expose an API that registers users using AWS Cognito SDK.
- sign-in endpoint: Create a Lambda function or expose an API that registers users using AWS Cognito SDK.

6. Cognito pool authorizer in API Gateway to handle authentication and authorize request to the API



Sudo amplify status

REST API endpoint: https://3bhpn23gyj.execute-api.us-east-1.amazonaws.com/dev/earthquakes










