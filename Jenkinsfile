pipeline{
    agent{
        docker{
            image 'node:18-alpine'
            args '-v /var/run/docker.sock:/var/run/docker.sock'
        }
    }

    stages{
        stage('Checkout'){
            steps{
                git 'https://github.com/HuynhNgocTien183/Jenkins.git'
            }
        }
        stage('Install'){
            steps{
                sh 'npm install'
            }
        }

        stage('Build'){
            steps{
                sh 'npm run build'
            }
        }

        stage('Test'){
            steps{
                sh 'npm test'
            }
        }
        
        stage('Publish'){
            steps{
                sh 'echo publish'
            }
        }

         stage('Deploy') { 
            steps { 
                sh 'echo deploy' 
            }
        }
    }      
        

    post{
        always{
            sh 'echo always'
        }
        success{
            sh 'echo success'
        }
        failure{
            sh 'echo failure'
        }
    }
}