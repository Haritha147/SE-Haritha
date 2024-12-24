FROM python:2.7-slim
WORKDIR /app
COPY first.py /app/
CMD ["python","first.py"]


docker build -t python27-trial .
docker run python27-trial
docker login
docker tag python27-trial npk62/python27-trial
docker push npk62/python27-trial

to verify
docker ps


Docker file for Java
# Use the official OpenJDK image as the base image
FROM openjdk:11-jdk-slim

# Set the working directory inside the container
WORKDIR /app

# Copy the Java source code into the container
COPY HelloWorld.java /app/

# Compile the Java program
RUN javac HelloWorld.java

# Run the Java program
CMD ["java", "HelloWorld"]
