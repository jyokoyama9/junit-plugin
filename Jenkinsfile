pipeline { 
   agent {
       docker {
           image 'maven:3.5.4-jdk-8'
           args '-v ${WORKSPACE}/.m2:/root/.m2' 
       }
   }
    stages { 
        stage('Build') { 
            steps { 
               sh 'mvn -Dmaven.test.failure.ignore=true clean build site' 
            }
            post {
                success {
                    junit 'target/surefire-reports/**/*.xml' 
                }
            }
        }
        stage('静的解析') {
            steps {
                $class: 'CheckStylePublisher'
            }
        }
    }
}
