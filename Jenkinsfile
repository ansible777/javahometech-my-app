pipeline{
  agent any
  environment{
      PATH = "/usr/share/maven/bin:$PATH"
      PATH = "/usr/lib/jvm/java-8-openjdk-amd64/jre/bin/java:$PATH"

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
