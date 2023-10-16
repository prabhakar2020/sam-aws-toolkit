# AWS Lambda on local machine 
### Create, Build and Invoke locally

The AWS Toolkit for AWS SAM (Serverless Application Model) is a set of tools and extensions that help developers create, build and deploy serverless applications on AWS. AWS SAM is an open-source framework for building serverless applications, making it easier to define, test, and deploy your serverless infrastructure as code.

Pre-requisites for SAM
1. Install [AWS SAM CLI](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/install-sam-cli.html)
2. AWS SAM CLI uses Docker to run and test Lambda functions locally. Ensure that Docker is installed and running on your system. - [Install Docker](https://docs.docker.com/engine/install/)

The AWS Toolkit for AWS SAM typically includes the following components and features:

1. **AWS SAM CLI**: The AWS SAM Command Line Interface (CLI) is a tool that provides a local development environment for building, testing, and deploying serverless applications defined using the AWS SAM specification. It enables you to test your serverless functions locally before deploying them to AWS.

2. **AWS SAM Visual Studio Code Extension**: This extension for Visual Studio Code (VS Code) offers an integrated development experience for building serverless applications with AWS SAM. 

3. **AWS SAM IntelliJ IDEA Plugin**: Similar to the VS Code extension, this is a plugin for JetBrains' IntelliJ IDEA IDE, which supports AWS SAM application development.

4. **AWS Toolkit for AWS SAM in AWS Cloud9**: AWS Cloud9 is a cloud-based integrated development environment. The toolkit extends Cloud9 with AWS SAM support, making it easy to develop serverless applications in a collaborative, browser-based environment.

## Steps to work with SAM to create, build and invoke lambda function on local machine

### 1. Install Visual Studio extension

![image](https://github.com/prabhakar2020/sam-aws-toolkit/assets/7165155/1fbb444b-34fe-468b-a082-631262365d30)

### 2. Go to AWS Explorer tab by clicking "AWS" icon
![image](https://github.com/prabhakar2020/sam-aws-toolkit/assets/7165155/cf410621-67a5-4aeb-9e4b-64446908318a)

### 3. Create lambda function from scratch
3.1 Press Cntrl + Shift + P, it will open a Command windown and choose "AWS: Create Lambda SAM Application"
![image](https://github.com/prabhakar2020/sam-aws-toolkit/assets/7165155/1835a65b-f118-4aec-a3ce-0e2a688ca69f)
3.2 Select run-time environment (programming language)
![image](https://github.com/prabhakar2020/sam-aws-toolkit/assets/7165155/8286b44a-50e5-4e79-9854-4a357df4cd68)
3.3 Select SAM application template
![image](https://github.com/prabhakar2020/sam-aws-toolkit/assets/7165155/39ea3ec3-871f-44cc-86f4-c82897fa30d2)
3.4 Select folder for your SAM application
![image](https://github.com/prabhakar2020/sam-aws-toolkit/assets/7165155/aeb8ab1f-b7fb-41e9-b308-0304c0f918c0)
3.5 Enter your application name
![image](https://github.com/prabhakar2020/sam-aws-toolkit/assets/7165155/b9de7acf-b721-4b5e-ae29-e87bf35f67de)
3.6 Navigate to newly created lambda function by opening that folder on VS Code
![image](https://github.com/prabhakar2020/sam-aws-toolkit/assets/7165155/4f694640-f1e6-4537-a80d-229823c8d084)
3.7 Open terminal/ command prompt and the following command to debug lambda function
```
sam build
```
![image](https://github.com/prabhakar2020/sam-aws-toolkit/assets/7165155/bd44f2da-952c-4c74-b007-5e500be77c68)

3.8 Run lambda function on local machine
```
sam local invoke
```

3.9 Define event json on /event/event.json file and pass as shown below
```
sam local invoke -e event/event.json
```
3.10 Test function in the cloud
```
sam sync --stack-name {{stack-name}} --watch
eg: sam sync --stack-name demo_lambda_function --watch
```

3.11 Deploy Lambda on AWS 
```
sam deploy --guide
```





