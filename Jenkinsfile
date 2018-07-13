 
node {
 

    stage('checkout source') {
        // when running in multi-branch job, one must issue this command
        checkout scm
    }
 
stage('Build') {
def antVersion = 'apache-ant-1.10.4'
withEnv( ["ANT_HOME=${tool antVersion}"] ) {
    sh '$ANT_HOME/bin/ant target1 target2'
}
    }
}
  
