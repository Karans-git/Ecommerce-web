pipeline {
  agent { label 'karan0'}
  stages {
    stage('building image') {
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
            sudo docker build -t karansrepo .
            sudo docker tag karansrepo:latest public.ecr.aws/d9k3o6i3/karansrepo:latest
            
         '''
      }
    }
    stage('pushing image') {
      steps {
        echo 'pushing image'
        echo 'hi'
        sh '''
            #!/bin/bash
            ls -la
            pwd
            whoami
            sudo su
            whoami
            sudo docker push public.ecr.aws/d9k3o6i3/karansrepo:latest
            sudo docker rmi karansrepo
         '''
      }
    }
  }
}
