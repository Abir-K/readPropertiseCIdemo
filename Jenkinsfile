pipeline {
    agent any
    
    environment {
        IMAGE = readMavenPom().getArtifactId()
        VERSION = readMavenPom().getVersion()
    
    }

    stages {
        stage('Reading POM') {
            steps {
                echo "The version is: ${VERSION}"
                echo "The image : ${IMAGE}"
            }
        }
        stage('Reading Propertise File') {
            steps {
                script {
                   prop = readPropertise file: 'demofile.propertise'
                   echo "Name of the app is : ${prop['app.name']}"
                   echo "Build environment : ${prop['environment.name']}"
                   echo "Version is : ${prop['app.version.number']}"
                
                }
            }
        }
        
    }
}
