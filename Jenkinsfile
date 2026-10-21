pipeline {
    agent any

    stages {
        stage('build') {
            agent{
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                sh '''
                ls -la
                node --version
                npm --version
               npm ci
               npm run build
                latest_log=$(ls -t /home/node/.npm/_logs/*debug-0.log 2>/dev/null | head -1)
    [ -z "$latest_log" ] || cat "$latest_log"
                ls -la
                '''
            }
        }
    }
}
