pipeline {
    agent any
    
    environment {
        JAVA_HOME = '/Library/Java/JavaVirtualMachines/jdk1.8.0_381.jdk/Contents/Home'
        PATH = "${JAVA_HOME}/bin:${tool name: 'maven_3_9_4', type: 'hudson.tasks.Maven$MavenInstallation'}/bin:${env.PATH}"
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
