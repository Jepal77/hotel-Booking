pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Jepal77/hotel-Booking.git'
            }
        }

      stage('Install Dependencies') {
    steps {
        // Navigate to the project directory
        dir("C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\hp") {
            // Run Composer install command
            bat 'composer install'
            }
        }
    }
        
     stage('Run Tests') {
            steps {
                bat 'phpunit'
            }
        }

        stage('Build') {
            steps {
                bat 'php index.php'  // Replace 'index.php' with your entry point script
            }
        }

        stage('Deploy') {
            steps {
                // Add deployment steps if needed
                echo 'Deploying...'
            }
        }
    }

    post {
        always {
            // Clean up steps, if needed
            echo 'Always executed'
        }

        success {
            // Notification or further actions on success
            echo 'Success!'
        }

        failure {
            // Notification or further actions on failure
            echo 'Failure!'
        }
    }
}
