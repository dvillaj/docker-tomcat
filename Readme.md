docker build -t tomcat8 .
docker tag tomcat8 dvillaj/tomcat8:latest
docker push dvillaj/tomcat8:latest



oc delete project tomcat8
oc new-project tomcat8 --display-name='Tomcat 8'
oc new-app dvillaj/tomcat8:latest

oc expose service tomcat8
oc status
