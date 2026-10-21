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
               rm -rf node_modules
               npm ci --no-audit --no-fund
               npm run build
                ls -la
                '''
            }
        }
    }
}
