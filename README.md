Usage:
aws cloudformation create-stack --stack-name pfeiffer4gettingstarted --capabilities CAPABILITY_NAMED_IAM --template-body file://cf.yaml --region us-west-2  --parameters ParameterKey=githubpassword,ParameterValue=REDACTED

Notes:
- The stack name means this:
  - Pfeiffer is the author of the Pluralsight AWS Devops Exam class.
  - pfeiffer4gettingstarted is the chapter/segment related to CodeDeploy and CodePipeline.
- For two days the attribute IamInstanceProfile caused the EC2 resource creation to hang. The workaround was to use CloudFormation to create the EC2 instance, use the CLI toassociate an IAMInstanceProfile with theEC2 resource(s), then use another CloudFormation templateto create the CodeDeploy and CodePipeline resources. See /workaround.
- The /CLI folder contains CLI scripts that created resources. The CLI scripts have all been folded into the one remaining cf.yaml file. 

