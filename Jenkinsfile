pipeline {
    agent any
    tools {
        nodejs 'NodeJS 16'  // Pastikan nama ini sesuai dengan konfigurasi di "Global Tool Configuration"
    }
    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/namauser/node-app.git'
            }
        }
        stage('Build') {
            steps {
                sh 'npm install'  // Ini akan menggunakan npm dari Node.js yang sudah terinstal
            }
        }
        stage('Test') {
            steps {
                sh 'npm test'  // Asumsi bahwa kamu sudah menyiapkan unit test di package.json
            }
            post {
                success {
                    echo 'Tes berhasil!'
                }
                failure {
                    echo 'Tes gagal!'
                }
            }
        }
        stage('Deploy') {
            steps {
                sh 'echo "Menjalankan aplikasi..."'
                sh 'node app.js &'  // Menjalankan aplikasi node.js di background
            }
        }
    }
}
