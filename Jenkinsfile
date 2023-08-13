def app

node {
    stage('Checkout') {
            checkout scm
    }

    stage('Ready'){
        sh "echo 'Ready to build'"
    }

    stage('Build'){
        sh "echo 'Build Spring Boot Jar'"
    }

    stage('Build image'){
        app = docker.build("211.183.3.100/web/production:1.0")
    }

    stage('Push image') {
        docker.withRegistry("http://211.183.3.100", "harbor") {
            app.push("01") 
        }
    }

    stage('Complete') {
        sh "echo 'The end'"
    }
  }
