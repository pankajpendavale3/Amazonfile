pipeline {

    agent any

    stages {

        stage('Git Pull') {

            steps {

                git branch: 'main',
                url: 'https://github.com/pankajpendavale3/Amazonfile.git'
            }
        }

        stage('Frontend Build') {

            steps {

                dir('frontend') {

                    sh 'npm install'
                    sh 'npm run build'
                }
            }
        }

        stage('Backend Build') {

            steps {

                dir('backend') {

                    sh 'npm install'
                }
            }
        }

        stage('Docker Build') {

            steps {

                sh 'docker-compose build'
            }
        }

        stage('Deploy') {

            steps {

                sh 'docker-compose down'
                sh 'docker-compose up -d'
            }
        }
    }
}
