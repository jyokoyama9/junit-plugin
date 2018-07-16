pipeline { 
   agent {
       docker {
           image 'maven:3.5.4-jdk-8'
       }
   }
    stages { 
        stage('Build') { 
            steps { 
               sh 'mvn -Dmaven.test.failure.ignore=true install' 
            }
        }
    }
}
