pipeline {
  agent { label 'Jenkins-Agent'}  
  tools {
      jdk 'Java17'
      maven 'Maven3'
  }
  stages{
      stage ("Cleanup Workspace") {
                steps {
                  cleanWS()
                }
      }
      stage ("Checkout from scm") {
                steps {
                  git branch: 'main', credentialID: 'github', url: 'https://github.com/kenny-john/Project-1'
                }
      }
      stage ("Build Application") {
                steps {
                  sh "mvn clean package"
                }
      }
      stage ("Test our application") {
                steps {
                   sh "mvn test"
                }
      }
  }
  
}
