node {
    stage('Build'){
        checkout scm
        sh "chmod 777 gradlew"
        sh "./gradlew build"
    }
    stage('Test'){
        sh "./gradlew clean test"
    }
    stage('SonarQube analysis') {
            steps {
                withSonarQubeEnv('sonarQubePruebas') {
                    sh './gradlew sonarqube'
                }
            }
    }
}