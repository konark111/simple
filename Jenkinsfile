pipeline {
    agent any

    stages {
        stage('scm checkout') {
            steps {
                checkout scmGit(branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/konark111/simple.git']])
            }
        }
        
        stage('build & SonarQube Analysis') {
            steps {
                script {
                def mvn = tool 'Maven';
                withSonarQubeEnv('sonarqube') {
                sh "${mvn}/bin/mvn clean verify sonar:sonar -Dsonar.projectKey=cicd -Dsonar.projectName='cicd'"
    }
   }
  }
 }
        stage ('deploy') {
            steps {
                deploy adapters: [tomcat9(credentialsId: '1366f423-f84a-45ab-9142-5d9248bcaa13', path: '', url: 'http://34.207.159.76:8080/')], contextPath: null, war: '**/*.war'
            }
        }
    }
}
