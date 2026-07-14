pipeline {

    stages {

        stage ("Deploy App") {
            steps {
                script {
                    container('gcloud-helm') {
                        sh "helm repo update"
                        sh "helm upgrade --install app release argocd-training -f values.yaml"

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
}
