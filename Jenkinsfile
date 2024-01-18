pipeline {
    agent {
        label 'test-agent-a10'
    }

    stages {
        stage('Hello') {
            steps {
                sh 'echo "hello world"'
            }
        }
        stage('Build') {
            steps {
                script {
                    try {
                        sh "docker run --rm --name pyinstall python:2-alpine sh -c 'python -m py_compile sources/add2vals.py sources/calc.py' | tee test.log"
                    } catch (err) {
                        sh "docker stop pyinstall"
                        sh "docker rm pyinstall"
                    }
                }
            }
        }
    }
}
