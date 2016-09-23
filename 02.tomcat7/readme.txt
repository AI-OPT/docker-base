docker build -t 10.19.13.18:5000/tomcat:7 .
docker push 10.19.13.18:5000/tomcat:7
docker run -d --name tomcat7  10.19.13.18:5000/tomcat:7 sleep 99999999
docker exec -it tomcat7 /bin/bash 