#!groovy
node {
	stage ('remove workspase') {
		deleteDir()
	}

	stage ('remove deploy workspase') {
		sh "sudo rm -rf /usr/share/tomcat/webapps/OMS*"
	}


    stage ('git') {
        git 'https://github.com/Sviatik/oms.git'
    }
        
    def mvnHome = tool 'M3'
    
    stage ('build') {
        sh "${mvnHome}/bin/mvn -DskipTests=true clean install"
    }

	stage ('deploy') {
        sh "sudo cp target/OMS.war /usr/share/tomcat/webapps"
    }
}

//sh 'scp target/OMS.war ec2-user@35.158.76.35:/usr/share/tomcat/webapps/'