pipeline {
    agent any  // Use any available agent
    tools {
        gradle 'Gradle'
        jdk 'JDK'
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/dhanushV360/Mavenjenkinspipeline.git'
            }
        }

        stage('Build') {
            steps {
                sh 'gradle install'  // Run Maven build
            }
        }

        stage('Test') {
            steps {
                sh 'gradle test'  // Run unit tests
            }
        }

        
        
       
        stage('Run Application') {
            steps {
                sh 'java -jar target/Dhanush-1.0-SNAPSHOT.jar '
            }
        }

        
    }

    post {
        success {
            echo 'Build and deployment successful!'
        }
        failure {
            echo 'Build failed!'

}
}
}

