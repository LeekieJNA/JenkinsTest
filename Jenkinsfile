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
        script {
          if (fileExists('step1.py')) {
            echo "File exists"
          } else {
            echo "File DOES NOT EXIST!"
            def userInput = input(
              id: 'userInput', message: 'The file step1.py does not exist. Do you want to continue?', 
              parameters: [choice(name: 'Continue', choices: ['Yes', 'No'], description: 'Continue without the file?')]
            )
            if (userInput == 'No') {
              error("Pipeline stopped by user.")
            }
          }
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
