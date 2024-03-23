pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            echo 'Building the .NET Core Application'
          }
        }

        stage('Test') {
          steps {
            echo 'Testing the application'
            echo 'Get the Driver Path {ChromeDriver}'
          }
        }

        stage('Test Log') {
          steps {
            writeFile(file: 'TestLog', text: 'This is an automation text file')
          }
        }

      }
    }

    stage('Deploy') {
      parallel {
        stage('Artifacts') {
          steps {
            archiveArtifacts 'LogFile'
            echo 'Deployig the app in IIS server'
          }
        }

        stage('Deploy') {
          steps {
            input(message: 'Provide acknowledgement', id: 'Ok')
          }
        }

      }
    }

  }
  environment {
    ChromeDriver = 'C:\\Program Files\\Google\\Chrome\\Application\\chrome.exe'
  }
}