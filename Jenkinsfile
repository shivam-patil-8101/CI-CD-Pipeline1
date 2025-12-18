pipeline {
    agent any

    environment {
        VERCEL_TOKEN = credentials('vercel_token')
    }

    stages {
        stage('Test') {
            steps {
                echo 'Skipping tests... No Test found'
            }
        }
        stage('Build') {
            steps {
                bat 'npm run build'
            }
        }
        stage('Install') {
            steps {
                bat 'npm install'
            }
        }
        stage('Deploy') {
            steps {
                bat 'npx vercel --prod --yes --token=%VERCEL_TOKEN%'
            }
        }
}
}