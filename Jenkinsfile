pipeline {
        agent any

        stages {
            stage('Checkout') {
                steps {
                        checkout scm
                      }}
                stage('Build') {
                   steps {
                          sh '/home/ishika/Documents/devops_software/apache-maven-3.9.6/bin/mvn install'
                         }}
                stage('Deployment'){
                   steps {
                sh 'cp target/pollscm3.war /home/ishika/Documents/devops_software/apache-tomcat-9.0.79/webapps'
                        }}
                stage('Docker build'){
                    steps {
                        sh 'docker build -t ishika21/pollscmimg .'
                        }}
                        stage('Container creation'){
                    steps {
                        sh 'docker run -it -d --name=container-pollscm ishika21/pollscmimg /bin/bash'
                        }}
