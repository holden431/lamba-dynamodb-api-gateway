# Users API
# Pre requisites
* [AWS CLI is installed](https://aws.amazon.com/cli/)
* [SAM CLI is installed](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/serverless-sam-cli-install.html)
* [Your AWS Configuration is pointing to your account](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-configure.html)

# How to run
* export AWS_ACCESS_KEY_ID=XXXXXXXXXXXXXXX
* export AWS_SECRET_ACCESS_KEY=XXXXXXXXXXXXXXXXX
* export AWS_DEFAULT_REGION=us-east-1
* $BUCKET_NAME="name_of_s3_bucket"
* Create S3 bucket:
* aws s3api create-bucket --bucket $BUCKET_NAME && aws s3 cp ./users-openapi.yaml s3://$BUCKET_NAME/
* change BUCKET_NAME to S3 bucket name in samconfig.toml and template.yml
* sam build && sam deploy
* aws cloudformation delete-stack --stack-name users-service