
 node  {
  stage 'Build and Test'
  env.PATH = "${tool 'AntDefault'}/bin:${env.PATH}"
  checkout scm
  sh 'ant build'
 }
