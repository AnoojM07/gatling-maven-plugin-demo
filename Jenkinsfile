pipeline {
  agent any
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

  }
}