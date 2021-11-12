# Experiment #1: Cloudformation with Kinesis and Lambda

This experiment contains Cloudformation template that spins up the following resources:

- Kinesis Stream
- Lambda Function

Ensure your AWS access key and secret key has been configured:

```
aws configure
```

You can check within the following directories:

```
~/.aws/config
~/.aws/credentials
```

To validate stack:

```
aws cloudformation validate-template --template-body file://cf.yaml
```

To create a new stack:

```
aws cloudformation create-stack --stack-name hello-lambda-stack \
  --template-body file://cf.yaml --capabilities CAPABILITY_NAMED_IAM
```

To update the stack:

```
aws cloudformation update-stack --stack-name hello-lambda-stack \
  --template-body file://cf.yaml --capabilities CAPABILITY_NAMED_IAM
```

To invoke lambda:

```
aws lambda invoke --function-name HelloLambdaFunction output.txt
```
