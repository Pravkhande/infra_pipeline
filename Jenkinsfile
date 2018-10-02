pipeline {
  agent any
  stages {
    stage('Stage 1') {
      environment {
        abc = 'qwe'
      }
      parallel {
        stage('Environment creation') {
          steps {
            sh '''#!/bin/bash

echo "starting deployment of an env"'''
          }
        }
        stage('Environment deployment') {
          steps {
            echo 'Deploying created environment'
          }
        }
      }
    }
  }
}