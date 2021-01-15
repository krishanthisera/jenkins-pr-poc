pipeline{
    agent {
        kubernetes {
            yamlFile 'jenkins-build-template.yaml'
        }
    }
    environment {
        GIT_REPO = 'https://github.com/krishanthisera/jenkins-pr-poc.git'
    }
    stages{
        stage("Source Chekout"){
            steps{
                git credentialsId: 'git-fcc', url: "${GIT_REPO}"
            }
            post{
                success{
                    echo "Source Chekout completed"
                }
                failure{
                    echo "Error On Source checkout"
                }
            }
        }
        stage("Docker Build"){
            steps{
                echo "Building Image"
            }
            post{
                success{
                    echo "Building Image completed"
                }
                failure{
                    echo "Error On Building Image"
                }
            }
        }
        stage("Docker Image Shipping"){
            steps{
                echo "Shipping Image"
            }
            post{
                success{
                    echo "Shipping Image completed"
                }
                failure{
                    echo "Error On Shipping Image"
                }
            }
        }
        stage("Production Deployment"){
            steps{
                echo "Production Deployment"
            }
            post{
                success{
                    echo "Production Deployment completed"
                }
                failure{
                    echo "Error On Production Deployment"
                }
            }
        }
    }
    post{
        always{
            echo "Pipeline Executed"
        }
        success{
            echo "Pipeline Execution Competed"
        }
        failure{
            echo "Pipeline Execution Failed"
        }
    }
}