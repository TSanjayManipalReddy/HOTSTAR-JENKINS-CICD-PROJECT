pipeline {

    agent any

    stages {

        stage('Checkout-Code') {
            steps {
                git 'https://github.com/Milky19/java-maven-project-new.git'
            }
        }

        stage('Compile-Project') {
            steps {
                sh 'mvn clean compile'
            }
        }

        stage('Test-Project') {
            steps {
                sh 'mvn test'
            }
        }

        stage('SonarQube-Scanning') {
            steps {
                withSonarQubeEnv('SonarQube') {
                    sh 'mvn org.sonarsource.scanner.maven:sonar-maven-plugin:3.7.0.1746:sonar'
                }
            }
        }

        stage('Package-Project') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Upload-to-Nexus') {
            steps {
                nexusArtifactUploader(
                    artifacts: [[
                        artifactId: 'myapp',
                        classifier: '',
                        file: 'target/myapp.war',
                        type: 'war'
                    ]],
                    credentialsId: 'NEXUS',
                    groupId: 'in.krishna',
                    nexusUrl: '3.109.2.51:8081',
                    nexusVersion: 'nexus3',
                    protocol: 'http',
                    repository: 'HOTSTAR',
                    version: '8.3.3-SNAPSHOT'
                )
            }
        }

        stage('Deployment') {
            steps {
                deploy(
                    adapters: [
                        tomcat9(
                            alternativeDeploymentContext: '',
                            credentialsId: 'apache-tomcat',
                            path: '',
                            url: 'http://13.233.199.81:8080'
                        )
                    ],
                    contextPath: 'myapp',
                    war: 'target/myapp.war'
                )
            }
        }
    }
}
