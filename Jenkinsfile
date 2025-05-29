// Jenkinsfile
// Declarative
// Ref: Jenkins Pipeline Tutorial https://www.youtube.com/watch?v=MY1w7sWW5ms&list=PLy7NrYWoggjw_LIiDK1LXdNN82uYuuuiC&index=3
// Resf: Jenkins environment variables http://localhost:8080/env-vars.html/
pipeline {
	agent any
	stages {
		stage("build") {
			steps {
				echo "Building application... "
				//Groovy script
				script {
				    def test = 2+2 > 3 ? "cool" : "not cool"
				    echo test
				}
					
			}
		}
		stage("test") {
			steps {
				echo "Testing application... "
			
			}
		}
		stage("deploy") {
			steps {
				echo "Testing application... "
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
