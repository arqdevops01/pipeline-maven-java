pipeline {
    agent any
    parameters {
		  string defaultValue: 'hacker', name: 'p1'
	    	  string defaultValue: 'attacks', name: 'p2'
		}
    stages {
        stage('Checkout') {
                steps {
                // Checkout the code from the repository
                //git branch: 'main', url: 'https://github.com/ApasoftTraining/pipeline-maven-java.git'
                echo 'checkout ok'  
			 }
        }
        stage('Build') {
               tools { //Utiliza la tools maven
                     maven 'Maven1'
                    }
               steps {
                echo 'Building...'
                // Compile the code using Maven
                sh 'mvn clean compile'
            }
        }
        stage('Test') {
               tools {
                     maven 'Maven1'
                    }
               steps {
                 echo 'Testing...'
                 // Run tests using Maven
                 sh 'mvn test'
            }
        }
        stage('Package') {
              tools {
                     maven 'Maven1'
                    }
             steps {
                 echo 'Packaging...'
                 // Package the application using Maven
                 sh 'mvn package'
            }
        }
        stage('Deploy') {
             steps {
                echo 'Deploying...'
                // Run the Java program with an example argument
                sh 'java -cp target/your-app-1.0-SNAPSHOT.jar com.apasoft.ToUpper "${p1}" "${p2}"'
            }
        }
    }
}
