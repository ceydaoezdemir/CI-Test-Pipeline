pipeline {
    agent any
    
    environment {
        JAVA_HOME = '/Library/Java/JavaVirtualMachines/jdk1.8.0_381.jdk/Contents/Home'
        MAVEN_HOME = '/Users/ceydaozdemir/Downloads/apache-maven-3.9.4'
        PATH = "$MAVEN_HOME/bin:${PATH}"
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
