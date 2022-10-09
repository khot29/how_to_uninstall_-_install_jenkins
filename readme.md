# installing jenkins with docker on amazon linux
```
- step 1 : sudo yum install docker 
- step 2 : sudo systemctl enable docker
- step 3 : sudo systemctl start docker
- step 4 : sudo docker pull jenkins/jenkins
- step 5 : sudo docker run -dt --name jenkins -p 8080:8080 jenkins/jenkins
- step 6 : go to the inbound rule and add custom tcp in type and 8080 as a port range
- step 7 : open your browser and copy your public ip  
           example: your public ip -----> http://23.11.132.159/ add 8080 to it http://23.22.127.153/8080 done!.
- step 8 : for the password do not cat /var/jenkins_home/secrets/initialAdminPassword 
           do this -----------> docker log jenkins 
           [ note at the bottom you will get its password it will look like this f7d7e0eaa2414668a43b7203b3e596ea ]
```


# AWS Ubuntu VM Provisioning steps
```
-	Step 1:  Click on Launch Instance 
-	Step 2 : Click on Software Image (AMI)
-	Select Ubuntu 
-	Step 4: Key pair name â required
-	Click on Create new key pair
-	Put key pair name Jenkins-sl
-	& Download it 
-	Step 5 : Click on Launch Instance 
-	Step 6 : Select your VM and Click connect 
-	Step 7 :  You can see the terminal 
-	Step: Showing Github example
```
# To get into jenkins xml file 
```
sudo vi /var/lib/jenkins/config.xml
```

## GIT & Ubuntu SSH connection
```
ssh-keygen 

"Hit enter button 3 time"

cat ~/.ssh/id_rsa.pub 
git clone git@github.com:manikcloud/Jenkins-cicd.git
history 
history | cut -c 8- 
```

# JENKINS INSTALLATION on UBUNTU 18.04, for Ubunt 22.04 please skip the step 3 & 4
```
sudo apt-get update
sudo apt install openjdk-8-jdk
sudo apt install ca-certificates
sudo wget -q -O - https://pkg.jenkins.io/debian/jenkins.io.key | sudo apt-key add
sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
sudo apt-get update
sudo apt install jenkins
sudo /etc/init.d/jenkins start
sudo service jenkins status 
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
history | cut -c 8- 

```
# Jenkins URL with port 8080
- http://x.x.x.x:8080/

replace x with your ip 

# Change Security group rule for Jenkins 
```
-	Select your instance 
-	Down below select your security tab 
-	Click on the Security groups sg-0c51908b5fa4abf75 (launch-wizard-2)
-	Click on the action 
-	Click on EDIT INBOUND RULE
-	Select custom TCP and put port 8080
-	Custom ip should be 0.0.0.0/0
-	Click on Save the rule
```


