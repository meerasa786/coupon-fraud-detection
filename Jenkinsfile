pipeline {
  agent any

  stages {
    stage('Deploy from Docker Hub') {
      steps {
        sh '''
          docker compose -f /home/ubuntu/fraud-deploy/docker-compose.yml pull
          docker compose -f /home/ubuntu/fraud-deploy/docker-compose.yml up -d
          docker ps
        '''
      }
    }
  }
}
