pipeline{
  agent any
  environment{
      PATH = "/usr/share/maven/bin:$PATH"
      PATH = "/usr/share/openjdk/bin:$PATH"

  }
  stages{
      stage('checking'){
          steps{
            sh "mvn clean package"

          }
      }
      stage('build') {
          steps{
            withSonarQubeEnv('sonarqube') {
                sh "mvn sonar:sonar"
            }

          }
      }
  }

}
