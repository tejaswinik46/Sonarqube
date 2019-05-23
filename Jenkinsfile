node {
try
{
catch (e) {
    // If there was an exception thrown, the build failed
    currentBuild.result = "FAILED"
    throw e
  } finally {
    // Success or failure, always send notifications
	def subject = "${buildStatus}: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]'"
    mail (to: 'tkoritala@ameren.com',
             subject: "Job '${env.JOB_NAME}' (${env.BUILD_NUMBER}) Build is Success",
             body: '''${SCRIPT, template="groovy-text.template"}''', "Please go to ${env.BUILD_URL}.")
    }  
    }
    }
