pipeline {
    agent any

    tools {
        maven 'maven'
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

       /* stage ('Package'){
            steps {
                echo "Packaging"
                sh "mvn package"
            }
        } */

        stage ('Install'){
        steps {
            echo "clean install"
            sh "whoami"
            sh "pwd"
            sh "ls -la"
            sh "mvn clean install -X"
        }
    }
    }
}
      //  stage ('Build'){
    //    steps {
      //      echo 'Maven Practice tests'
        //   checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'cred', url: 'https://github.com/mashk12345/samplesum.git']]])
          //  sh "mvn -Dmaven.test.failure.ignore=true clean package" 
        //}
        //} 
