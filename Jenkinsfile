pipeline {
    agent any
    tools {
             maven "M399"
    }
    stages {
        stage("Echo version") {
            steps {
                sh "echo Print maven version"
                sh "mvn --version"
            }
        }
        stage("Build"){
            steps {
                git 'https://github.com/dstar55/docker-hello-world-spring-boot.git'
                sh "mvn clean package -DskipTests=true"
            }
        }
        stage("Test"){
            steps {
                script {
                    for(int i=0; i<60; i++) {
                        echo "${i + 1}"
                        sleep 1
                    }
                }
                sh "echo NO TESTS"
            }
        }
    }
}
