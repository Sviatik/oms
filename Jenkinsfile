#!groovy
node {
	stage ('remove workspase') {
		deleteDir()
	}

    stage ('git') {
        git 'https://github.com/Sviatik/oms.git'
    }
    
    stage ('stage2') {
        echo 'HW1'
    }
        
    def mvnHome = tool 'M3'
    
//    stage ('build') {
//        sh "${mvnHome}/bin/mvn -DskipTests=true clean install"
//    }
    
    stage ('test') {
    	sh 'ssh root@10.129.132.88 "ls"'
    }
}

//sh 'scp target/OMS.war ec2-user@35.158.76.35:/usr/share/tomcat/webapps/'