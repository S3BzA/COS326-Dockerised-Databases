FROM openjdk:8-jdk-alpine

# Copy the local ObjectDB zip file to the container
COPY objectdb-2.9.0.zip /tmp/objectdb.zip

# Create the directory, unzip the ObjectDB file, and clean up
RUN mkdir -p /opt/objectdb && unzip /tmp/objectdb.zip -d /opt/objectdb && rm /tmp/objectdb.zip

# List the contents of /opt/objectdb to check the structure
RUN ls -l /opt/objectdb && ls -l /opt/objectdb/objectdb-2.9.0 && ls -l /opt/objectdb/objectdb-2.9.0/bin

WORKDIR /opt/objectdb/objectdb-2.9.0

# Expose the default ObjectDB port
EXPOSE 6136

# Command to run the ObjectDB server
CMD ["java", "-cp", "bin/objectdb.jar", "com.objectdb.Server", "start"]
