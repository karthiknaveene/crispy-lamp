pipeline {
    agent any

    stages {
        stage('Build') {
            stages {
                stage('Compile') {
                    steps {
                        echo 'Compiling...'
                        sleep 10
                    }
                }
                stage('Package') {
                    steps {
                        echo 'Packaging...'
                        sleep 5
                    }
                }
            }
        }

        stage('Registering build artifact') {
            steps {
                echo 'Registering the metadata'
                echo 'Another echo to make the pipeline a bit more complex'
                registerBuildArtifactMetadata(
                    name: "KN-artifact-1",
                    version: "1.0.1",
                    type: "docker",
                    url: "http://localhost:1111",
                    digest: "6f637064707039346163663237383938",
                    label: "preprod,test"
                )
                registerBuildArtifactMetadata(
                    name: "KN-artifact-2",
                    version: "1.0.1",
                    type: "docker",
                    url: "http://localhost:222",
                    digest: "7f637064707039346163663237383938",
                    label: "nort,south"
                )
                registerBuildArtifactMetadata(
                    name: "KN-artifact-3",
                    version: "1.0.1",
                    type: "docker",
                    url: "http://localhost:333",
                    digest: "8f6370647070393463663237383938",
                    label: "ease,west"
                )
            }
        }

        stage('Test') {
            steps {
                echo 'Running Unit Tests...'
                sleep 10
                echo 'Running Integration Tests...'
                sleep 5
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying...'
                sleep 5
            }
        }
    }
}
