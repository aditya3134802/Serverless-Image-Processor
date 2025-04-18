# Serverless-Image-Processor
Directory Structure:
serverless-image-processor/
├── lambda/
│   ├── handler.py
│   └── requirements.txt
└── terraform/
    ├── main.tf
    └── variables.tf
Key Script:
# handler.py
import boto3

def lambda_handler(event, context):
    s3 = boto3.client('s3')
    for record in event['Records']:
        bucket = record['s3']['bucket']['name']
        key = record['s3']['object']['key']
        print(f"Processing {key} from {bucket}")
        
