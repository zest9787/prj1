
pipeline {

    agent any

    tools {
        ant 'ANT-1.10.9'
    }

    stages {
        stage('checkout') {
            git credentialsId: 'jenkins_github', url: 'https://github.com/zest9787/prj1.git'
            git credentialsId: 'jenkins_github', url: 'https://github.com/zest9787/prj2.git'
        }
    }
}