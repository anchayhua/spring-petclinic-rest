# Versions control
mvn version:set -DnextSnapshot=true
mvn version:set -DnextVersion=true

# Docker
sonarqube      10.6.0-community                  
maven          3.8.8-eclipse-temurin-17-alpine   
artifactory-oss releases-docker.jforg.io/jfrog/artifactory-oss:7.77.14

# command
docker run -d -p 8081:8081 -p 8082:8082 --name artifactory-oss releases-docker.jfrog.io/jfrog/artifactory-oss:7.77.14
docker run -d -p 8083:8081 --name nexus sonatype/nexus3:3.72.0
## download manual nexus plugin jenkins and attach 