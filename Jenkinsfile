node {
    stage('Build'){
        checkout scm
        sh "chmod 777 gradlew"
        sh "./gradlew build"
    }
    stage('Test'){
        sh "./gradlew clean test"
    }
    stage("build & SonarQube analysis") {
        agent any
        steps {
            withSonarQubeEnv('My SonarQube Server') {
            sh 'mvn clean package sonar:sonar'
            }
        }
    }
}