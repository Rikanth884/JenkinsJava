pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                echo 'Building Java Application'

                sh 'javac Hello.java'

                echo 'Build Completed Successfully'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing Java Application'

                sh 'java Hello > output.txt'

                sh 'grep "Jenkins CI Pipeline" output.txt'

                echo 'Test Completed Successfully'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying Java Application'

                archiveArtifacts artifacts: '*.class,output.txt'

                echo 'Deployment Completed Successfully'
            }
        }
    }
}
