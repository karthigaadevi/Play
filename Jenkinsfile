pipeline {
    agent {
        label 'master' // Use 'master' if Jenkins is running on the same machine
    }

    stages {
        stage('Checkout') {
            steps {
                // Clone the repository
                git branch: "${env.BRANCH_NAME}", url: 'https://github.com/karthigaadevi/Project1.git'
            }
        }

        stage('Build') {
            steps {
                script {
                    // Set the Maven home path
                    def mavenHome = "C:\\Program Files\\apache-maven-3.9.9"

                    // Build the project using Maven
                    bat "${mavenHome}\\bin\\mvn clean package"
                }
            }
        }
    }

    post {
        success {
            echo 'Build completed successfully!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
