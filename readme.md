## installing jenkins with docker on amazon linux

- step 1 : sudo yum install docker 
- step 2 : sudo systemctl enable docker
- step 3 : sudo systemctl start docker
- step 4 : sudo docker pull jenkins/jenkins
- step 5 : sudo docker run -dt --name jenkins -p 8080:8080 jenkins/jenkins
- step 6 : go to the inbound rule and add custom tcp in type and 8080 as a port range
- step 7 : open your browser and copy your public ip  
           example: your public ip -----> http://23.11.132.159/ add 8080 to it http://23.22.127.153/8080 done!.
- step 8 : for the password do not cat /var/jenkins_home/secrets/initialAdminPassword 
           do this -----------> docker logs jenkins 
           [ note at the bottom you will get its password it will look like this f7d7e0eaa2414668a43b7203b3e596ea ]

## To uninstall jenkins 
```
sudo apt-get remove --purge jenkins
```

## To get into jenkins xml file 
```
sudo vi /var/lib/jenkins/config.xml
```

## To change jenkins running port 
```
sudo vi /etc/default/jenkins
```


## jenkins installation on ubuntu 
```
sudo apt update

java -version

sudo apt install openjdk-11-jdk-headless

java -version

curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee /usr/share/keyrings/jenkins-keyring.asc > /dev/null

echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] https://pkg.jenkins.io/debian-stable binary/ | sudo tee /etc/apt/sources.list.d/jenkins.list > /dev/null

sudo apt update

sudo apt install jenkins

sudo systemctl start jenkins.service

sudo systemctl status jenkins

sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```

## Change Security group rule for Jenkins 
```
 Select your instance 
 Down below select your security tab 
 Click on the Security groups 
 Click on the action 
 Click on edit inbound rule
 Select custom TCP and put in which you have to run jenkins
 Custom ip should be 0.0.0.0/0
 Click on Save the rule
```


