pipeline {
    agent {
        docker {
            image 'python:2-alpine'
            label 'test-node-a800'
        }
    }
    environment {
        HTTP_PROXY = 'http://proxy-dmz.intel.com:911'
        HTTPS_PROXY = 'http://proxy-dmz.intel.com:912'
    }
    stages {
        stage('Build') {
            steps {
                sh 'python -m py_compile sources/add2vals.py sources/calc.py'
            }
        }
    }
}
