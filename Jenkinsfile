pipeline {
    agent {
        docker {
            image 'python:2-alpine'
            label 'test-node-a800'
        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'python -m py_compile sources/add2vals.py sources/calc.py'
            }
        }
    }
}
