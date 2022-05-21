//scripted
/*
node {
		echo "Build"
		echo "Test"
	    echo "Integration Test"
	
}
*/

//Declarative Pipeline
pipeline{
	//agent any
	//agent { docker { image 'maven:3.6.3'} }
	agent { docker {image 'node:13.8'}}
	environment{
		mavenHome = tool 'mymaven'
		dockerHome = tool 'mydocker'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages{
		stage('Build'){
			steps{
				sh 'mvn --version'
				sh 'docker --version'
				echo "Build"
				echo "PATH - $PATH"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "BUILD_ID - $env.BUILD_ID"
				echo "BUILD_TAG - $env.BUILD_TAG"
				echo "JOB_NAME - $env.JOB_NAME"
			}
		}
		stage('Test'){
			steps{
				echo "Test"
			}
		}
		stage('Integration Test'){
			steps{
				echo "Integration Test"
			}
		}
	}	
	post {
			always{
				echo "Im awesome. I run always"
			}
			success{
				echo 'I un when you are successful'
			}
			failure{
				echo 'I run when you fail'
			}
		}
	
}