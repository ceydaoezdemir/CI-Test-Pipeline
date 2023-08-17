pipeline {
    agent any
    
    environment {
        JAVA_HOME = '/Library/Java/JavaVirtualMachines/jdk-13.0.2.jdk/Contents/Home'
    }

    stages {
        stage ('Compile Stage') {
            steps {
                sh 'mvn clean compile'
            }
        }
        
        stage ('Testing Stage') {
            steps {
                sh 'mvn test'
            }
        }

        stage ('Deployment Stage') {
            steps {
                sh 'mvn deploy'
            }
        }
    }
}
