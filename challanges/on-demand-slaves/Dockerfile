FROM centos:7

MAINTAINER <Savio Mathew>

#the USER will be root by default just explicitly 
#expressing it for better documentation
USER root

# Checking for updates
RUN yum update -y 

RUN yum install -y \
    git \
	maven \
    wget \
    openssh-server \
    java-1.8.0-openjdk 

# Creating a dummy key 
RUN /usr/bin/ssh-keygen -A

# Add user jenkins to the image
RUN useradd jenkins -m -s /bin/bash

# Set password for the jenkins user
RUN echo "jenkins:jenkins@123" | chpasswd

# Set SSH Configuration to allow remote logins 
RUN sed -ri 's/^session\s+required\s+pam_loginuid.so$/session optional pam_loginuid.so/' /etc/pam.d/sshd

#setup permissions for the new folders and files
RUN chown -R jenkins:jenkins /home/jenkins

# Adding the jenkins user to sudoers
RUN echo "jenkins  ALL=(ALL)  ALL" >> etc/sudoers

# Expose SSH port and run SSHD
EXPOSE 22

#Technically, the Docker Plugin enforces this call when it starts containers by overriding the ENTRY command. 
CMD ["/usr/sbin/sshd","-D"]