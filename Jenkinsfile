pipeline {

    agent { 
        label 'built-in' 
    }

    stages {

        stage ("Deploy App") {
            steps {
                script {
                    //    sh "helm repo update"
                        sh "helm upgrade --install app-release ./Chart.yaml -f values.yaml --insecure-skip-tls-verify --kube-insecure-skip-tls-verify"                
            }
        }
    }
    }

    post {
        success {
            echo "========================================================="
            echo " App Helm Deployment completed successfully!"
            echo "========================================================="
        }
        failure {
            echo "========================================================="
            echo "Deployment failed. Please check the logs and resources."
            echo "========================================================="
        }
    }
}
