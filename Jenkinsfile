pipeline{
    
    tools{
        jdk 'maven'
        maven 'maven'
    }
    
    agent any
    
    stages{
        
        stage('Checkout Source'){
            steps{
                git 'https://github.com/devops-trainer/game-of-life.git'
            }
        }
        
        stage('Compile'){
            steps{
                sh 'mvn compile'
            }
        }
        
        stage('Test'){
            steps{
                sh 'mvn test'
            }
            
            // Generate readable Unit test reportss//
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
