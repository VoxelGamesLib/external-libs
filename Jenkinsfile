pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Building...'
        git(branch: '${BRANCH_NAME}', credentialsId: 'github', url: 'https://github.com/VoxelGamesLib/external-libs.git')
        sh 'chmod +x gradlew'
        sh './gradlew build'
      }
    }
    stage('Test') {
      steps {
        echo 'Testing...'
        sh './gradlew testReport'
      }
    }
    stage('Deploy') {
      steps {
        echo 'Deploying...'
      }
    }
  }
}
