# AWS S3 Lambda Project

This project sets up an AWS infrastructure using Bash scripting to create an S3 bucket, Lambda function, IAM role, SNS topic, and establishes the necessary permissions and triggers between them.

## Project Structure

- **`s3-lambda-function`**: Contains the Lambda function code.
- **`example_file.txt`**: A sample file to be uploaded to the S3 bucket.

## Prerequisites

- AWS CLI installed and configured with the necessary credentials.
- `jq` installed for JSON parsing.

## Instructions

1. **AWS Account ID:**
   The script retrieves and prints the AWS Account ID.

2. **IAM Role Creation:**
   - Creates an IAM role with the required trust relationship for Lambda, S3, and SNS services.
   - Attaches policies for Lambda and SNS full access.

3. **S3 Bucket Creation:**
   - Creates an S3 bucket in the specified AWS region.
   - Uploads `example_file.txt` to the created S3 bucket.

4. **Lambda Function Setup:**
   - Zips the contents of `s3-lambda-function` for Lambda deployment.
   - Creates a Lambda function with the specified configuration.
   - Grants permissions to the S3 bucket to invoke the Lambda function.

5. **S3 Event Trigger:**
   - Sets up an S3 event trigger to invoke the Lambda function upon object creation.

6. **SNS Topic Creation:**
   - Creates an SNS topic named "s3-lambda-sns."
   - Subscribes an email address to the topic for notifications.

7. **SNS Publish:**
   - Publishes a sample message to the SNS topic.

## Usage

1. Ensure AWS CLI is installed and configured.

2. Install `jq` for JSON parsing.

3. Run the script:
   ```bash
   ./deploy.sh
   ```

## Notes

- The script uses a sample Lambda function (`s3-lambda-function`) for demonstration purposes. Modify the function as needed.

- Adjust the AWS region, S3 bucket name, Lambda function name, IAM role name, and email address as per your requirements.

- Ensure that the IAM user/role executing the script has the necessary permissions to create resources.

- Monitor the AWS CloudWatch logs for Lambda function execution and SNS notifications for successful integration.

Feel free to customize the project based on your specific use case and requirements.
