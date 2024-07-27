pipeline {
  agent any
  stages {
    stage("Check Version of Python") {
      steps {
        sh 'python3 --version'
      }
    }
    stage("Check if Python Script Exists") {
      steps {
        if fileExists('step1.py') {
          echo "File exists"
        } else {
          echo "File DOES NOT EXIST!"
        }
      }
    }
   stage("Run the Python Script") {
      steps {
        sh 'python3 step1.py'
      }
    }
  }
}
