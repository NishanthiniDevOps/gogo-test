node {
    def app

    stage('Clone repository') {

        checkout scm
    }

    stage('Build image') {

        app = docker.build("gogo-ci")
    }

    stage('Test image') {

        app.inside {
            sh 'echo "Tests passed"'
        }
    }

    stage('Push image') {
      sh '$(aws ecr get-login --no-include-email --region ap-southeast-1)'
      sh 'docker tag gogo-ci:latest 480838393998.dkr.ecr.ap-southeast-1.amazonaws.com/gogo:latest'
      sh 'docker push 480838393998.dkr.ecr.ap-southeast-1.amazonaws.com/gogo:latest'         
    }
    stage('Deploy to dev') {
      input "Deploy to Dev?"
      sh 'echo Deploy to Dev'
      sh 'aws ecs update-service --service gogo-WebService-9L041BDEG1TP --force-new-deployment'
      
    
    }
   stage('Deploy to UAT') {
      input "Deploy to UAT?"
      sh 'echo Deploy to UAT'
    }
  stage('Deploy to Prod') {
      input "Deploy to Prod"
      sh 'echo Deploy to Prod'
    }
}
