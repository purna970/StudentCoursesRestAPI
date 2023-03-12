pipeline {
    agent { label 'ubuntu' }
    triggers { 
        pollSCM('* * * * *')
    }
    stages {
        stage('vcs') {
            steps {
                git url: 'https://github.com/purna970/StudentCoursesRestAPI.git',
                    branch: 'sprint_branch'
            }
        }
        stage('build') {
            steps {
                sh 'docker image build -t poornaboda/spc:latest .'
            }
        }
        stage('scan and push') {
            steps {
                sh 'echo docker scan poornaboda/spc:latest'
                sh 'docker image push poornaboda/spc:latest'
            }
        }
    }

}