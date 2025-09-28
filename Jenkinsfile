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
        stage("build"){
            steps{
                // echo("build project 1")
                // echo("build project 2")
                // echo("Sleep for 5 seconds")
                // sleep 5
                // echo("build project 3")
                script {
                    for(i=0; i<3; i++){
                        echo("build project ${i}")
                    }
                }
                echo("Start build with maven")
                sh "java -version"
                sh "./mvnw clean compile test"
                echo("Build finished")
            }
        }
        stage("test"){
            steps{
                echo("test project")
            }
        }
        stage("deploy"){
            steps{
                echo("deploy project")
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