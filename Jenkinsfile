pipeline {
    agent any
    stages {
        stage('Clone repository') {
            steps {
                sh 'rm -rf spring-petclinic' // remove existing workspace
                sh 'https://github.com/Aarushitiwari/spring-petclinic.git'
                sh 'cd spring-petclinic && git checkout main'
            }
        }
        stage('Build') {
            steps {
                sh 'cd spring-petclinic && ./mvnw package'
            }
        }
        stage('Ansible Deploy') {
            steps {
                dir('spring-petclinic') {
                    sh 'ansible-playbook /etc/playbook.yml'
                }
            }
        }
    }
}