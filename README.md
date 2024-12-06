<!--
title: 'AWS HTTP Endpoint in NodeJS'
description: 'This project demonstrates how to make a HTTP API with Node.js running on AWS Lambda, API Gateway, S3, DynamoDB and CloudFormation using the Serverless Framework.'
layout: Doc
framework: v4
platform: AWS
language: nodeJS
-->

# Serverless Framework Node HTTP API on AWS

This project demonstrates how to make a HTTP API with Node.js running on AWS Lambda, API Gateway, S3, DynamoDB and CloudFormation using the Serverless Framework.

## Usage

### Deployment

In order to deploy the project, you need to run the following command:

```
serverless deploy
```

After running deploy, you should see output similar to:

```
Deploying "serverless-http-api" to stage "dev" (ca-central-1)

✔ Service deployed to stack serverless-http-api-dev (91s)

endpoint: GET - https://xxxxxxxxxx.execute-api.ca-central-1.amazonaws.com/
functions:
  hello: serverless-http-api-dev-hello (1.6 kB)
```

_Note_: In current form, after deployment, your API is public and can be invoked by anyone. For production deployments, you might want to configure an authorizer. For details on how to do that, refer to [HTTP API (API Gateway V2) event docs](https://www.serverless.com/framework/docs/providers/aws/events/http-api).

### Invocation

After successful deployment, you can call the created application via HTTP:

```
curl https://xxxxxxx.execute-api.ca-central-1.amazonaws.com/
```

Which should result in response similar to:

```json
{ "message": "Go Serverless v4! Your function executed successfully!" }
```

### Local development

The easiest way to develop and test your function is to use the `dev` command:

```
serverless dev
```

This will start a local emulator of AWS Lambda and tunnel your requests to and from AWS Lambda, allowing you to interact with your function as if it were running in the cloud.

Now you can invoke the function as before, but this time the function will be executed locally. Now you can develop your function locally, invoke it, and see the results immediately without having to re-deploy.

When you are done developing, don't forget to run `serverless deploy` to deploy the function to the cloud.
