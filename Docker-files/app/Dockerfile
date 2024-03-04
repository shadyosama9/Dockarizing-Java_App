FROM openjdk:11 AS BUILDING_IMAGE


# Installing Services
RUN apt update && apt install maven git -y && apt clean && rm -rf /var/lib/apt/lists/*
# Cloning The Repo
RUN git clone "https://github.com/Shady-10/Vprofile-Project.git"
# Building The Artifact
WORKDIR /Vprofile-Project
RUN git checkout containers && mvn install

FROM tomcat:9-jre11

LABEL "Author"="Shady Osama"
LABEL "Project"="Vprofile"

# Deploying The Artifact
RUN rm -rf /usr/local/tomcat/webapps/*
COPY --from=BUILDING_IMAGE Vprofile-Project/target/vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war

EXPOSE 8080
CMD ["catalina.sh", "run"]




