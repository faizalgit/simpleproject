def version
def modifiedFiles
def skipBuild
def tomcatBin
def deployPath
def targetServer
node{
	
      	stage("compile"){
            if (fileExists('simpleproject')){
                  sh 'rm -r simpleproject'
            }
            git credentialsId: 'FaizalGit', url: 'https://github.com/faizalgit/simpleproject'
            sh 'git clone https://github.com/faizalgit/simpleproject'
	    sh 'mvn package'
	    nexusArtifactUploader artifacts: [[artifactId: 'simpleproject', classifier: '', file: 'target/simpleproject.war', type: 'war']], credentialsId: 'nexus-upload', groupId: 'com.simpleproject', nexusUrl: '104.196.30.112:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'maven-nexus-repo', version: 'v1'
	
      	}
	stage("deploy"){
		env.targetServer='34.142.247.158'
		tomcatBin='/opt/tomcat/bin'
		deployPath='/opt/tomcat/webapp'
		sshagent(['tomcatID']) {
    			echo env.targetServer
			sh 'ssh tomcat@"env.targetServer" hostname '
		
		}
		
		//dir("$deployPath") {
    		//	sh 'curl http://104.196.30.112:8081/repository/maven-nexus-repo/com/simpleproject/simpleproject/v1/simpleproject-v1.war'
		//}
		//sshagent(['tomcatID']) {
    		
		//	sh 'ssh tomcat@env.targetServer hostname'
		
		//}
	}
     
}
