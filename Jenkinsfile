pipeline {
    agent any

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
                sh 'flutter pub get'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'flutter test'
            }
        }

        //opcional
        stage('Build APK') {
            steps {
                sh 'flutter build apk'
            }
        }
    }
}
