import groovy.json.JsonSlurperClassic

def jsonParse(def json) {
    new groovy.json.JsonSlurperClassic().parseText(json)
}

pipeline {
    agent { label 'main' }
    environment {
        appName = 'my-app'
    }

    stages { // Estos son los pasos del pipeline
        stage('Paso 1') {
            steps {
                script {
                    sh "echo 'Hola mundo'"
                }
            }
        }
    }
    post { // Siempre se ejecuta al final del pipeline
        always {
            deleteDir()
            sh "echo 'Fase Always'"
        }
        success {
            sh "echo 'Fase Success'"
        }

        failure {
            sh "echo 'Fase Failure'"
        }
    }
}
