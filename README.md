# simple-java-maven-app

This repository is for the
[Build a Java app with Maven](https://jenkins.io/doc/tutorials/build-a-java-app-with-maven/)
tutorial in the [Jenkins User Documentation](https://jenkins.io/doc/).

The repository contains a simple Java application which outputs the string
"Hello world!" and is accompanied by a couple of unit tests to check that the
main application works as expected. The results of these tests are saved to a
JUnit XML report.

The `jenkins` directory contains an example of the `Jenkinsfile` (i.e. Pipeline)
you'll be creating yourself during the tutorial and the `jenkins/scripts` subdirectory
contains a shell script with commands that are executed when Jenkins processes
the "Deliver" stage of your Pipeline.


Ms Nidhi Joshi Parsai
Created Jan 24Jan 24
Hi
Assesment Plan.pptx
Microsoft PowerPoint

DEVOPS (1).pptx
Microsoft PowerPoint

Lesson Plan.docx
Microsoft Word

SYLLABUS.pdf
PDF

EXPERIMENT 3
Stream
gradle
==============
installation- java is required for gradle
==========================================
//1: Install Java and Gradle

//1.1.Update and Install Java

sudo apt update
sudo apt install -y openjdk-17-jdk
java -version


//1.2.Download and Install Gradle

sudo apt install unzip -y
wget https://services.gradle.org/distributions/gradle-8.5-bin.zip
sudo mkdir /opt/gradle
sudo unzip -d /opt/gradle gradle-8.5-bin.zip


1.3.Set Up Environment Variables
echo "export PATH=/opt/gradle/gradle-8.5/bin:\$PATH" | sudo tee -a /etc/profile.d/gradle.sh
source /etc/profile.d/gradle.sh
gradle -v


2: Create a Gradle Project

mkdir my-gradle-project && cd my-gradle-project

gradle init

Select type of project to generate:
  1: basic
  2: application
  3: library
  4: Gradle plugin
Enter selection (default: basic) [1..4] 2

Select implementation language:
  1: C++
  2: Groovy
  3: Java
  4: Kotlin
  5: Scala
  6: Swift
Enter selection (default: Java) [1..6] 3

Generate multiple subprojects for application? (default: no) [yes, no] no
Select build script DSL:
  1: Kotlin
  2: Groovy
Enter selection (default: Kotlin) [1..2] 2

Select test framework:
  1: JUnit 4
  2: TestNG
  3: Spock
  4: JUnit Jupiter
Enter selection (default: JUnit Jupiter) [1..4] 4

Project name (default: my-gradle-project): gradle-demo
Source package (default: gradle.demo): com.myapp
Enter target version of Java (min. 7) (default: 17): 
Generate build using new APIs and behavior (some features may change in the next minor release)? (default: no) [yes, no] no

3.gradle build

4. gradle run

5.gradle test

6. gradle tasks

7.gradle depencies


EXPERIMENT 4
maven to gradle
================


1. //install java    
sudo apt update && sudo apt upgrade -y
sudo apt install openjdk-17-jdk -y
java -version

2.install git to clone one repo into our local machine 
sudo apt install git -y
git --version

//in google first open your git hub later fork the below repo-https://github.com/jenkins-docs/simple-java-maven-app
//Edit Below command with your forked Github repositoty

git clone paste your forked GitHub repository link


//3.install maven
wget https://archive.apache.org/dist/maven/maven-3/3.9.2/binaries/apache-maven-3.9.2-bin.tar.gz
sudo tar -xvf apache-maven-3.9.2-bin.tar.gz -C /opt
sudo ln -sfn /opt/apache-maven-3.9.2 /opt/maven
echo 'export PATH=/opt/maven/bin:$PATH' >> ~/.bashrc
source ~/.bashrc
mvn -version


//4.generate a build using maven
cd simple-java-maven-app
mvn clean package
ls//to see target


//5. install gradle
cd ..
sudo apt install unzip -y
wget https://services.gradle.org/distributions/gradle-8.5-bin.zip
sudo mkdir /opt/gradle
sudo unzip -d /opt/gradle gradle-8.5-bin.zip
echo 'export PATH=$PATH:/opt/gradle/gradle-8.5/bin' >> ~/.bashrc
source ~/.bashrc
gradle -v

//6. initialize gradle
cd simple-java-maven-app
gradle init

Found a Maven build. Generate a Gradle build from this? (default: yes) [yes, no] yes

Select build script DSL:
  1: Kotlin
  2: Groovy
Enter selection (default: Kotlin) [1..2] 2

Generate build using new APIs and behavior (some features may change in the next minor release)? (default: no) [yes, no] no

now gradle related files will be created 

now open build.gradle with vi editior like vi build.gradle and hit enter after that do the follwoing changes


    id 'application'



jar {
    manifest {
        attributes(
            'Main-Class': 'com.mycompany.app.App'  // Ensure this matches your actual main class
        )
    }
}


//7. now generte build
gradle build

now here can see the jar file-cd build/libs/


//8. how to check outcome

java -jar build/libs/my-app-1.0-SNAPSHOT.jar


//9.how toclean build

gradle clean build

//10. how to check maven build output

java -jar target/*.jar

//checking
==========
ubuntu@ip-172-31-42-54:~/simple-java-maven-app$ ls
LICENSE.txt  azure-pipelines-1.yml  build         gradle   gradlew.bat  pom.xml          src
README.md    azure-pipelines.yml    build.gradle  gradlew  jenkins      settings.gradle  target
ubuntu@ip-172-31-42-54:~/simple-java-maven-app$ java -jar build/libs/my-app-1.0-SNAPSHOT.jar
Hello World!
ubuntu@ip-172-31-42-54:~/simple-java-maven-app$ java -jar target/*.jar
Hello World!


EXPERIMENT 5

1: Update System and Install Java

sudo apt update
sudo apt install openjdk-17-jdk -y
java -version

2.Jenkins Installation on Ubuntu (Latest Method)

https://pkg.jenkins.io/

3: Start and Enable Jenkins
sudo systemctl start jenkins
sudo systemctl enable jenkins
sudo systemctl status jenkins  # Check if Jenkins is running

or

sudo service jenkins start
sudo service jenkins status

4: Get Jenkins Admin Password
sudo cat /var/lib/jenkins/secrets/initialAdminPassword


5: Access Jenkins Web Interface

first allow custom tcp port 8080 by selecting anywhere with ipv4 with all zeros in security grops of that instance 
http://your-server-ip(public-ip):8080

0d740e938eef4641b36cd509577aabfe


