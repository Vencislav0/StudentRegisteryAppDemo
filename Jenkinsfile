pipeline{
    agent any

    

    stages{
        stage('Checkout'){
            steps{
                git branch: 'main', url: 'https://github.com/Vencislav0/StudentRegisteryAppDemo'
            }
        }
        stage('Install dependencies'){
            steps{
                script{
                    bat 'npm install'

                }

            }
        }
        stage('Start application and run tests'){
            steps{
                script{
                    bat 'start npm start'                    
                    bat 'npm test'
                    
                }

            }
        }
    }

    post{
        always{
            echo "CI pipeline completed"
        }
    }
}