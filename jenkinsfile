pipeline {
    agent none
    stages {
		stage('Non-parallel'){
				agent {
						label "master"
				}
				steps {
						echo 'This stage will be executed first'
				}
		}
        stage('Run Tests') {
			parallel{
                stage('Test on Windows_Node') {
					agent {
						label "windows_Node"
					}
					steps {
						echo "Task1 on Agent"
					}
				}
				stage('Test on Master') {
					agent {
						label "master"
					}
					steps {
						echo "Task1 on master"
					}
				}
            }
		}
    }
}
