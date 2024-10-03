pipeline {

    agent any
    environment {
        NPM_CONFIG_CACHE = "${WORKSPACE}/.npm"
    }
    stages {
        stage('etapa de contruccion de aplicacion') {
            agent {
                docker {
                    image 'node:alpine3.20'
                    reuseNode true
                }
            }
            stages {
                stage('install') {
                    steps {
                        sh 'npm install'
                    }
                }
                stage('test') {
                    steps {
                        sh 'npm run test'
                    }
                }
                stage('build') {
                    steps {
                        sh 'npm run build'
                    }
                }
            }
        }
    }
    
}
