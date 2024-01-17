pipeline {
    agent {
        docker {
            image 'python:2-alpine'
            label 'test-agent-a10'
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
