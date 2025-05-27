// Jenkinsfile
// Declarative
// Ref: Jenkins Pipeline Tutorial https://www.youtube.com/watch?v=MY1w7sWW5ms&list=PLy7NrYWoggjw_LIiDK1LXdNN82uYuuuiC&index=3
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
			}
		}		
				
	}
}

// Scriptual
//node {
  //groovy script
//}
