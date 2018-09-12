pipeline {
    agent any 
    stages {
       stage('Build') {
           steps {
               sh 'mvn clean package'
               sh 'sudo docker build -f example.df . -t 10.219.39.124:5000/springbootci/$BUILD_NUMBER'
               sh 'sudo docker push 10.219.39.124:5000/springbootci/$BUILD_NUMBER'
       
     agent {
       kubernetes {
         label 'k8'
         defaultContainer 'jnlp'
         yaml """
apiVersion: extensions/v1beta1
kind: Deployment
metadata:
  name: springboot-deployment
spec:
  replicas: 2
  template:
    metadata:
      labels:
        app: spring-slc.metric.io
    spec:
      containers:
      - name: springboot
        image: 10.219.39.124:5000/springbootci/$BUILD_NUMBER
        ports: 8080
    
       } 
     }
           }
       }     

    }  
 
}
