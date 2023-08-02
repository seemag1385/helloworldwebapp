node{

   def tomcatWeb = 'c:\\tomcat\\webapps'
   def tomcatBin = 'c:\\tomcat\\bin'
   def tomcatStatus = ''
   stage('SCM Checkout'){
      git 'https://github.com/seemag1385/helloworldwebapp.git'
   }
  stage( 'Compile-Package-create-war-file'){
    // Get maven home path
    def mvnHome = tool name: 'Maven' , type: 'maven'
    bat "${mvnHome}/bin/mvn package"
  }
  stage('Deploy to tomcat '){
    bat "copy target\\JenkinsPipeline.war \"${tomcatWeb}\\JenkinsPipeline.war\""
  }
  stage('start Tomcat Server'){
    sleep(time:5,unit:"SECONDS")
    bat "${tomcatBin}\\startup.bat"
    sleep(time:100,unit:"SECONDS")
  }
}

    
