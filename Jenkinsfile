pipeline {
    agent {
        docker {
            image 'maven:3.6.3-jdk-13'
            args '-v /tmp/maven:/root/.m2'
        }
    }
    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/3ct-mx/spring-boot-computadoras.git', branch: 'main'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }
    }
}

    post {
        success {
            echo 'Build completed successfully!'
        }
        failure {
            echo 'Build failed.'
        }
    }
}
