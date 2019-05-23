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
	buildStatus =  buildStatus ?: 'SUCCESSFUL'
	def subject = "${buildStatus}: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]'"
    mail (to: 'tkoritala@ameren.com',
             subject: subject,
             body: '''${SCRIPT, template="groovy-text.template"}''', "Please go to ${env.BUILD_URL}.")
    }  
    }
