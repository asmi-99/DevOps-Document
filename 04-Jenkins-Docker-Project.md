1. Project Setup using below tools
      1. Maven
      2. Git Hub
      3. Jenkins
      4. Docker
         
Step-1 : Jenkins Server Setup in Linux VM
             1. Create Ubuntu VM using AWS EC2 (t2.medium)
             2. Enable 8080 Port Number in Security Group Inbound Rules
             3. Connect to VM using MobaXterm
             4. Install Java
                  sudo apt update
                  sudo apt install fontconfig openjdk-17-jre
                  java -version
                  
  Step-1a) : Install Jenkins
            1. sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
            https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
            2. echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
            https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
            /etc/apt/sources.list.d/jenkins.list > /dev/null
            3. sudo apt-get update
            4. sudo apt-get install jenkins
          
  Step-1b) : Start Jenkins
            1. sudo systemctl enable jenkins
            2. sudo systemctl start jenkins
            
  Step-1c) : Verify Jenkins
            1. sudo systemctl status jenkins
         
  Step-1d) : Access jenkins server in browser using VM public ip
            1. http://public-ip:8080/

  Step-1e) : Copy jenkins admin pwd
            1. sudo cat /var/lib/jenkins/secrets/initialAdminPassword
            
  Step-1f) : Create Admin Account & Install Required Plugins in Jenkins

Step-2 : Configure Maven as Global Tool in Jenkins
            1. Manage Jenkins -> Tools -> Maven Installation -> Add maven
            
Step-3 : Setup Docker in Jenkins
              curl -fsSL get.docker.com | /bin/bash
              sudo usermod -aG docker jenkins
              sudo usermod -aG docker ubuntu
              sudo systemctl restart jenkins
              sudo docker version
              
Step - 4 : Create Jenkins Job
              Stage-1 : Clone Git Repo
              Stage-2 : Maven Build
              Stage-3 : Create Docker Image
              Stage-4 : Create Docker Container
              
Step - 5 : Trigger Jenkins Job

Step - 6 : Enable host port in security group inbound rules

Step - 7 : Access Application in Browser

We should be able to access our application
URL : http://public-ip:port/

We are done with our Setup
Step - 8 : After your practise, delete resources we have used in AWS Cloud to avoid billing
