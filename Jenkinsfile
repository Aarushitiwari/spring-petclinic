pipeline {
    agent any
    stages {
        stage('Clone repository') {
            steps {
                 sh 'rm -rf spring-petclinic' // remove existing workspace
//                 sh 'git clone https://github.com/Aarushitiwari/spring-petclinic.git'
//                 sh 'cd  spring-petclinic && git checkout main'
            }
        }
        stage('Build') {
            steps {
                sh './mvnw package'
            }
        }
        stage('Ansible Deploy') {
            steps {
                // dir('spring-petclinic') {
                    sh 'ansible-playbook /etc/playbook.yml'
                // }
            }
        }
    }
}