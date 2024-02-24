1. Setup Linux VM (Amazon Linux / Ubuntu)
    1.Login into AWS Cloud account
    2.Create Linux VM and connect to it using MobaXterm
2. Install Docker In Amazon Linux VM
    sudo yum update -y 
    sudo yum install docker -y
    sudo service docker start
    sudo usermod -aG docker ec2-user
    exit
3. Install Docker In Ubuntu VM
    sudo apt update
    curl -fsSL get.docker.com | /bin/bash
    sudo usermod -aG docker ubuntu 
    exit
4. Verify docker installation
    docker -v
