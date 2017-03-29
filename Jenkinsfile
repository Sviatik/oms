#!groovy
node {
    stage 'git'
        git 'https://github.com/Sviatik/oms.git'
    stage 'stage2'
        echo 'HW1'
        
    def mvnHome = tool 'M3'
    
    stage 'build'
        sh "${mvnHome}/bin/mvn -DskipTests=true clean install"
    
    stage 'deploy'
        sh 'cp target/OMS.war /usr/share/tomcat/webapps/'

}