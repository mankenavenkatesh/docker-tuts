FROM tomcat
COPY HelloWorldWebApp/target/HelloWorldWebApp.war /usr/local/tomcat/webapps
COPY start.sh /tmp/start.sh
RUN chmod +x /tmp/start.sh
CMD ["/tmp/start.sh"]
