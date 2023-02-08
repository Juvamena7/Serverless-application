# Serverless-application
Successfully complete this lab by achieving the following learning objectives:

# Create the Lambda Functions

  You will need to create three Lambda functions for use in the Step Function using the resouces provided in the GitHub Repo.

Create an email reminder function called email using the contents of email_reminder.py. 
This function will require the use of a Simple Email Service (SES) verified email, so you will need to create and verify a new email identity in SES.
Create an SMS reminder function called sms using the contents of sms_reminder.py.
Create a function called api_handler using the contents of api_handler.py. 
Please note that this function will require a Step Function ARN which will be created in the next objective.
For all functions, you will need to utilize Python 3.8 and the LambdaRuntimeRole.

# Create a Step Function State Machine

Create a Step Function State Machine using the option to Write your workflow in code, and utilize the code provided in the step-functions-template.json file. 
This code is partially completed and will need to be updated to include your Email Reminder ARN and SMS Reminder ARN from the Lambda functions you created in the previous objective. Once the Step Function has been deployed, update your api_handler Lambda function to include the ARN for your Step Function.

# Create the API Gateway

Create an API Gateway using REST API with the REST protocol. 
You will need to create a New API called reminders and ensure that you Enable API Gateway CORS. 
Once the API has been created, you will need to create a POST method for /reminders in the us-east-1 region that uses the api_hanlder function that was created earlier and deploy the API Gateway as a New Stage called prod.

# Create and Test the Static S3 Website

Download a local copy of the static_website folder with its contents from the GitHub repo and modify the formlogic.js file to include the Invoke URL from your API Gateway. 
Make sure to keep /reminders at the end of the string. Once the file has been modified, create a web enabled S3 bucket with static website hosting enabled and upload the static_website folder to your S3 bucket. Use the Bucket website endpoint to access and test the functionality of the website by sending an email reminder to your SES verified email and verify you receive the message. Observe the visual workflow of the event in Graph Inspector for MyStateMachine in AWS Step Functions.
