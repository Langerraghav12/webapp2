pipeline{
agent any
stages{
stage('Checkout'){
steps{
git branch:'main', url:'https://github.com/Langerraghav12/webapp2.git'
}}
stage('Build'){
steps{
sh 'mvn clean package'
}}
stage('Archive'){
steps{
archiveArtifacts artifacts: 'target/*.war',fingerprint:true
}}
stage('Deploy'){
steps{
sh 'mvn clean package'
sh 'ansible-playbook playbook.yml -i hosts.ini'
}}}}
