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
            echo "Get the Driver Path {ChromeDriver}"
          }
        }

      }
    }

    stage('Deploy') {
      steps {
        echo 'Deployig the app in IIS server'
      }
    }

  }
  environment {
    ChromeDriver = '"C:\\Program Files\\Google\\Chrome\\Application\\chrome.exe"'
  }
}