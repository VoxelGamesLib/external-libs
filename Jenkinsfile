pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Building..'
        git(changelog: true, url: 'https://github.com/VoxelGamesLib/external-libs.git')
        sh 'gradle'
      }
    }
    stage('Test') {
      steps {
        echo 'Testing..'
      }
    }
    stage('Deploy') {
      steps {
        echo 'Deploying....'
      }
    }
  }
}