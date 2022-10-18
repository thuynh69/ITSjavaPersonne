pipeline{
    agent any

    stages{
        stage('Clone') {
            steps {
                script {
                    git credentialsId: 'thuynh69', url: 'https://github.com/thuynh69/ITSjavaPersonne.git'
                    echo 'Clone du repo réussi'
                }
            }
        }
        stage('Clean') {
            steps {
                sh 'mvn clean'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn package'
                echo 'Build success'
            }
        }
        stage('Run') {
            steps {
                sh "java -jar ${env.WORKSPACE}/target/itsjavapersonne-0.1.jar"
                echo 'Run success'
            }
        }
    }
}