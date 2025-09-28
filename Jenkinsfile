pipeline{
    agent {
        node {
            label "ubuntu && java21"
        }
    }
    stages {
        stage("hello"){
            steps{
                echo("hello pipeline")
            }
        }
    }

    post {
        always {
            echo "This will always run"
        }
        success {
            echo "This will run only if successful"
        }
        failure {
            echo "This will run only if failed"
        }
        unstable {
            echo "This will run only if the run was marked as unstable"
        }
        changed {
            echo "This will run only if the state of the pipeline has changed"
        }
    }
}