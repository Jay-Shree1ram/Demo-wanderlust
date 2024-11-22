pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                echo 'Cloning repository...'
                checkout scmGit(branches: [[name: '*/production']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/Jay-Shree1ram/Demo-wanderlust.git']])
            }
        }

        stage('Build') {
            steps {
                echo 'Building application...'
                sh ' sudo docker-compose up --build -d'
            }
        }

    stage('Image Push') {
    steps {
        echo 'Pushing Docker images...'
        sh '''
        docker push kajirocks/wanderlust-be-prod
        docker push kajirocks/wanderlust-fe-prod
        '''
    }
}

      stage('Deployment') {
            steps {
                echo 'Application deployed...'
               
            }
        }
    


}
}
