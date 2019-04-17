@Library(['github.com/selvakumardreams/jenkins-pipeline-library']) _

pipeline {
    agent { label 'nodelabel' }

    options {
        timeout(time: 60, unit: 'MINUTES')
        timestamps()
        buildDiscarder(logRotator(numToKeepStr: '5'))
    }

    stages {

        stage('Clean Workspace') {
            steps {
                // Clean the workspace
            }
        }

        stage('Checkout') {
            steps {
                // clone your project
            }
        }

        stage('Build') {
            steps {
                // build
            }
        }

        stage('Test') {
            steps {
                // Test (Unit test / Automation test / etc.)
            }
        }

        stage('Static Analysis') {
            steps {
                // Static Code analysis (CppCheck / SonarQube / etc.)
            }
        }

        stage('Release') {
            steps {
                // release (Snapshot / release / etc.)
            }
        }

        stage('Tag') {
            steps {
                // Tag 
            }
        }

        stage('Deploy') {
            steps {
                // Deploy to artifactory / drive etc.
            }
        }
    }

    post {
        success {
            echo "SUCCESS"
        }
        unstable {
            echo "UNSTABLE"
        }
        failure {
            echo "FAILURE"
        }
        changed {
            echo "Status Changed: [From: $currentBuild.previousBuild.result, To: $currentBuild.result]"
        }
        always {
            script {
                def result = currentBuild.result
                if (result == null) {
                    result = "SUCCESS"
                }
            }
        }
    }

}
