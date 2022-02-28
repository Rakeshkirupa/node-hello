#! groovy
pipeline {
  agent any
  stages {
    stage('Git') {
        steps {
            sh '''
            #!/bin/bash
            echo "Deployment start"
            cd /Users/rakesh/Documents/jenkins/node-hello
            git pull
         '''
            }
        }
    stage('Deploy') {
        steps {
            sh '''
            cd /Users/rakesh/Documents/jenkins/node-hello
            PATH=/sbin:/usr/sbin:/usr/bin:/usr/local/bin
            pm2 restart index.js
         '''
            }
        }
    stage('Status') {
        steps {
            sh '''
            echo Checking the host
            curl localhost:3000
         '''
            }
        }
    }
}

