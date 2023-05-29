pipeline {
  agent { label 'karan0'}
  stages {
    stage('Running Build') {
      steps {
        echo 'Successfully build the docker image and running this command inside it!'
        echo 'hi'
        sh '''
            #!/bin/bash
            ls -la
            pwd
            whoami
            sudo su
            whoami
            sudo aws ecr-public get-login-password --region us-east-1 | sudo docker login --username AWS --password-stdin public.ecr.aws/d9k3o6i3
            sudo docker build -t test .
            sudo docker rmi test
         '''
      }
    }
  }
}
