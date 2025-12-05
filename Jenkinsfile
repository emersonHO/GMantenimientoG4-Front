pipeline {
    agent any

    environment {
        PATH = "/opt/flutter/bin:${env.PATH}"
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                    credentialsId: 'github_token',
                    url: 'https://github.com/emersonHO/GMantenimientoG4-Front.git'
            }
        }

        stage('Install Flutter dependencies') {
            steps {
                sh 'flutter --version'
                sh 'flutter pub get'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'flutter test'
            }
        }

        stage('Build APK (Optional)') {
            when {
                expression { false }
            }
            steps {
                sh 'flutter build apk'
            }
        }
    }
}
