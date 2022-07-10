pipeline{
	agent any
	stages{
		stage("Pull Latest Image"){
			steps{
				  docker pull darkklin/finalproject
			}
		}
		stage("Run Test"){
			steps{
				sh "docker-compose up TestNGWeb TestNGApi"
			}
		}
	}
	post{
		always{
			archiveArtifacts artifacts: 'output/**'
			sh "docker-compose down"
			sh "sudo rm -rf output/"
		}
	}
}