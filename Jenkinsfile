pipeline{
    agent any

    stages{
        stage('zip the file'){
            steps{
                sh 'zip ansible-${BUILD_ID}.zip * --exclude Jenkinsfile'
                sh 'ls -l'
            }
        }
        stage('upload artifacts to jfrog'){
            steps{
                sh 'curl -uadmin:AP7pcbfccJcTYXZg8HcQ3VKep2w -T\
                 ansible-${BUILD_ID}.zip\
                 "http://44.203.139.247:8081/artifactory/ansible-week18/ansible-${BUILD_ID}.zip"'
            }
        }
    }
}