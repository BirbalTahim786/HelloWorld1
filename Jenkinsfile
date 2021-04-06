pipeline{
    agent any
    tools{
        maven 'Maven'
    }
    stages{
    stage('checkout'){
        steps{
        checkout scm
    }
    }
    stage('Build'){
    steps{
        bat 'mvn clean'
        bat 'mvn install'
    }
    }
    stage('unit test'){
    steps
        {
        bat 'mvn test'
    }
}
stage('Sonar Analysis'){
    steps
        {
            withSonarQubeEnv('Test_Sonar')
            {
                bat 'mvn org.sonarsource.scanner.maven:sonar-maven-plugin:3.2:sonar'
            }
        
    }
}
}
post{
    success{
        bat 'echo i am success'
    }
    
}
}
