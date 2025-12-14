pipeline {
    agent any

    triggers {
        githubPush()   
    }

    stages {

        stage('Clone') {
            steps {
                git branch: 'main', url: 'https://github.com/MouadBensafir/cargo-tracker'
            }
        }

        // Changement pour le webhook

        stage('Build & Test') {
            steps {
                bat 'mvn clean verify'
            }
        }

    }

    post {
        success {
            echo 'Build et analyse terminés avec succès !'
        }
        failure {
            echo 'Échec du build ou des tests.'
        }
    }
}
