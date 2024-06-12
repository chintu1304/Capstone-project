pipeline {
    agent any
    stages{
        stage('build project'){
            steps{
                git url:'https://github.com/chintu1304/Capstone-project/', branch: "master"
                sh 'mvn clean package'
              
            }
        }
        stage('Build docker image'){
            steps{
                script{
                    sh 'docker build -t hemanth1304/staragileprojectfinance:v1 .'
                    sh 'docker images'
                }
            }
        }
         
        
     stage('Deploy') {
            steps {
                sh 'sudo docker run -itd --name Banking Project -p 8083:8081 hemanth1304/staragileprojectfinance:v1'
                  
                }
            }
        
    }
}
