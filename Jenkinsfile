pipeline{
	agent any
	
	tools{
		maven 'Maven'
	}
	
	stage{
		stage("Checkout"){
			git branch:"main",
			git url: "https://github.com/icemberg/MyMaven.git"
		}
		
		stage("Build"){
			steps{
				sh 'maven clean package'
			}
		}
		
		stage("Test"){
			steps{
				sh 'maven test'
			}
		}
		
		stage("Run application"){
			steps{
				sh 'java -jar target/MyMaven-1.0-SNAPSHOT.jar'
			}
		}
		
		post{
			success{
				echo "Build and deployment successful"
			}
			failure{
				echo "Build failed!"
			}
		}
	}
}
