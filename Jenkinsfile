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
               cat /home/node/.npm/_logs/2026-10-21T17_42_46_875Z-debug-0.log || true
                ls -la
                '''
            }
        }
    }
}
