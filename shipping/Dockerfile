# FROM maven:3.6.2-jdk-11 AS build
# RUN mkdir /opt/server
# WORKDIR /opt/server
# COPY pom.xml .
# COPY src src
# RUN mvn clean package
# RUN cp target/shipping-1.0.jar shipping.jar

# FROM openjdk:17-alpine
# RUN adduser -D -h /opt/server roboshop \
#     && mkdir -p /opt/server \
#     && chown roboshop:roboshop /opt/server

# COPY --from=build /opt/server/shipping.jar /opt/server/shipping.jar

# WORKDIR /opt/server
# USER roboshop
# EXPOSE 8080

# CMD ["java","-jar","shipping.jar"]

# =========================
# Build stage
# =========================
# FROM maven:3.9.6-eclipse-temurin-17 AS build

# WORKDIR /opt/server

# COPY pom.xml .
# RUN mvn dependency:go-offline

# COPY src src
# RUN mvn clean package -DskipTests

# RUN cp target/shipping-1.0.jar shipping.jar


# # =========================
# # Runtime stage
# # =========================
# FROM eclipse-temurin:17-jre-alpine

# RUN adduser -D -h /opt/server roboshop \
#     && mkdir -p /opt/server \
#     && chown -R roboshop:roboshop /opt/server

# WORKDIR /opt/server

# COPY --from=build /opt/server/shipping.jar /opt/server/shipping.jar

# USER roboshop
# EXPOSE 8080

# CMD ["java", "-jar", "shipping.jar"]
FROM 384570460482.dkr.ecr.ap-south-1.amazonaws.com/platform/java-runtime:11-jre-alpine

WORKDIR /opt/server

COPY target/shipping-1.0.jar app.jar

CMD ["java", "-jar", "app.jar"]