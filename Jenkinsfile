
echo 'Deployemnt in Dev'

stage 'Dev'

node {
  import maven.json.JsonOutput
  git credentialsId: 'OrangeExim', url: 'https://github.com/MdAfzalAnsari/Mavendemo.git'
  def mvnHome = tool 'M3'
  bat "${mvnHome}\\bin\\mvn install -Dmaven.test.skip=true"
  dir('target') {stash name: 'jar', includes: '/*.jar'}
  // Add whichever params you think you'd most want to have
  // replace the slackURL below with the hook url provided by
  // slack when you configure the webhook
  def notifySlack(text, channel) {
      def slackURL = 'https://jenkinschannel.slack.com/services/hooks/jenkins-ci/'
      def payload = JsonOutput.toJson([text      : text,
                                       channel   : channel,
                                       username  : "jenkins",
                                       icon_emoji: ":jenkins:"])
      sh "curl -X POST --data-urlencode \'payload=${payload}\' ${slackURL}"
  }
}
