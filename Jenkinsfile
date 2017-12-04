#!groovy

pipeline {
    agent any

    stages {
        stage('Hello') {
          echo 'Hello there!'
        }
        
        stage('Get scm') {
          sh git 'https://github.com/executeautomation/SeleniumWithCucucumber.git'
        }
        
        stage('mvn clean')  {
			    agent{
				    label 'slave'
			      }
			    tools{
				  jdk "JDK 8"
				    maven "apache-maven-3.3.9"
			      }		
			    steps{
		   		  sh('mvn clean') 
			      }
		      }

		      stage('mvn install')  {
			      agent{
				      label 'slave'
			      }
			      tools{
				      jdk "JDK 8"
				      maven "apache-maven-3.3.9"
			      }		
			      steps{
		   		    sh('mvn install') 
			        }
          }
    
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
