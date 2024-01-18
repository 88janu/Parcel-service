pipeline {
    agent {label 'slave1'}
    stages {
        stage('checkout') {
            steps {
                sh 'rm -rf hello-world-war'
                sh 'git clone https://github.com/88janu/hello-world-war.git'
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
                sh 'scp /home/slave1/workspace/parcel-service_feature-1/target/simple-parcel-service-app-1.0-SNAPSHOT.jar root@172.31.6.180:/opt/apache-tomcat-8.5.98/webapps'
            }
        }
    }
}
