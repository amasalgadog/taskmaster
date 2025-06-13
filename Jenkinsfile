pipeline {
    agent any

    tools{
        maven 'Maven 3.9.10'
        jdk 'JDK 21'
    }

    stages{
        stage('Clonar'){
            steps{
                git 'https://github.com/amasalgadog/taskmaster.git'
            }
        }

        stage('Compilar'){
            steps{
                sh 'mvn clean compile'
            }
        }

        stage('Testear'){
            steps{
                sh 'mvn test'
            }
        }

        stage('Empaquetar'){
            steps{
                sh 'mvn package'
            }
        }

        post{
            success{
                echo "El build fue exitoso"
            }

            failure{
                echo "El build falló"
            }
        }
    }
}