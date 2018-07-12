Jenkins 1.535 and above is built with an internal web container called Jetty.

- How to restart Jenkins manually?
To restart Jenkins via url, you can use either of the following commands:
(jenkins_url)/safeRestart - Allows all running jobs to complete. New jobs will remain in the queue to run after the restart is complete.
(jenkins_url)/restart - Forces a restart without waiting for builds to complete.
(jenkins_url)/reload - To reload the configuration.

- Move jobs between 2 different Jenkins servers? 
Go to $JENKINS_HOME/jobs
Copy the files from Server1 to Server2 Job location and reload the server2.

- Can't su to user jenkins after installing Jenkins
jenkins is a service account, it doesn't have a shell by design. It is generally accepted that service accounts shouldn't be able to log in interactively.
if for some reason you want to login as jenkins, you can do so with: sudo su -s /bin/bash jenkins or you can edit /etc/passwd file and search for jenkins user
and replace /sbin/nologin --> /bin/bash

- jenkins on different port rather than 8080 using command prompt in Windows/linux?
Use the following command at command prompt:
	java -jar jenkins.war --httpPort=9090
If you want to use https use the following command:
	java -jar jenkins.war --httpsPort=9090
 