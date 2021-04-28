pipeline {

    agent any

    stages {
        stage('Build') {
            steps {
                echo "Build step"
                sleep 10
            }
            steps {
                echo "NOT SEQUENTIAL"
                sleep 10
            }
        } 
    } 
}
