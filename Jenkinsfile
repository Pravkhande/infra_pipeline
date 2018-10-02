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

echo "Creation of env"'''
          }
        }
        stage('Environment deployment') {
          steps {
            echo 'Deploying created environment'
            sh '''#!/bin/bash

echo "starting deployment of an env"'''
            sleep 60
          }
        }
      }
    }
    stage('Stage 2') {
      parallel {
        stage('InfraParams.json') {
          steps {
            echo 'Create infraParams.json from payload'
            sh '''#!/bin/bash

echo "Creating input.json from payload"'''
          }
        }
        stage('Infra test(awspec)') {
          steps {
            sleep(time: 60, unit: 'SECONDS')
          }
        }
      }
    }
    stage('Stage 3') {
      parallel {
        stage('Check report ') {
          steps {
            echo 'Check test is completed and fetch report'
          }
        }
        stage('Display spec report') {
          steps {
            echo 'URL for Report should be given'
            sleep 30
          }
        }
      }
    }
  }
}