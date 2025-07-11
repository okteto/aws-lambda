# AWS Lambda

## What is AWS Lambda?

AWS Lambda is a serverless computing service provided by Amazon Web Services (AWS) that allows you to run code without provisioning or managing servers. It's a key component of the serverless architecture paradigm.

## Key Features

### Serverless Architecture
- **No server management**: AWS handles all the infrastructure, including server provisioning, scaling, and maintenance
- **Event-driven execution**: Functions are triggered by events from various AWS services or HTTP requests
- **Automatic scaling**: Lambda automatically scales your application by running code in response to each trigger

### Pay-per-Use Model
- **Cost-effective**: You only pay for the compute time you consume
- **No idle costs**: No charges when your code isn't running
- **Granular billing**: Charged per request and duration (rounded up to the nearest 1ms)

### Supported Runtimes
Lambda supports multiple programming languages including:
- Python (3.8, 3.9, 3.10, 3.11, 3.12)
- Node.js
- Java
- C# (.NET)
- Go
- Ruby
- Custom runtimes via Lambda Layers

## Common Use Cases

1. **Web APIs**: Build RESTful APIs using API Gateway + Lambda
2. **Data Processing**: Process files uploaded to S3, transform data streams
3. **Scheduled Tasks**: Run cron-like jobs using CloudWatch Events
4. **Real-time Stream Processing**: Process data from Kinesis or DynamoDB streams
5. **Microservices**: Build loosely coupled, independently deployable services
6. **Image/Video Processing**: Resize images, transcode videos on-demand
7. **IoT Backend**: Process IoT device data and trigger actions

## Benefits

- **High Availability**: Built-in fault tolerance and redundancy
- **Automatic Scaling**: Handles traffic spikes without configuration
- **Security**: Integrated with AWS IAM for fine-grained access control
- **Monitoring**: Built-in logging and monitoring with CloudWatch
- **Integration**: Native integration with 200+ AWS services

## Limitations

- **Execution Time**: Maximum execution time of 15 minutes
- **Memory**: 128 MB to 10,240 MB (10 GB)
- **Temporary Storage**: 512 MB to 10,240 MB in /tmp directory
- **Cold Starts**: Initial latency when function hasn't been used recently
- **Concurrent Executions**: Default limit of 1,000 concurrent executions per region

## This Project

This Lambda function is a simple "Hello World" example that:
- Responds to both GET and POST HTTP requests
- Returns a JSON response with a "Hello World!" message
- Is deployed using AWS SAM (Serverless Application Model)
- Uses Python 3.12 runtime
- Is accessible via API Gateway endpoint

## Deployment from Okteto

This Lambda function is deployed directly from Okteto, which provides several advantages:

### Integrated Development Experience
- **Unified Platform**: Manage both your containerized applications and serverless functions from a single platform
- **Consistent Workflow**: Use the same `okteto deploy` command for all your cloud-native resources
- **Environment Variables**: Leverage Okteto's environment variable system across your entire stack

### Development Stack Integration
- **Shared Resources**: Easily share configuration, secrets, and environment variables between your Lambda functions and other Okteto-deployed services
- **Cross-Service Communication**: Lambda functions can interact with your containerized services running in the same Okteto namespace
- **Unified Monitoring**: View logs and metrics for both serverless and containerized components in one place

### Simplified CI/CD
- **Single Pipeline**: Deploy your entire application stack, including Lambda functions, with one command
- **Environment Consistency**: Ensure your Lambda functions use the same configuration across development, staging, and production environments
- **Team Collaboration**: Share Lambda function endpoints and configurations with your team through Okteto's external resources feature

This approach makes it easier to build full-stack applications that combine the benefits of both containerized microservices and serverless functions, all managed through Okteto's developer-friendly platform.