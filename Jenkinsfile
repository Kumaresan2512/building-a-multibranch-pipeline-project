pipeline {
    agent any
    stages {
        stage('Read Excel files from Logs folder') {
            steps {
                sh 'echo "Hello world!"'
                log_files = shellGetOutput("ls logs")
                if(log_files != null && !log_files.allWhitespace)
                    archiveArtifacts(artifacts: "logs/*.xlsx", fingerprint: true)
            }
        }
    }
}

def shellGetOutput(cmd)
{
    return sh(script: cmd, returnStuout: true).trim()
}