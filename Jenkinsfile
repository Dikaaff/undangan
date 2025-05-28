pipeline {
 agent any
 stages {
 stage('Clone Repository') {
 steps {
 git 'https://github.com/Dikaaff/undangan'
 }
 }
 stage('Build') {
 steps {
 sh 'npm install'
 }
 }
 stage('Test') {
 steps {
 sh 'npm test' // asumsi telah dibuat unit test
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
 sh 'node app.js &'
 }
 }
 }
}
