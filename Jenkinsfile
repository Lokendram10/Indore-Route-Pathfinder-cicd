pipeline {
    agent any
    environment {
        SONARQUBE_SCANNER_HOME = tool 'SonarQubeScanner'
    
    }

    stages {
        stage('Clone') {
            steps {
                git url: 'https://github.com/Lokendram10/Indore-Route-Pathfinder-cicd.git', branch: 'main'
            }
        }
        stage('SonarQube Scan') {
            steps {
                withSonarQubeEnv('SonarQubeServer') {
                    sh ''' ${SONARQUBE_SCANNER_HOME}/bin/sonar-scanner \
                    -Dsonar.projectName=Indore-Route-Pathfinder-cicd \
                     -Dsonar.projectKey=Indore-Route-Pathfinder-cicd
                     '''
                }
                
            }
        }
        stage('OWASP Dependency Check') {
            steps {
                 echo "OWASP Dependency Check"
                 dependencyCheck (
                    additionalArguments: '--scan ./'
                    , odcInstallation: 'owasp'
                 )
                    echo "OWASP Dependency Check"
            }
        }
        stage('Trivy Scan') {
            steps {
                sh 'trivy fs --exit-code 1 --severity HIGH,CRITICAL -f json -o trivy-report.json . '
            }
        }
        stage('Quality Gate') {
            steps {
                timeout(time: 1, unit: 'HOURS') {
                    waitForQualityGate abortPipeline: true
                }
            }
        }
        stage('Docker Build') {
            steps {
                sh 'docker compose up --build -d'
            }
        }
    }
}