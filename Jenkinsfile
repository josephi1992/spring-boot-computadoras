pipeline {
    agent any
    environment {
        JAVA_TOOL_OPTIONS = "-Duser.home=/home/jenkins"
    }
    stages {
        stage('Checkout') {
            steps {
                // Clonar el repositorio desde GitHub
                git url: 'https://github.com/3ct-mx/spring-boot-computadoras.git', branch: 'main'
            }
        }
        stage('Build') {
            steps {
                // Ejecutar Maven dentro de un contenedor temporal de Maven
                sh 'docker run --rm -v $PWD:/app -w /app maven:3.6.3-jdk-13 mvn clean install'
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

        }
    }
}
