Stage 1:Create EC2 Instance

Stage 2: Install Jenkins

  Commands:
  
      sudo apt update
      sudo apt install default-jdk
      wget -q -O - https://pkg.jenkins.io/debian/jenkins.io.key | sudo apt-key add -
      sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
      sudo apt update
      sudo apt install jenkins
      sudo systemctl start jenkins
      sudo systemctl enable jenkins
      sudo systemctl status jenkins

    Get the Public IP Address and test ( ip address:8080 )
    copy password from sudo cat /var/lib/jenkins/secrets/initialAdminPassword and paste it in website.
    Install suggested plugins 
    Create user or skip


Stage 3: Install Docker:

  Commands: 
  
      sudo apt-get update
      sudo apt-get install docker.io -y
      sudo usermod -aG docker $USER   #my case is ubuntu
      newgrp docker
      sudo chmod 777 /var/run/docker.sock

  After the docker installation, we create a sonarqube container (Remember to add 9000 ports in the security group).
  
      docker run -d --name sonar -p 9000:9000 sonarqube:lts-community
      

      
      









