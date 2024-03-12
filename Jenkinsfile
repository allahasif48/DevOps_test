pipeline {
    agent any
    
    stages {
        stage('Execute Shell Command') {
            steps {
                script {
                    // Run a basic shell command
                    
                    def commandOutput = sh(script: 'echo "Hello, Jenkins!"', returnStdout: true).trim()
                    //
                    // Print the output
                    echo "Shell Command Output: ${commandOutput}"
                }
            }
        }
    }
}
