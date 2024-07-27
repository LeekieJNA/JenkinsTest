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
        fileExists "step1.py" ? "File found proceeding with the build" : "File NOT Found"
      }
    }
   stage("Run the Python Script") {
      steps {
        sh 'python3 step1.py'
      }
    }
  }
}
