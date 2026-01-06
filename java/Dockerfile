# ===============================
# Java Golden Runtime Image
# ===============================
FROM eclipse-temurin:17-jre-alpine

ENV JAVA_OPTS="-XX:+UseContainerSupport \
               -XX:MaxRAMPercentage=75.0 \
               -Djava.security.egd=file:/dev/./urandom"
LABEL org.opencontainers.image.source="platform-team" \
      org.opencontainers.image.description="Java Golden Runtime Image" \
      org.opencontainers.image.version="17-jre-alpine-v1"

RUN addgroup -S roboshop && \
    adduser -S roboshop -G roboshop && \
    mkdir -p /opt/server && \
    chown -R roboshop:roboshop /opt/server

WORKDIR /opt/server

USER roboshop

EXPOSE 8080

CMD ["sh", "-c", "java $JAVA_OPTS -jar app.jar"]
