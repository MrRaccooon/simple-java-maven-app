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

Experiment 3 – Stream Gradle

1. Install Java and Gradle
1.1 Update System and Install Java
sudo apt update
sudo apt install -y openjdk-17-jdk
java -version
1.2 Download and Install Gradle
sudo apt install unzip -y
wget https://services.gradle.org/distributions/gradle-8.5-bin.zip
sudo mkdir /opt/gradle
sudo unzip -d /opt/gradle gradle-8.5-bin.zip
1.3 Set Up Environment Variables
echo "export PATH=/opt/gradle/gradle-8.5/bin:$PATH" | sudo tee -a /etc/profile.d/gradle.sh
source /etc/profile.d/gradle.sh
gradle -v
2. Create a Gradle Project
mkdir my-gradle-project
cd my-gradle-project
gradle init
Select the following options
Select type of project to generate:
1: basic
2: application
3: library
4: Gradle plugin
Enter selection (default: basic) [1..4]: 2

Select implementation language:
1: C++
2: Groovy
3: Java
4: Kotlin
5: Scala
6: Swift
Enter selection (default: Java) [1..6]: 3

Generate multiple subprojects for application? (default: no)
[yes, no]: no

Select build script DSL:
1: Kotlin
2: Groovy
Enter selection (default: Kotlin) [1..2]: 2

Select test framework:
1: JUnit 4
2: TestNG
3: Spock
4: JUnit Jupiter
Enter selection (default: JUnit Jupiter) [1..4]: 4

Project name (default: my-gradle-project): gradle-demo
Source package (default: gradle.demo): com.myapp
Enter target version of Java (min. 7) (default: 17)
Generate build using new APIs and behavior? (default: no) [yes, no]: no
3. Run Gradle Commands
gradle build
gradle run
gradle test
gradle tasks
gradle dependencies

Experiment 4 – Maven to Gradle Conversion

1. Install Java
sudo apt update && sudo apt upgrade -y
sudo apt install openjdk-17-jdk -y
java -version
2. Install Git and Clone Repository
sudo apt install git -y
git --version

Fork the repository in GitHub:

https://github.com/jenkins-docs/simple-java-maven-app

Clone your forked repository:

git clone <your-forked-repository-link>
3. Install Maven
wget https://archive.apache.org/dist/maven/maven-3/3.9.2/binaries/apache-maven-3.9.2-bin.tar.gz
sudo tar -xvf apache-maven-3.9.2-bin.tar.gz -C /opt
sudo ln -sfn /opt/apache-maven-3.9.2 /opt/maven

echo 'export PATH=/opt/maven/bin:$PATH' >> ~/.bashrc
source ~/.bashrc

mvn -version
4. Generate a Build Using Maven
cd simple-java-maven-app
mvn clean package
ls

Check the target folder for build output.

5. Install Gradle
cd ..
sudo apt install unzip -y
wget https://services.gradle.org/distributions/gradle-8.5-bin.zip
sudo mkdir /opt/gradle
sudo unzip -d /opt/gradle gradle-8.5-bin.zip

echo 'export PATH=$PATH:/opt/gradle/gradle-8.5/bin' >> ~/.bashrc
source ~/.bashrc

gradle -v
6. Initialize Gradle
cd simple-java-maven-app
gradle init

Select:

Found a Maven build. Generate a Gradle build from this? (default: yes) → yes

Select build script DSL:
1: Kotlin
2: Groovy
Enter selection → 2

Generate build using new APIs and behavior? (default: no) → no

Gradle-related files will now be generated.

7. Edit build.gradle
vi build.gradle

Add the following:

id 'application'

jar {
    manifest {
        attributes(
            'Main-Class': 'com.mycompany.app.App'
        )
    }
}
8. Generate Gradle Build
gradle build

Check generated JAR:

cd build/libs/
9. Run the Application
java -jar build/libs/my-app-1.0-SNAPSHOT.jar
10. Clean Build
gradle clean build
11. Check Maven Build Output
java -jar target/*.jar

Example Output:

Hello World!

Experiment 5 – Jenkins Installation

1. Update System and Install Java
sudo apt update
sudo apt install openjdk-17-jdk -y
java -version
2. Install Jenkins

Visit the official Jenkins repository:

https://pkg.jenkins.io/

Follow installation steps for Ubuntu.

3. Start and Enable Jenkins
sudo systemctl start jenkins
sudo systemctl enable jenkins
sudo systemctl status jenkins

OR

sudo service jenkins start
sudo service jenkins status
4. Get Jenkins Admin Password
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
5. Access Jenkins Web Interface

Allow TCP Port 8080 in your instance security group.

Open in browser:

http://<your-server-public-ip>:8080

Example password:

0d740e938eef4641b36cd509577aabfe
