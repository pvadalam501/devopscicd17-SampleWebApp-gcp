# ⚠️  Image pulled from Google Artifact Registry at runtime.
# Base image: Tomcat 9 on JDK 17 (no AWS dependency)
FROM tomcat:9-jdk17

# Copy WAR into Tomcat webapps
WORKDIR /usr/local/tomcat/webapps

COPY target/WebApp.war .

# Replace default ROOT with our WAR so the app is served at /
RUN rm -rf ROOT && mv WebApp.war ROOT.war

# Expose Tomcat HTTP port
EXPOSE 8080

# Run Tomcat in foreground (required for Docker / GKE containers)
CMD ["catalina.sh", "run"]
