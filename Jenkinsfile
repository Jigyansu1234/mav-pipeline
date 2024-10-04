pipeline {
    agent any
    
    tools {
        jdk "Java-11"  // Change to "Java-11" if it's available in your Jenkins configuration
        maven "M3"     // Change to "M3" if Jenkins suggests this as your configured Maven version
    }

    stages {
        stage('Compile Stage') {
            steps {
                withMaven(maven: 'M3') {   // Make sure this matches the Maven configuration in Jenkins
                    sh 'mvn clean compile'  // Use 'sh' for Unix/Linux environments, or 'bat' for Windows
                }
            }
        }

        stage('Testing stage') {
            steps {
                withMaven(maven: 'M3') {
                    sh 'mvn test'
                }
            }
        }

        stage('Packaging Stage') {
            steps {
                withMaven(maven: 'M3') {
                    sh 'mvn package'
                }
            }
        }
    }
}
