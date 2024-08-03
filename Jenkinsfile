pipeline {
  
    agent any 
    tools{
        maven "M3"
    }

    stages {
        stage('Git clone') {
            steps {
               git 'https://github.com/Alekhya-kandala/Maven_Web_App.git'
            }
        }
       stage('Maven build') {
            steps {
               sh 'mvn clean package'
            }
        }
       stage('DI') {
            steps {
               sh 'docker build -t alekhyaa .'
            }
        }
       stage('DC') {
            steps {
               sh 'docker run -d -p 9090:8080 --name sample1 alekhyaa'
            }
        }
    }  
}
