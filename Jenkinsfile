pipeline {
  agent any
  environment {
    AAA_TOP_LEVEL_VAR = 'topLevel'
    AAA_RANDOM_VAR = sh(returnStdout:true,script:'openssl rand -base64 19').trim()
    AAA_SECRET_TEXT = credentials('secret-text')
  }
  stages {
    stage('stage 1') {
      steps {
        sh 'echo $AAA_TOP_LEVEL_VAR'
        sh 'env | sort'
      }
    }
    stage('stage 2') {
      environment {
        AAA_STAGE_LEVEL_VAR = 'stageLevel'
      }
      steps {
        sh 'echo $AAA_STAGE_LEVEL_VAR'
        sh 'env | sort'
      }
    }
    stage('stage 3') {
      steps {
        sh 'echo $AAA_STAGE_LEVEL_VAR'
        sh 'env | sort'
      }
    }
    stage('stage 4') {
      steps {
        sh 'echo $AAA_RANDOM_VAR'
        sh 'env | sort'
      }
    }
    stage('stage 5') {
      steps {
        sh 'echo $AAA_SECRET_TEXT'
        sh 'env | sort'
      }
    }
  }
}
