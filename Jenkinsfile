pipeline {
    agent any
    
    environment {
        JAVA_HOME = '/Library/Java/JavaVirtualMachines/jdk1.8.0_381.jdk/Contents/Home'
    }

    stages {
        stage ('Compile Stage') {
            steps {
                withMaven(maven : 'maven_3_9_4') {
                    sh 'mvn clean compile'
                }
            }
        }
        
        stage ('Testing Stage') {
            steps {
                withMaven(maven : 'maven_3_9_4') {
                    sh 'mvn test'
                }
            }
        }

        stage ('Deployment Stage') {
            steps {
                withMaven(maven : 'maven_3_9_4') {
                    sh 'mvn deploy'
                }
            }
        }
    }
}
