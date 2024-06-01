pipeline {
    agent any
 parameters { 
    choice(name: 'BRANCH_TO_BUILD', choices: ['war', 'jar'], description: '') 
	string(name: 'MAVEN_GOAL', defaultValue: 'mvn install', description: 'maven build')
}
triggers { pollSCM('* * * * *') }

    stages {
        stage('SCM') {
            steps {
                git branch: "${params.BRANCH_TO_BUILD}", url: 'https://github.com/awskaizen02/May26.git'
            }
        }
        stage('build') {
            steps {
                bat "${params.MAVEN_GOAL}"
            }
        }
       
    }
}
