pipeline {

    agent any
    tools {
        maven 'maven_hypercode'
    }
    stages {
        stage('Compile stage') {
            steps {
                bat "mvn clean install"
        }
    }

         stage('testing stage') {
             steps {
                bat "mvn test"
        }
    }

          stage('deployment stage') {
              steps {
                bat "cf login -a http://api.run.pivotal.io -u gguzman@g.harvard.edu -p ReginaAdmin1805."
				bat "cf target -o hypercode -s development"	
				bat "cf push LibStatsHelper"
        }
    }

  }

}