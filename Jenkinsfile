pipeline {

agent any {

    stages {
      stage('Build') {
          steps {
            sh 'mvn clean package'
            sh 'docker build -f example.df . -t 10.219.39.124:5000/springbootci/$BUILD_NUMBER'
            sh 'docker push 10.219.39.124:5000/springbootci/$BUILD_NUMBER'
      
          }
      }    

    }  
 }

}
