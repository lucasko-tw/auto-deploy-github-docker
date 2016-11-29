
Automatic Deployment from Github to Docker
==============================

### Shell script

```SH
#!/bin/sh

git clone https://username:password@github.com/lucasko-tw/SpringMVC.git

mvn package -f ./SpringMVC

cp ./SpringMVC/target/SpringMVC-Web.war ./

docker build -t tomcat:mvc . 

docker run -d -p 80:8080 tomcat:mvc
