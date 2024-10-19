pipeline{
    agent any
    stages{
        stage('checkout the code from github'){
            steps{
                 git url: 'https://github.com/SandhyaMogarala/repo1234'
                 echo 'github url checkout'
            }
        }
        stage('codecompile with project'){
            steps{
                echo 'starting compiling'
                sh 'mvn compile'
            }
        }
        stage('codetesting with project'){
            steps{
                sh 'mvn test'
            }
        }
        stage('qa with project'){
            steps{
                sh 'mvn checkstyle:checkstyle'
            }
        }
        stage('package with project'){
            steps{
                sh 'mvn package'
            }
        }
        stage('run dockerfile'){
          steps{
               sh 'docker build -t myimg .'
           }
         }
        stage('port expose'){
            steps{
                sh 'docker run -dt -p 8081:8081 --name c01 myimg'
            }
        }   
    }
}
