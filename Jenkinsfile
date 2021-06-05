pipeline{
    agent { label 'master'}
    tools {
        maven 'maven3'
    }
    stages{
        stage('Maven Build'){
            when {
                branch 'develop'
            }
            steps{
                sh "mvn clean package"
            }
        }
        stage('Upload to Nexus'){
            when {
                branch 'develop'
            }
            steps{
                nexusArtifactUploader artifacts: [
                        [artifactId: 'multibranch', classifier: '', file: 'target/*.war', type: 'war']
                    ], 
                    credentialsId: 'nexus3', 
                    groupId: 'devops.shaikmoula', 
                    nexusUrl: 'http://52.66.233.131:8081', 
                    nexusVersion: 'nexus3', 
                    protocol: 'http', 
                    repository: 'shaikmoula-devops-snapshot', 
                    version: '1.0'
            }
        }

        stage('Deploy to Dev'){
            when {
                branch 'develop'
            }
            steps{
                echo "coming soon.."
            }
        }

        stage('Deploy to QA'){
            when {
                branch 'release'
            }
            steps{
                echo "coming soon.."
            }
        }

        stage('Deploy to Prod'){
            when {
                branch 'master'
            }
            steps{
                echo "coming soon.."
            }
        }

    }
