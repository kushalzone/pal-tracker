# pal-tracker
PIVOTAL Platform  Acceleration Lab - Sessions. 

###Commonly used commands

<pre>
====CLOUD FOUNDARY====
cf login -a api.run.pivotal.io
cf push
cf target -s review
cf create-service ${MYSQL_SERVICE_NAME} ${PLAN_NAME} tracker-database
cf target -s production
cf create-service ${MYSQL_SERVICE_NAME} ${PLAN_NAME} tracker-database
cf target -s review
cf bind-service pal-tracker tracker-database
cf target -s production
cf bind-service pal-tracker tracker-database
cf create-space review
cf create-space production

====FLYWAY COMMANDS====
flyway -url="jdbc:mysql://localhost:3306/tracker_dev" -locations=filesystem:databases/tracker clean migrate
flyway -url="jdbc:mysql://localhost:3306/tracker_test" -locations=filesystem:databases/tracker clean migrate


===LINUX COMMANDS==
apt search PACKAGE
sudo apt install git
brew install cloudfoundry/tap/cf-cli
!4 (Runs the 4th command from history)


====GRADLE COMMANDS====
./gradlew build
mkdir -p  ~/workspace/use-gradle
cd ~/workspace/use-gradle
gradle wrapper
./gradlew tasks
touch build.gradle
./gradlew sayHello sayGoodbye
./gradlew sH sG
./gradlew clean build --dry-run
./gradlew clean build

====Concourse FLY Commands====
fly --target pal-concourse login --concourse-url ${CONCOURSE_URL} --team-name ${TEAM_NAME}
fly -t pal-concourse set-pipeline -p pal-tracker --load-vars-from ci/variables.yml -c ci/pipeline.yml
fly -t pal-concourse destroy-pipeline -p pal-tracker
fly -t pal-concourse unpause-pipeline -p pal-tracker
fly set-pipeline
fly validate-pipeline
fly format-pipeline
fly pipelines
fly rename-pipeline
fly pause-pipeline
fly unpause-pipeline
fly expose-pipeline
fly hide-pipeline
fly get-pipeline
fly destroy-pipeline


</pre>
