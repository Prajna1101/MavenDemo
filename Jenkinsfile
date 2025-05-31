pipeline{
	agent any
	
	tokens{
		maven 'Maven'
		jdk 'jdk'
	}
	
	stages{
		stage('Checkout'){
			steps{
				git branch:'master',url:'https://github.com/Prajna1101/MavenDemo.git'
			}
		}
		
		stage('Build'){
			steps{
				sh 'mvn clean install'
			}
		}
		
		stage('Test'){
			steps{
				sh 'mvn test'
			}
		}
		
		stage('Run Application'){
			steps{
				sh 'java -jar target/MavenDemo-1.0-SNAPSHOT.jar'
			}
		}
	}
	
	post{
		success{
			echo 'Build and deployed maven application!'
		}
		failure{
			echo 'Build failed!'
		}
	}
}
