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

	stage ('test1') {
		sshagent(['a5d4ee19-dcd1-4ef3-b27f-8ba729d0a430']) {
			sh 'ls -la'
		    sh 'ssh -o StrictHostKeyChecking=no -l root@10.129.132.76 uname -a'
		}    
	}
}
//sh 'scp target/OMS.war ec2-user@35.158.76.35:/usr/share/tomcat/webapps/'