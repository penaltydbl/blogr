pipeline {
  agent {
    docker {
      image 'python:3.7.2'
    }

  }
  stages {
    stage('Build') {
      steps {
        sh '''pwd
pip install wheel
cd blogr
python3.7 setup.py bdist_wheel'''
      }
    }

    stage('Test') {
      steps {
        sh '''pip install pytest coverage
pytest'''
      }
    }

  }
}