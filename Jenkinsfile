pipeline {
    agent any

    stages {
        stage('Resolve dependencies') {
            steps {
                sh 'npm install'
            }
            
        }
        stage('Black Duck Hub Scan') {
            steps {
                sh """#!/usr/bin/env bash
                    bash <(curl -s https://blackducksoftware.github.io/hub-detect/hub-detect.sh) \
                    --blackduck.hub.url=https://my.hub.server.com \
                    --blackduck.hub.username=username \
                    --blackduck.hub.password=password \
                    --detect.project.name=Black_Duck_Sample \
                    --detect.project.version.name=1.0 \
                    --detect.hub.signature.scanner.disabled=true
                """
            }
        }
    }
}