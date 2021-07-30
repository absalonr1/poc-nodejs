FROM openjdk:11
COPY ./rest-service-complete-0.0.1-SNAPSHOT.jar /usr/app/
COPY ./dd-java-agent.jar /usr/app/
WORKDIR /usr/app
#ENTRYPOINT ["java", "-jar", "rest-service-complete-0.0.1-SNAPSHOT.jar"]
ENTRYPOINT ["java", "-javaagent:./dd-java-agent.jar", "-Ddd.profiling.enabled=true", "-Ddd.logs.injection=true", "-Ddd.trace.sample.rate=1", "-Ddd.service=my-app", "-Ddd.env=devlab", "-jar", "rest-service-complete-0.0.1-SNAPSHOT.jar", "-Ddd.version=1.0"]
