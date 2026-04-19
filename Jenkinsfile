pipeline {
  agent {
    label 'linux-agent'
  }
  
 tools {
        maven 'M3' // This name must match the name in Global Tool Configuration
    }

  stages {
       stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/mohamedmagdy05/devsecops/'
            }
        }
      stage('Build Artifact') {
            steps {
              sh "mvn clean package -DskipTests=true"
              archive 'target/*.jar' //so that they can be downloaded later
            }
        }   
    }
}