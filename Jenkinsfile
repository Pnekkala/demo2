pipeline {


 agent {label 'master'}


stages {


stage('Test') {


steps {


sh '/usr/local/bin/cfn-lint ./*.json'


}


}


stage('s3upload') {


steps {


sh '/usr/local/bin/aws s3 cp instance.json s3://aws-logs-786678469955-ap-southeast-2/instance.json'


}


}


stage('Deploy') {


steps {


sh 'cd /usr/local/bin/'


sh 'ls'


sh "/usr/local/bin/aws cloudformation create-stack --stack-name Stagestack --template-body file://instance.json --region 'ap-southeast-2'"


}


}


}


}
