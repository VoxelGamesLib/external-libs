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
        publishHTML([allowMissing: false, alwaysLinkToLastBuild: false, keepAll: false, reportDir: 'build/reports/allTests/', reportFiles: 'index.html', reportName: 'JUnit Test Reports'])
      }
    }
    stage('Deploy') {
      steps {
        echo 'Deploying...'
      }
    }
  }
}
