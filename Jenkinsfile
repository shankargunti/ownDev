 
node {
 

    stage('checkout source') {
        // when running in multi-branch job, one must issue this command
        checkout scm
    }
 
            stage('hello') {
                steps {
                    sh 'echo "Hello World"'
                }
            }
       
stage('Build') {
        // when running in multi-branch job, one must issue this command
    steps {
     sh "AntDefault" 
    }
    }

   
}
