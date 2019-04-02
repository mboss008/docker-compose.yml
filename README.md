# docker-compose.yml
installation
version: '2'



services:

  httpd:

    container_name: httpd-container

    build: ./docker/httpd

    ports:

      - "80:80"

  tomcat:

    container_name: tomcat-container

    build: ./docker/tomcat

    volumes:

      - ./target/ROOT.war:/usr/local/tomcat/webapps/ROOT.war

    expose:

      - "8009"
      
