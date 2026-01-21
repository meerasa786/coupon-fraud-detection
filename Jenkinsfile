pipeline {
  agent any

  environment {
    COMPOSE_FILE = '/opt/fraud-deploy/docker-compose.yml'
  }

  stages {

    stage('Deploy using Docker Compose') {
      steps {
        sh '''
          echo "Using compose file: $COMPOSE_FILE"

          if [ ! -f "$COMPOSE_FILE" ]; then
            echo "ERROR: docker-compose.yml not found at $COMPOSE_FILE"
            exit 1
          fi

          docker compose -f "$COMPOSE_FILE" pull
          docker compose -f "$COMPOSE_FILE" up -d

          docker ps
        '''
      }
    }
  }

  post {
    always {
      echo 'Deployment finished'
    }
  }
}

