pipeline {
  agent any
  stages {
    stage("Check Version of Python") {
      steps {
        echo "Checking for Python Version"
        sh 'python3 --version'
      }
    }
    stage("Check if Python Script Exists") {
      steps {
        echo "Locating Python Script"
        script {
          if (fileExists('step1.py')) {
            echo "File exists"
          } else {
            echo "File DOES NOT EXIST!"
            input message: 'The file step1.py does not exist. Do you want to continue?', ok: 'Yes'
            if (userInput == 'No') {
              error("Pipeline stopped by user.")
            }
          }
        }
      }
    }
    stage("Run the Python Script") {
      steps {
        echo "Running the Script"
        sh 'python3 step1.py'
      }
    }
  }
}
