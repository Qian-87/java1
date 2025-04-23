pipeline { 
    agent any 
    stages { 
        stage('Checkout') { 
            steps { 
                git branch: 'master', url: 'https://github.com/Qian-87/java1.git'

            } 
        } 
        stage('Build') { 
            steps { bat'start gradlew build'} 
        } 
        stage('Test') { 
            steps { bat 'start gradlew test'} 
        } 
        stage('Deploy') { 
            steps { powershell 'java -jar build/libs/java1.jar'}            
        }     
}

post {
    always {
    echo 'Cleaning up workspace'
    deleteDir() // Clean up the workspace after the build
    }
    success {
    echo 'Build succeed!!!!'
    // You could add notification steps here
    }
    failure {
    echo 'Build failed!'
    // You could add notification steps here
    }
    }
}