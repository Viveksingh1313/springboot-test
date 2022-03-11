# springboot-test
This is a project with minimal use case of a controller and test case. The repository is used in a CICD pipeline with Jenkins and Ansible


https://medium.com/appgambit/configure-jenkins-with-ansible-7bfaa387fb1c
https://medium.com/appgambit/build-pipeline-with-jenkins-c13bf788a3f0

https://github.com/ansible/ansible-examples


https://www.browserstack.com/guide/ansible-vs-jenkins -- good for usages of ansible like ansible tower




How to start ?
username password - root root
sudo systemctl start jenkins






















springboot test

do not build manually

push to git branch -
two cases
push with test cases - success
push without test cases - not success

build - run tests - run integration tests - sonarcube analysis - everything works fine ?
upload image on nexus - Ansible reads the image and deploys on which env(dev,int,prod)


https://forums.docker.com/t/linux-container-on-windows-docker-host/25884/2
https://www.cyberciti.biz/python-tutorials/linux-tutorial-install-ansible-configuration-management-and-it-automation-tool/ ----ansible


https://docs.microsoft.com/en-us/azure/developer/ansible/configure-in-docker-container?tabs=azure-cli ---ansible docker container
https://www.cyberciti.biz/python-tutorials/linux-tutorial-install-ansible-configuration-management-and-it-automation-tool/
https://vinodpandey.com/how-to-install-python3-on-centos-7/         ---------install python3.8
https://www.docker.com/docker-desktop/getting-started-for-windows   ---- docker desktop

https://computingforgeeks.com/install-sonarqube-code-review-centos/              ----------------- sonarqube on centons7 guide
You wont be able to run sonar with root user. You will have to create a user for that. Menitoned in the guide above.
Also remeber to provide all folder permissins to this user.  for more : https://stackoverflow.com/questions/47731102/cant-run-sonar-server-caused-by-elasticsearch-cannot-running-as-root
doesn't work with java8. Use java11 : https://sysadminxpert.com/steps-to-upgrade-java-8-to-java-11-on-centos-7/
Install this plugin on github which will connect sonar servers to your git - SonarQube Scanner plugin -- http://localhost:9000/documentation/analysis/jenkins/
sonar with jenkins pipeline : https://medium.com/@rosaniline/setup-sonarqube-with-jenkins-declarative-pipeline-75bccdc9075f
https://www.youtube.com/watch?v=PRpEbFZi7nI --- ansible on centos installation and setup
Add connection:local for no ssh on localhost run jar by ansible -- https://www.youtube.com/watch?v=muQmkzNL7B0




jenkins with ansible in windows ?
springboot unittest and integraiton test
sonarcube integration
nexus repository
ci

ansible
cd





https://itnext.io/ci-cd-with-jenkins-and-ansible-f41ef2b33977

https://isurunuwanthilaka.github.io/software-engineering/2021/02/18/docker-jenkins-ansible-automation.html




could have been done with docker where we push images to dockerhuib
email on build fails
ask for deployment on which envs ?


jenkins ****
vivek sinless1@

sonarqube user
sonar password


user centos
sonar password

sonarqube server
admin sonar



git  client secret - f248e38b1cfa47414504bac43d99a65baae33990

token to check in - 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


sonarqube token for git credrential integration






Failed to execute goal org.apache.maven.plugins:maven-resources-plugin:3.2.0:resources (default-resources) on project cicd:
The plugin org.apache.maven.plugins:maven-resources-plugin:3.2.0 requires Maven version 3.1.0



Failed to execute goal org.apache.maven.plugins:maven-resources-plugin:3.2.0:resources (default-resources) on project cicd:
The plugin org.apache.maven.plugins:maven-resources-plugin:3.2.0 requires Maven version 3.1.0 ->


Mailer plugin to setup mail services  - 
Mailer Plugin doc link - https://plugins.jenkins.io/mailer/
difference - https://stackoverflow.com/questions/52114233/what-is-difference-between-extended-email-notification-and-email-notification
medium link for UI setup - https://medium.com/@arun.dev/get-email-notification-for-jenkins-build-failure-and-success-d59154dc639a



Ansible with Jenkins had a few bugs on Windows. Works with all Linux system though.
I am using Centos, we can use any other Linux distributed OS. Should be fine. 


After creating a jar -> upload the jar to nexus repository-> Now Ansible picks that jar ->
Deploys it on our server -> triggers a jar start on server.

Sonarqube Analysis needs some work - Test case coverage needs to be setup using 
jecko(most used as far as I know, need to re-check ?). The advantage for this is -  
for any feature one is merging to tetc-dev branch, if the code coverage is less than
80% the merge request will fail because Jenkins while building that branch will fail it.
This rule needs to be configured in Sonarqube piepeline. 
(Need to read blogs, easily achievable though - 16-48 hours max)

Use CICD Blue Ocean pipeline because what I am using is legacy UI

Instead of choosing the environment to deploy in at the beginning, why not make this a
series of steps . Like :  clone -> build -> deploy dev-> deploy uat -> deploy prod
But this would not make sense for common branches. Makes sense for UAT or PROD
branch.

The servers keeps changing. So Jenkins,python, java, sonarqube installation & setup in a docker
image. Saves time, and makes the system fault tolerant.

Need to work on running server, and exiting the build without terminating the server.

