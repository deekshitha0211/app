mkdir mydockerfile
cd mydockerfile
cp /var/lib/jenkins/workspace/Package/target/addressbook.war .
touch dockerfile
cat <<EOT>> dockerfile
FROM tomcat
MAINTAINER Deekshitha
ADD addressbook.war /usr/local/tomcat/webapps
EXPOSE 8080
CMD ["catalina.sh", "run"]
EOT
docker build -t myimage:$BUILD_NUMBER .
docker run -itd -P myimage:BUILD_NUMBER
