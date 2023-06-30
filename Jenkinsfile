pipeline {
    agent any
    stages {
        stage('install') {
            steps {
                sh "npm install"
            }
        }

        stage('build') {
            steps {
                sh "npm run build"
            }
        }
      
      stage('SonarQube analysis') {
            steps {
                withSonarQubeEnv('sonarqube') {
                    echo 'scanning'
                    sh 'mvn sonar:sonar'
                }
            }
        }

      stage('deploy') {
            steps {
                sh "npm run deploy"
    }
  }
 }
}
