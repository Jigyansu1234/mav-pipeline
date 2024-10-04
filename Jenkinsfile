pipeline {
    agent any
    
    tools {
        jdk "${tool 'DefaultJDK'}"  // Will use the default JDK configured in Jenkins
        maven "${tool 'DefaultMaven'}"  // Will use the default Maven configured in Jenkins
    }

    stages {
        stage('Compile Stage') {
            steps {
                withMaven {   // No need to specify the Maven version
                    sh 'mvn clean compile'
                }
            }
        }

        stage('Testing stage') {
            steps {
                withMaven {
                    sh 'mvn test'
                }
            }
        }

        stage('Packaging Stage') {
            steps {
                withMaven {
                    sh 'mvn package'
                }
            }
        }
    }
}
