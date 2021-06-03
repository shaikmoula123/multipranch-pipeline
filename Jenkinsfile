
pipeline{
    agent any
    stages{
        stage("Dev Deploy"){
            when {
                branch "dev"
            }
            steps{
                echo "deploy to dev"
                  stage("uat Deploy"){
            when {
                branch "uat"
            }
            steps{
                echo "deploy to uat"
                  stage("main Deploy"){
            when {
                branch "main"
            }
            steps{
                echo "deploy to main"

            }
        }
    }
}
