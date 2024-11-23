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
    - create a new Lambda function each CRUD operation (Get, Post, Update, Destroy)
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

REST API endpoint: https://3bhpn23gyj.execute-api.us-east-1.amazonaws.com/dev/earthquakes




TESTING:

1. User Registration

Post request: https://cognito-idp.us-east-1.amazonaws.com/

{
  "ClientId": "3l6p8cvu74adjuq4i4nqsfa8rl",
  "Username": "prakash",
  "Password": "$unny1223",
  "UserAttributes": [
    {
      "Name": "email",
      "Value": "xyz@gmail.com"
    }
  ]
}


2. Confirm UserSignup

Post request: https://cognito-idp.us-east-1.amazonaws.com/

{
  "ClientId": "3l6p8cvu74adjuq4i4nqsfa8rl", 
  "Username": "prakash",  
  "ConfirmationCode": "668660" # code received in email during user registration
}


3. User login

Post request: https://cognito-idp.us-east-1.amazonaws.com/

response: {
    "AuthenticationResult": {
        "AccessToken": "",
        "ExpiresIn": 86400,
        "IdToken": "",
        "RefreshToken": "g",
        "TokenType": "Bearer"
    },
    "ChallengeParameters": {}
}

4. Get All Data

Get request: https://3bhpn23gyj.execute-api.us-east-1.amazonaws.com/dev/earthquakes

Headers: 
Authorization code
Content-Type

5. Get Single Data

Get request: https://3bhpn23gyj.execute-api.us-east-1.amazonaws.com/dev/earthquakes/:id 


6. Post Data:

Post request: https://3bhpn23gyj.execute-api.us-east-1.amazonaws.com/dev/earthquakes

example: 
  {
        "id": "500",
        "date": "10/23/24 03:10",
        "latitude": -23.214387,
        "longitude": -135.410919,
        "magnitude": 6.0,
        "depth": 595.5,
        "region": "Indonesia"
    }


7. Updata Data:
Put request: https://3bhpn23gyj.execute-api.us-east-1.amazonaws.com/dev/earthquakes

example: 
  {
        "id": "500",
        "date": "11/20/24 03:10",
        "latitude": -23.214387,
        "longitude": -135.410919,
        "magnitude": 6.0,
        "depth": 595.5,
        "region": "Indonesia"
    }


8. Delete Signle Data: 

Delete request: https://3bhpn23gyj.execute-api.us-east-1.amazonaws.com/dev/earthquakes/500













