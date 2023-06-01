pipeline {
    agent any
	parameters {
		booleanParam(name: 'VERSION',defaultValue: 'true',description: '')
		choice(name: 'executesTests',choices: ['dev','stage','prod'],description: '')
	  }
	environment {
	    VERSION = '1.1'				
	}
    stages {
        stage('build') {
            steps {
                echo "Hello build env ${VERSION} World"
            }
        }
        stage('test') {
		 when {
		     expression {
			   params.executesTests
			 } 
		 }
            steps {
                echo "Hello test ${VERSION} World"
            }
        }
        stage('deploy') {
            steps {
                echo "Hello deploy  ${ VERSION } World"
				echo "Hello deploy  ${params.VERSION} World"
            }
        }
    }
}
