 
node {
 

    stage('checkout source') {
        // when running in multi-branch job, one must issue this command
        checkout scm
    }
 
stage('Build') {
        // when running in multi-branch job, one must issue this command
       sh "AntDefault"
    }

   
}
