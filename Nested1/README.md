-- PROD

Prod S3 Contents:

	aws s3 sync --exclude "*" --include "cloudformation/*" . s3://enquizit-cfsandbox-bucket/Nested1

	aws s3 sync --exclude "*" --include "cloudformation/*" . s3://shankarthanu-cftemplates/Nested1

	Amazon S3enquizit-cfsandbox-bucket/Nested1/cloudformation

Create / update stack
	aws cloudformation create-stack --stack-name Nested1 --template-url https://s3.amazonaws.com/enquizit-cfsandbox-bucket/Nested1/cloudformation/Nested1.yml
	aws cloudformation create-stack --cli-input-json file://dev/cli_input.json

	aws cloudformation create-stack --cli-input-json file://cli_input.json
	aws cloudformation update-stack --cli-input-json file://cli_input1.json

	aws cloudformation create-stack --stack-name CFStack3 --template-body file://Nested1.yml
	aws cloudformation update-stack --stack-name CFStack3 --template-body file://Nested1.yml
	

Prod How to Create Change Set

    aws cloudformation create-change-set --change-set-name "New-Changes" --change-set-type UPDATE --template-url https://s3.amazonaws.com/campussvcs-prod-bucket/hmag/prod/parent.yml --cli-input-json file://prod/cli_input.json

Execute SSM command to start user-data execution 

## Replace Instance-Ids with instance IDs created by stack ##

    






