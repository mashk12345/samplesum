pipeline {
    agent any

    tools {
        maven 'Maven'
    } 

    stages {
        stage ('Compile') {
        steps {
            echo 'compiling'
            git branch: 'main', credentialsId: 'cred', url: 'https://github.com/mashk12345/samplesum.git'
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
            sh "whoami"
            sh "pwd"
            sh "ls -la"
            sh "mvn clean install sonar:sonar"
        }
    }
       stage ('Build'){
            steps {
                sh "mvn clean deploy"
    }
} 
      
        }
} 

