# localstack - https://localstack.cloud/

## check logs for specific lambda function

```sh
awslocal logs tail /aws/lambda/${lambda_function_name}  --follow
```
