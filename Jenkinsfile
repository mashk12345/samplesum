pipeline {
    agent any

    tools {
        maven 'Maven'
    } 

    stages {
        stage ('Compile') {
        steps {
            echo 'compiling'
           // git branch: 'main', credentialsId: 'cred', url: 'https://github.com/mashk12345/samplesum.git'
            git branch: 'main', changelog: false, credentialsId: '1bb4059c-b8db-4e03-ba8a-e82f92443246', poll: false, url: 'https://github.com/mashk12345/samplesum.git'
            sh "mvn compile"
        }
        }

        stage ('Test') {
        steps {
            echo "test"
            sh "mvn test"
        }
        }

        stage ('Package'){
            steps {
                echo "Packaging"
                sh "mvn package"
            }
        } 

        stage ('Install'){
        steps {
            echo "clean install"
            sh "mvn clean install"
        }
    }
       stage ('Deploy'){
            steps {
               sh "mvn deploy"
           //    sh "curl http://localhost:8081/repository/maven-releases/"
    }
} 
      
        }
} 

