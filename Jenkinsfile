pipeline{
	agent any
	stages{
		stage("Pull Latest Image"){
			steps{
				bat "docker pull darkklin/finalproject"
			}
		}
		stage("Run Test"){
			steps{
				bat "docker-compose up TestNGWeb TestNGApi"
			}
		}
	}
	post{
		always{
			bat "docker-compose down"
			bat "docker system prune -f"
		}
	}
}