pipeline {
  agent any

  tools {
    maven "M2"
  }

  stages {
    stage('Compile') {
      steps {
        bat "mvn clean compile"
      }
    }

    stage('Build') {
      steps {
        bat "mvn clean package"
      }

      post {
        success {
          archiveArtifacts 'target/*.war'
        }
      }
    }
  }
}
