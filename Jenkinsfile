node {
try
{
	sh echo 'email testing'
}
catch (e) {
    // If there was an exception thrown, the build failed
    currentBuild.result = "FAILED"
    throw e
  } finally {
    // Success or failure, always send notifications
	notifyBuild(currentBuild.result)
}
}
def notifyBuild(String buildStatus = 'STARTED') {
  // build status of null means successful
	buildStatus =  buildStatus ?: 'SUCCESSFUL'
	def subject = "${buildStatus}: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]'"
    mail (to: 'tejaswini.koritala@gmail.com',
             subject: 'subject',
             body: '${SCRIPT, template="groovy-text.template"}, "Please go to ${env.BUILD_URL}."')
    }  
