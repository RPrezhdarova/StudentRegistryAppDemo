pipeline{
    agent any
  
    stages{
        stage('Checkout'){
            steps{
                git branch: 'main', url: 'https://github.com/RPrezhdarova/StudentRegistryAppDemo'
            }
        }
        stage('Install dependencies'){
            steps{
                script{
                        bat 'npm install'                       
                    }
                }
            }
        }
        stage("Start application and run tests"){
            steps{
                script{
                    bat 'npm start &'
                    bat 'wait-on http://localhost:8090'
                    bat 'npm test'
                }
            }
        }
    
    post{
        always{
            echo "CI pipeline completed"
        }
    }
    
}