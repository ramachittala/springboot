pipeline {
    agent any 
    stages {
       stage('Build') {
           steps {
               sh 'mvn clean package'
               sh 'docker build  . -t 10.219.39.124:5000/springbootci:$BUILD_NUMBER'
               sh 'docker images'
       }     
       }
    }  
}

