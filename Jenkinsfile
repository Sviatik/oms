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
        sshagent(['dbf4729e-28be-40e7-93a7-b87337ca396c']) {
    		sh 'ssh ec2-user@35.158.76.35'
		}
    }
}

//sh 'scp target/OMS.war ec2-user@35.158.76.35:/usr/share/tomcat/webapps/'