pipeline {
  agent {
    docker {
      image 'maven:3-alpine'
      args '-v /root/.m2:/root/.m2'
    }

  }
  stages {
    stage('Build') {
      steps {
        sh 'mvn -B clean package'
      }
    }

    stage('Test') {
      steps {
        sh 'mvn gatling:test -Dgatling.simulationClass=computerdatabase.BasicSimulation'
      }
    }

    stage('Publish Report') {
      steps {
        sh 'gatlingArchive()'
      }
    }

  }
}