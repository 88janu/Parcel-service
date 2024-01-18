pipeline {
    agent {label 'slave1'}
    stages {
        stage('checkout') {
            steps {
                sh 'rm -rf '
                sh 'git clone '
            }
        }
        stage('build') {
            steps {
                sh 'mvn --version'
                sh 'mvn clean install'
            }
        }
        stage('deploy') {
            steps {
                sh 'ssh root@172.31.6.180'
                sh 'scp  root@172.31.6.180:/opt/apache-tomcat-8.5.98/webapps'
            }
        }
    }
}
