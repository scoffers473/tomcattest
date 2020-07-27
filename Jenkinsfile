pipeline {
    agent any
    stages {
        stage('Build Application') {
            steps {
                sh 'mvn -f ./pom.xml clean package'
            }
            post {
                success {
                    echo "Now Archiving the Artifacts...."
                    archiveArtifacts artifacts: '**/*.war'
                }
            }
        }
        stage('Feploy in Staging Environment') {
            nuild_job: 'Deploy_Application_Staging'
        }
    }
}