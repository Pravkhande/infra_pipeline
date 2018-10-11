pipeline {
  agent any
  stages {
    stage('Deploy') {
      environment {
        abc = 'qwe'
      }
      parallel {
        stage('1. Staging deployment') {
          steps {
            sh '''#!/bin/bash

echo "Creation of env"'''
          }
        }
        stage('2. Production deployment') {
          steps {
            echo 'Deploying created environment'
            sh '''#!/bin/bash

echo "starting deployment of an env"'''
            sleep 60
          }
        }
      }
    }
    stage('Test (Infra test)') {
      parallel {
        stage('1. InfraParams.json') {
          steps {
            echo 'Create infraParams.json from payload'
            sh '''#!/bin/bash

echo "Creating input.json from payload"'''
          }
        }
        stage('2. Infra test(awspec)') {
          steps {
            sleep(time: 60, unit: 'SECONDS')
          }
        }
      }
    }
    stage('Output') {
      parallel {
        stage('1. Check report ') {
          steps {
            echo 'Check test is completed and fetch report'
          }
        }
        stage('2. Display spec report') {
          steps {
            echo 'URL for Report should be given'
            sleep 30
          }
        }
      }
    }
  }
}