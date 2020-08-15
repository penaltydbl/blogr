pipeline {
  agent {
    docker {
      image 'python:3.7.2'
    }

  }
  stages {
    stage('PWD') {
      steps {
        sh 'pwd'
        script {
          pipeline {
            agent { docker { image 'python:3.7.2' } }
            stages {
              stage('build') {
                steps {
                  sh 'pip install -r requirements.txt'
                }
              }
              stage('test') {
                steps {
                  sh 'python test.py'
                }
              }
            }
          }
        }

      }
    }

  }
}