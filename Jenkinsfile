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
    
    stage ('build') {
        sh "${mvnHome}/bin/mvn -DskipTests=true clean install"
    }
    
    stage ('deploy to remote host') {
    	sh 'sudo ssh -i /home/jenkins/aws.pem ec2-user@35.158.76.35 "ls"'
    }
}

//sh 'scp target/OMS.war ec2-user@35.158.76.35:/usr/share/tomcat/webapps/'