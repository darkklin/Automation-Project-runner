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
				stage("reports"){
			steps {
			script {
            allure([
                    includeProperties: false,
                    jdk: '1.8.0_202"',
                    properties: [],
                    reportBuildPolicy: 'ALWAYS',
                    results: [[path: '/c/home/qa/jenkins/workspace/Automtion-Project-run-tests/']]
            ])
    }
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