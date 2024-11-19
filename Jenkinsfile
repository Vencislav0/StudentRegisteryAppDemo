pipeline{
    agent any

    environment{
        NODE_VERSIONS = '18.x'
    }

    tools{
        nodejs '18.x'
    }

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
                    bat 'npm start &'
                    bat 'wait-on http://localhost:8090'
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