pipeline {
    agent any

    tools { 
        maven 'Maven_3_8_4'  
    }

    stages {
        stage('Run SCA Analysis Using Snyk') {
            steps {		
                withCredentials([string(credentialsId: 'SNYK_TOKEN', variable: 'SNYK_TOKEN')]) {
                    sh 'mvn snyk:test -fn'
                }
            }
        }
    }
}
