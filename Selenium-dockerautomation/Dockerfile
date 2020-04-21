FROM openjdk:8u191-jre-alpine3.8
#Workspace
WORKDIR /usr/share/dockerimage
#Add .jar under target from host into this image
ADD target/selenium-docker.jar selenium-docker.jar
ADD target/selenium-docker-tests.jar selenium-docker-tests.jar
ADD target/libs libs
#if you have test data files .csv/json/.xls,add them as well
#Add suite files
ADD book-flight-module.xml book-flight-module.xml
ADD searchmodule.xml searchmodule.xml
ENTRYPOINT java -cp selenium-docker.jar:selenium-docker-tests.jar:libs/* -DBROWSER=$BROWSER -DHUB_HOST=$HUB_HOST org.testng.TestNG $MODULE

