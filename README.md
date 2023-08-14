This is a sample Web Application project for  Continuous Integration/ Continous Delivery.
TOOLS used - Jenkins, Tomcat, Github, Sonarqube

#Tomcat Instruction
Configure your tomcat-users.xml file so that your user has sufficient permissions to deploy.

<role rolename="manager-script"/>
<role rolename="manager-jmx"/>
<user username="tomcat" password="s3cret" roles="manager-script,manager-jmx"/>
<role rolename="admin-gui" />
<user username="admin" password="Nikkikutti123#" roles="manager-gui,admin-gui" />
--------BEFORE ENDING TAG


Deploy ```target/poo.war``` on Tomcat
 

