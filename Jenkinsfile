pipeline {

    agent any
        

    stages {

        stage('Checkout') {

            steps {

                // Checkout code from the branch

                checkout scm

            }

        }

 

        stage('Build and Run ') {

            steps {

                script {



                        sh 'python test.py' // Replace with your actual run command

                }

            }

        }


        stage('Code Analysis with Horusec') {

            steps {

                script {

                    sh 'curl -fsSL https://raw.githubusercontent.com/ZupIT/horusec/main/deployments/scripts/install.sh | bash -s latest'
                    sh 'horusec start -p="./" --disable-docker="true"'

                }

            }

        }

    }

}
