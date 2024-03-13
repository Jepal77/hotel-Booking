pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main' url: 'https://github.com/Jepal77/hotel-Booking.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'composer install'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'phpunit'
            }
        }

        stage('Build') {
            steps {
                sh 'php index.php'  // Replace 'index.php' with your entry point script
            }
        }

        stage('Deploy') {
            steps {
                // Add deployment steps if needed
                sh 'echo "Deploying..."'
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
