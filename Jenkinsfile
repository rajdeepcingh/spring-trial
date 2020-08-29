pipeline {
    agent any
    stages {
        stage ('Initialize') {
            steps {                
			echo "JAVA_HOME = ${JAVA_HOME}"
            }
        }

        stage ('Build') {
            steps {
                bat "mvn -Dmaven.test.failure.ignore=true install" 
            }
            post {
                success {
                    junit 'target/surefire-reports/**/*.xml' 
                }
            }
        }
    }
}
