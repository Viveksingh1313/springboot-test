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