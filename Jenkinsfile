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
//    stage ('test1') {
//    	sh 'ssh-keyscan 10.129.132.88 >> ~/.ssh/known_hosts'
//    }


	sshagent(['44e0a983-236b-4640-802c-71880878ede0']) {
	    sh 'ls'
	}    


    stage ('test2') {
    	sh 'ssh root@10.129.132.88 "ls"'
    }
}

//sh 'scp target/OMS.war ec2-user@35.158.76.35:/usr/share/tomcat/webapps/'