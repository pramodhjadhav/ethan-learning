pipeline {
    agent any
	parameters {
		booleanParam(name: 'VERSION',defaultValue: 'true',description: '')
		choice(name: 'executesTests',choices: ['dev','stage','prod'],description: '')
	  }
	environment {
	 new_env: 'DEV'				
	}
    stages {
        stage('build') {
            steps {
                echo "Hello build env ${new_env} World"
            }
        }
        stage('test') {
		 when {
		     expression {
			   params.executesTests
			 } 
		 }
            steps {
                echo "Hello test ${new_env} World"
            }
        }
        stage('deploy') {
            steps {
                echo "Hello deploy  ${new_env} World"
				echo "Hello deploy  ${params.VERSION} World"
            }
        }
    }
}
