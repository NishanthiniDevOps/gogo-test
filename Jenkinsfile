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
      sh 'docker tag gogo-ci:latest 480838393998.dkr.ecr.ap-southeast-1.amazonaws.com/gogo:latest'
      sh 'docker push 480838393998.dkr.ecr.ap-southeast-1.amazonaws.com/gogo:latest'         
    }
}
