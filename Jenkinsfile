pipeline {
    agent any
	parameters {
	 string(name :'version',defaultValue:'',description: 'version to deploy on prod')
	 choice(name :'version',choices:['dev','stage','prod'],description: '')
	}
	environment{
	 new_env: 'DEV'				
	}
    stages {
        stage('build') {
            steps {
                echo "Hello build env ${new_env} World"
            }
        }
        stage('test') {
            steps {
                echo "Hello test ${new_env} World"
            }
        }
        stage('deploy') {
            steps {
                echo "Hello deploy  ${new_env} World"
            }
        }
    }
}
