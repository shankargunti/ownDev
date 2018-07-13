 
node {
 

    stage('checkout source') {
        // when running in multi-branch job, one must issue this command
        checkout scm
    }
 
stage('Build') {
def antVersion = 'AntDefault'
withEnv( ["ANT_HOME=${tool antVersion}"] ) {
   bat '%ANT_HOME%/bin/ant.bat fetchChanges  deploy'
}
    }
}
  
