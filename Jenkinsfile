pipeline {
    agent any
    
    
    triggers {
        cron('H/15 * * * *')   
        pollSCM('H/2 * * * *') 
    }

    stages {
        stage('Clone Repository') {
		steps { 	
                git branch: 'master', url: 'https://github.com/Aamirrazi/git-advanced-practical.git'
            }
        }
        stage('Build') {
            steps {
                bat 'echo "Building Project..."' 
 
            }
        }
        stage('Echo Build Status') {
            steps {
                echo "Build Status: SUCCESS" 
            }
        }
        stage('Archive Artifacts') {
            steps {
                 bat 'echo "Build Log Artifact" > build_artifact.log'
                archiveArtifacts artifacts: 'build_artifact.log', fingerprint: true
            }
        }
    }
}
