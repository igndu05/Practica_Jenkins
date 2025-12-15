pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Instalando dependencias'
                sh 'npm install'

                echo 'Construyendo la aplicación'
                sh 'npm run build'
            }
        }
    }

    post {
        success {
            archiveArtifacts artifacts: 'dist/**', fingerprint: true
        }
        failure {
            echo 'Build fallido'
        }
    }
}
