## Apache Web & Application Server on Docker

FILES TO EDIT FIRST:
1. httpd/security.conf  - scroll to end and modify to match where you want parent container to execute from
2. httpd/jk.conf - modify if you want a different project other than the war file for iframetest2
3. httpd/000-default.conf - modify if you want a different projeccct other than war file for iframetest2
4. tomcat/iframetest2.war <- change this if you want to use a different war file


Running 'docker-compose up' will invoke two Docker containers
- An Apache Tomcat container that will host a sample web application.
- An Apache HTTPD container that will run the httpd web server with mod_jk configuration. 

Mod_jk configurations will be pointing the backend to the tomcat container which will have it's AJP connector port exposed. As per Docker compose version 2 by default every container is reachable via other containers, hence the backend host i.e. Apache Tomcat will be already reachable from HTTPD. 

Apache HTTPD's port 80 will be mapped to base machine's port 80
```
http://localhost/ - apache sample
http://localhost/iframetest2/ -- embed test jsp page invoked by mod_JK from Apache Tomcat
