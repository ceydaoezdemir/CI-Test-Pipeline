pipeline {
    agent any
    
    environment {
        JAVA_HOME = '/Library/Java/JavaVirtualMachines/jdk1.8.0_381.jdk/Contents/Home'
    }

    stages {
        stage ('Compile Stage') {
            steps {
                script {
                    def mvnHome = tool name: 'maven_3_9_4', type: 'hudson.tasks.Maven$MavenInstallation'
                    env.PATH = "${mvnHome}/bin:${env.PATH}"
                    sh 'mvn clean compile'
                }
            }
        }
        
        stage ('Testing Stage') {
            steps {
                script {
                    def mvnHome = tool name: 'maven_3_9_4', type: 'hudson.tasks.Maven$MavenInstallation'
                    env.PATH = "${mvnHome}/bin:${env.PATH}"
                    sh 'mvn test'
                }
            }
        }

        stage ('Deployment Stage') {
            steps {
                script {
                    def mvnHome = tool name: 'maven_3_9_4', type: 'hudson.tasks.Maven$MavenInstallation'
                    env.PATH = "${mvnHome}/bin:${env.PATH}"
                    sh 'mvn deploy'
                }
            }
        }
    }
}
