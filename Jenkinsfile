pipeline {
    agent any
    stages {
        stage('Read Excel files from Logs folder') {
            steps {
                sh 'echo "Hello world!"'
                script{
                log_files = shellGetOutput("ls logs_files")
                if(log_files != null && !log_files.allWhitespace)
                    archiveArtifacts(artifacts: "logs_files/*.xlsx", fingerprint: true)
                }
            }
        }
    }
}

def shellGetOutput(cmd)
{
    return sh(script: cmd, returnStuout: true).trim()
}