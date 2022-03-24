def version
def modifiedFiles
def skipBuild
node{
      stage("compile"){
            if (fileExists('app2')){
                  sh 'rm -r app2'
            }
            git credentialsId: 'FaizalGit', url: 'https://github.com/faizalgit/simpleproject'
            sh 'git clone https://github.com/faizalgit/app2'
	    sh 'mvn package'
      }
        
}
