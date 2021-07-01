pipeline {
    agent any

    // tools {
      //  maven 'Maven'
   // } 

    stages {
        stage ('Compile') {
        steps {
            echo 'compiling'
            //git branch: 'main', credentialsId: 'cred', url: 'https://github.com/mashk12345/samplesum.git'
            //git branch: 'main', changelog: false, credentialsId: '1bb4059c-b8db-4e03-ba8a-e82f92443246', poll: false, url: 'https://github.com/mashk12345/samplesum.git'
            git branch: 'main', changelog: false, credentialsId: 'c8f4230d-2609-4bbb-9af1-ec504f07995a', poll: false, url: 'https://github.com/mashk12345/samplesum.git'
             sh "export MVN_HOME=/opt/maven"
            sh "mvn --version"
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
            sh "mvn --version"
           
        }
    }
      stage ('Deploy'){
            steps {
                // sh "cd ~"
                sh "pwd"
                sh "whoami"
                
               sh "mvn deploy -X"
           //    sh "curl http://localhost:8081/repository/maven-releases/"
    }
} 
      stage ('code quality'){
            steps {
                echo "Packaging"
                sh "mvn sonar:sonar"
            }
        } 
        }
} 

