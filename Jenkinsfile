pipeline{
agent any
stages{
  stage("Git Checkout"){
    steps{
      git credentialsId: 'ba0f45f0-7b2b-4c7f-b804-5a843cd4a163', url: 'https://github.com/B-Apoorva/java-maven-starter.git'
    }
  }
  stage ("Build"){
    steps{
    sh "mvn validate"
    sh "mvn compile"
    sh "mvn test"
    sh "mvn clean package"
    }
  }
  stage('SonarQube analysis') {
        steps{
        withSonarQubeEnv('sonarqube-10.0') { 
        sh "mvn sonar:sonar"
    }
        }
        }
  }
}
