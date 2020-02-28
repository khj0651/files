FROM openjdk:8-jre-alpine

ENV JAR_FILE spring-music-1.0.0-SNAPSHOT.jar
ENV GW_HOME /app
WORKDIR $GW_HOME
RUN mkdir -p $GW_HOME/volumes
ENV DATABASE in-memory
ENV JAVA_OPTS "$JAVA_OPTS -Dspring.profiles.active=$DATABASE"

EXPOSE 8080
COPY spring-music/target/$JAR_FILE $GW_HOME/
ENTRYPOINT ["sh", "-c"]

CMD ["exec java $JAVA_OPTS -jar $JAR_FILE"]
