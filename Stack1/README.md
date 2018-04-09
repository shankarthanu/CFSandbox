-- PROD

Prod S3 Contents:

	aws s3 sync --exclude "*" --include "cloudformation/*" --include "prod/*" --include "instance-ps/*" . s3://campussvcs-prod-bucket/hmag

	
Prod Environment Stack

    aws cloudformation create-stack --cli-input-json file://prod/cli_input.json

    aws cloudformation update-stack --cli-input-json file://prod/cli_input.json

Prod How to Create Change Set

    aws cloudformation create-change-set --change-set-name "New-Changes" --change-set-type UPDATE --template-url https://s3.amazonaws.com/campussvcs-prod-bucket/hmag/prod/parent.yml --cli-input-json file://prod/cli_input.json

Execute SSM command to start user-data execution 

## Replace Instance-Ids with instance IDs created by stack ##

    
aws cloudformation create-stack --stack-name CFStack3 --template-body file://CFStack1.yml
aws cloudformation update-stack --stack-name CFStack3 --template-body file://CFStack1.yml
aws cloudformation update-stack --stack-name CFStack3 --template-url https://s3.amazonaws.com/shankarthanu-cftemplates/Stack1/CFStack1.yml


aws cloudformation update-stack --cli-input-json file://cli_input.json


aws s3 sync . 