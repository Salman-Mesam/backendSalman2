FROM openjdk:8 as build
CMD ["chmod -r 777 ."] 
CMD ["chown -R :root ."]
CMD ["pwd"]
COPY springboot-backend/src /home/app/src
COPY springboot-backend/pom.xml /home/app
ENV my_env springboot-backend
WORKDIR "/home/app"
CMD ["./mvnw clean install"]

ENV APP_HOME /usr/src/app
COPY  $my_env/Tfix/springboot-backend-0.0.1-SNAPSHOT.jar $APP_HOME/app.jar
WORKDIR $APP_HOME
ENTRYPOINT ["java" , "-jar" , "app.jar"]
