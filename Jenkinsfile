pipeline {
	agent any
	stages {
		stage('Creation codepipeline') {
			steps {
		  sh '''
		  export AWS_DEFAULT_REGION=eu-west-1
		  if aws cloudformation describe-stacks  --query 'Stacks[].StackName' | grep JenkinsWithCodepipeline-ds ; then
		  aws cloudformation update-stack --stack-name JenkinsWithCodepipeline-ds --template-body file://templateCodepipeline.json --region 'eu-west-1'
		  else
		  aws cloudformation create-stack --stack-name JenkinsWithCodepipeline-ds --template-body file://templateCodepipeline.json --region 'eu-west-1'
          fi
		  '''
		  }
		}
	}
}