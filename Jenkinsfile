// Jenkinsfile
// Declarative
// Ref: Jenkins Pipeline Tutorial https://www.youtube.com/watch?v=MY1w7sWW5ms&list=PLy7NrYWoggjw_LIiDK1LXdNN82uYuuuiC&index=3
// Resf: Jenkins environment variables http://localhost:8080/env-vars.html/
pipeline {
	agent any
	parameters {
		string(name: 'VERSION', defaultValue: '', description: 'version to deploy on prod')
		choice(name: 'VERSIONS', choices: ['1.0.0', '1.2.0', '1.3.0'], description: '')
		booleanParameter(name: 'execueTests', defaultValue: true, description: '')
	}
	environmnet {
		NEW_VERSION = '1.0.0'
		SERVER_CREDENTIALS = credentials('server-credentials')
	}
	tools {
		maven 'Maven'
		gladle 'gradle-8.14.1'
		// jdk ...
	}
	stages {
		stage("build") {
			steps {
				echo "Building application... "
				echo "Building version  ${NEW_VERSION}"
				echo "Run Maven"
				sh "mvn install"
				echo "Run Gradle"
				withGradle(){
					sh 'gradle -v'
				}
				//Groovy script
				script {
				    def test = 2+2 > 3 ? "cool" : "not cool"
				    echo test
				}

					
			}
		}
		stage("test") {
			when {
				expression {
					params.execueTests == true
					// params.execueTests 
				}
			}
			steps {
				echo 'Testing application... '
				withCredentials({
					usernamePassword(credentials: 'server-credentials', usernameVariable: USER, passwordVariable: PWD)
				}) {
					sh "echo ${USER} ${PWD}"
				}
			
			}
		}
		stage("deploy") {
			steps {
				echo 'Deploying application... '
				echo "deploying version ${VERSION}"
				echo "deploying with ${SERVER_CREDENTIALS}"
				sh "${SERVER_CREDENTIALS}"
				//Groovy script
				script {
				    def test = 30 +1 > 3 ? "cool" : "not cool"
				    echo test
				}
			}
		}		
				
	}
	post {
		always {
			echo  'post always'
		}
		success {
			echo 'post success'
		}
		failure {
			echo 'post failure'
		}
	}
}

// Scriptual
//node {
  //groovy script
//}
