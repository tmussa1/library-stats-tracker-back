pipeline {

    agent any
    tools {
        maven 'maven_hypercode'
    }
    stages {
        stage('Compile stage') {
            steps {
                bat "mvn clean compile"
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
				bad "cd target"
				bat "cf push LibStatsHelper -p LibStatsHelper-0.0.1-SNAPSHOT.jar"
        }
    }

  }

}