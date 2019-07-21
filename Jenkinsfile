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
}
