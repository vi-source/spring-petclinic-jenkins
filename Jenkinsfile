pipeline {
    agent any
    options { 
        timeout(time: 10, unit: 'MINUTES') 
    }
    triggers {
        pollSCM('* * * * *')
    }
    stages {
        stage('git') {
            steps {
                git url: 'https://github.com/vi-source/spring-petclinic-jenkins.git', 
                    branch: 'dev' 
            }
        }
        stage('build') {
            steps {
                sh 'mvn validate'
            }
        }
    }
}    