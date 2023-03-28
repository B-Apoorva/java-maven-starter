pipeline{
agent any
stages{
  stage("Git Checkout"){
    steps{
      git credentialsId: 'html_home', url: 'https://github.com/B-Apoorva/java-maven-starter.git'
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
  }
}
