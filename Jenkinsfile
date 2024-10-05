pipeline {
    agent {
        label 'master' // or 'any'
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

                    // Change to the directory containing the pom.xml (if it's in a subdirectory)
                    dir('subdirectory') { // Replace 'subdirectory' with the actual path
                        // Build the project using Maven
                        bat "\"${mavenHome}\\bin\\mvn\" clean package"
                    }
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
