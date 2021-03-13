
pipeline {

    agent any

    tools {
        ant 'ANT-1.10.9'
    }

    stages {
        stage('checkout') {
            git credentialsId: 'jenkins_github', url: 'https://github.com/zest9787/prj2.git'
            git credentialsId: 'jenkins_github', url: 'https://github.com/zest9787/prj3.git'
        }

        stage('build') {
            bat 'ant deploy/build.xml'
        }
    }
}