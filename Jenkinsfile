pipeline{
    tools{
        jdk 'maven'
        maven 'maven'
    }
    agent none
      stages{
          stage('Checkout'){
              agent any
              steps{
                  git 'https://github.com/devops-trainer/game-of-life.git'
              }
          }
          stage('Compile'){
              
              steps{
                  sh 'mvn compile'
              }
          }
          stage('UnitTest'){
              
              steps{
                  git 'https://github.com/devops-trainer/game-of-life.git'
                  sh 'mvn test'
              }
              post{
                  always{
                      junit 'gameoflife-web/target/surefire-reports/*.xml'
                  }
              }
          }
          stage('Package'){
              
              steps{
                  sh 'mvn package'
              }
          }
         
      }
    
}
