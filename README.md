# forexam

## Maven Dependencies

```xml
<dependency>
    <groupId>org.junit.jupiter</groupId>
    <artifactId>junit-jupiter-api</artifactId>
    <version>5.11.0</version>
    <scope>test</scope>
</dependency>

<dependency>
    <groupId>org.junit.jupiter</groupId>
    <artifactId>junit-jupiter-engine</artifactId>
    <version>5.11.0</version>
    <scope>test</scope>
</dependency>
```

---

## Docker

```dockerfile
FROM redis:latest
CMD ["redis-server"]
```

### 1.

```bash
docker build -t redisnew
```

### 3.

```bash
docker run --name myredisnew -d redisnew
```

### 5.

```bash
docker ps
```

### 7.

```bash
docker stop myredisnew
```

### 9.

```bash
docker login
```

### 11.

```bash
docker ps -a
```

### 13.

```bash
docker commit 0e993d2009a1 budarajumadhurika/redis1
```

### 14.

```bash
docker images
```

### 15.

```bash
docker push budarajumadhurika/redis1
```

### 16.

```bash
docker rm 0e993d2009a1
```

### 17.

```bash
docker rmi budarajumadhurika/redis1
```

### 19.

```bash
docker logout
```

### 20.

```bash
docker pull budarajumadhurika/redis1
```

### 21.

```bash
docker run --name myredis -d budarajumadhurika/redis1
```

### 23.

```bash
docker exec -it myredis redis-cli
SET name "Abcdef"
GET name
exit
```

### What It Does:

• Logs you out from Docker Hub and removes your stored credentials.

---

## Docker Web App

```bash
nano Dockerfile
docker build -t mywebapp .
docker run -p 8080:8080 mywebapp
docker images
docker commit <container-id> <username>/mywebapp
docker push <username>/mywebapp
```

## Git

```bash
git init
git add .
git commit -m "push"
git remote add origin <repo-URL>
git push -u origin main
```

---

## Dockerfiles

### Web Application

```dockerfile
FROM tomcat:9
COPY target/*.war /usr/local/tomcat/webapps/
COPY target/*.war /usr/local/tomcat/webapps/
```

### Java Application

```dockerfile
FROM eclipse-temurin:17
COPY target/*.jar app.jar
CMD ["java", "-jar", "app.jar"]
```

### Web Application - ROOT

```dockerfile
FROM tomcat:9.0
COPY target/*.war /usr/local/tomcat/webapps/ROOT.war
CMD ["catalina.sh","run"]
```

---

## Maven POM

```xml
<?xml version="1.0" encoding="UTF-8"?>

<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0
                             http://maven.apache.org/xsd/maven-4.0.0.xsd">

    <modelVersion>4.0.0</modelVersion>

    <groupId>com.kmit.calculator</groupId>

    <artifactId>simple-cal</artifactId>

    <version>0.0.1-SNAPSHOT</version>

    <packaging>war</packaging>

    <name>Simple Calculator</name>

    <properties>
        <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
        <maven.compiler.release>11</maven.compiler.release>
    </properties>

    <dependencies>

        <!-- JUnit dependency -->
        <dependency>
            <groupId>org.junit.jupiter</groupId>

            <artifactId>junit-jupiter-api</artifactId>

            <version>5.11.0</version>
            <scope>test</scope>
        </dependency>

        <dependency>
            <groupId>org.junit.jupiter</groupId>
            <artifactId>junit-jupiter-engine</artifactId>
            <version>5.11.0</version>
            <scope>test</scope>
        </dependency>

    </dependencies>

    <build>

        <plugins>

            <!-- Compiler Plugin -->
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>

                <artifactId>maven-compiler-plugin</artifactId>

                <version>3.13.0</version>

                <configuration>
                    <release>11</release>
                </configuration>
            </plugin>

            <!-- JAR Plugin -->
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-jar-plugin</artifactId>

                <version>3.4.2</version>

                <configuration>
                    <archive>
                        <manifest>
                            <mainClass>com.kmit.simple_cal.Calculator</mainClass>
                        </manifest>
                    </archive>
                </configuration>
            </plugin>

            <!-- Clean Plugin -->
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-clean-plugin</artifactId>
                <version>3.4.0</version>
            </plugin>

        </plugins>

    </build>

</project>
```

---

## Useful Docker Commands

### 1)Check logs after an app crashes

```bash
docker logs <container_name>
```

### 2)Find which container is using port 3000

```bash
docker ps --filter "publish=3000"
```

### 3) Tag an image that you forgot to tag

```bash
docker tag <existing-image> <new-name>:<tag>
```

### 4)Export an image as .tar

```bash
docker save -o myimage.tar myimage
```

### 5)Automatically restart a container if it crashes

When creating the container:

```bash
docker run --restart=on-failure <image_name>
```

If the container already exists, you can set the restart policy with:

```bash
docker update --restart=on-failure <container_name>
```

### 6)How to limit RAM?

```bash
docker run --memory=512m <image_name>
```

### 7)

```bash
docker tag redisi:latest harika2703/redisi:latest
```

-------------perform this for evry push ,before push perform this

---

## Git Commands

### 1)

```bash
git remote remove origin
```

### 2)

```bash
git fetch <remote_name>
```

### 3)

```bash
git remote set-url origin https://github.com/username/new-repository.git
```

### 4)

```bash
git remote show origin
```

### 5)

```bash
git branch –r
```

---------all remote branches

### 6)

```bash
git rebase origin/main
```

“Take my local commits and replay them on top of the latest origin/main

### 7)

Shows the details of a specific commit, including the changes made and the commit message.

```bash
git show <commit>
```

### 8)Recovering deleted branches

```bash
git reflog
git checkout -b feature-ui <commit_hash>
```

### 9)To download the latest changes from the remote without merging

```bash
git fetch origin
```

### 10) To remove accidentally committed sensitive file from Git history.

```bash
git filter-branch --force --index-filter \
"git rm --cached --ignore-unmatch secrets.txt" \
--prune-empty --tag-name-filter cat -- --all
```

### 11)Add Rules to .gitignore

Inside the .gitignore file, you add patterns for the files and directories you want Git to ignore. Each pattern should be written on a new line.

Here are some common examples:

• Ignore all .log files:

```gitignore
*.log
```

• Ignore a specific file:

```gitignore
secret_file.txt
```

• Ignore all files in a temp/ directory:

```gitignore
temp/
```

• Ignore all files except important_file.txt inside a folder:

```gitignore
folder/*
!folder/important_file.txt
```

• Ignore files with a specific extension:

```gitignore
*.bak
```

### 12)16. Git stash

```bash
git stash
git switch another-branch
# do something else...
git switch main
git stash apply
```

### 13)To check branch is merge

```bash
git branch –merged
```

If branch not merged then displays its name

### Restore stashed changes

```bash
git stash pop
```

### 14)Remove a file from staging without losing changes

```bash
git restore --staged file1.txt
```

### 15)Create search-filter from main

While on main:

```bash
git switch -c search-filter
```

### 16)Remove an API key completely from repository history

Simply deleting the file is not enough, because the key remains in Git history.

Use history-rewriting tools such as:

```bash
git filter-repo
```
1. Maven Java Project
Step 1: Clone the GitHub Repository
git clone <repository-url>
cd <project-folder>
Step 2: Import into Eclipse
Eclipse
→ File
→ Import
→ Maven
→ Existing Maven Projects
→ Browse to project folder
→ Finish
Step 3: Check Maven Project Structure
project/
├── pom.xml
├── src/
│   ├── main/
│   │   ├── java/
│   │   └── resources/
│   └── test/
│       └── java/
└── target/
src/main/java → Java source code
src/main/resources → application resources
src/test/java → test code
pom.xml → Maven configuration
target → generated build output
Step 4: Check pom.xml

Dependencies go inside:

<dependencies>
    <dependency>
        <groupId>...</groupId>
        <artifactId>...</artifactId>
        <version>...</version>
    </dependency>
</dependencies>

Example Gson dependency:

<dependency>
    <groupId>com.google.code.gson</groupId>
    <artifactId>gson</artifactId>
    <version>2.8.9</version>
</dependency>
Step 5: Maven Build

From Eclipse Terminal:

mvn clean install

Or:

mvn clean package
Step 6: Run a Java Application

If the project contains a main() method:

Right-click Java class
→ Run As
→ Java Application

Do not use mvn run. run is not a standard Maven lifecycle phase.

Step 7: Run Tests
mvn test

Test reports are generated inside:

target/surefire-reports/
Useful Maven Commands
mvn clean
mvn compile
mvn test
mvn package
mvn install
mvn clean package
mvn clean install
Skip Tests
mvn package -DskipTests
View Dependency Tree
mvn dependency:tree
Debug Maven
mvn -X
2. Maven Web Project
Step 1: Clone Repository
git clone <repository-url>
cd <project-folder>
Step 2: Import into Eclipse
File
→ Import
→ Maven
→ Existing Maven Projects
→ Select project folder
→ Finish
Step 3: Web Project Structure
web_project/
├── pom.xml
├── src/
│   ├── main/
│   │   ├── java/
│   │   ├── resources/
│   │   └── webapp/
│   │       └── WEB-INF/
│   │           └── web.xml
│   └── test/
│       └── java/
└── target/
Step 4: Configure WAR Packaging

In pom.xml:

<packaging>war</packaging>

The output will be:

target/web_project.war
Step 5: Add Servlet Dependency
<dependency>
    <groupId>javax.servlet</groupId>
    <artifactId>javax.servlet-api</artifactId>
    <version>4.0.1</version>
    <scope>provided</scope>
</dependency>

provided means the Servlet API is supplied by the web server such as Tomcat.

Step 6: Configure Java Version

Example compiler plugin:

<plugin>
    <groupId>org.apache.maven.plugins</groupId>
    <artifactId>maven-compiler-plugin</artifactId>
    <version>3.11.0</version>
    <configuration>
        <source>17</source>
        <target>17</target>
    </configuration>
</plugin>
Step 7: Build the WAR
mvn clean package

Check:

target/
└── web_project.war
Step 8: Configure Tomcat

In Eclipse:

Window
→ Show View
→ Servers

Then:

New Server
→ Apache
→ Tomcat v9.0
→ Select Tomcat installation directory
→ Finish
Step 9: Add Project to Tomcat
Right-click Tomcat server
→ Add and Remove
→ Select web_project
→ Add
→ Finish
Step 10: Start Tomcat
Right-click Tomcat
→ Start

Or:

Right-click project
→ Run As
→ Run on Server
→ Tomcat v9.0
→ Finish
Step 11: Open Web Application

If Tomcat is running on port 8080:

http://localhost:8080/web_project/

If your Tomcat uses another port, replace 8080.

3. Maven Web Project — Complete Practical Flow
GitHub Repository
       ↓
git clone
       ↓
Import Existing Maven Project
       ↓
Check pom.xml
       ↓
Add Servlet dependency
       ↓
Set WAR packaging
       ↓
Configure compiler plugin
       ↓
mvn clean package
       ↓
target/web_project.war
       ↓
Tomcat
       ↓
Run on Server
       ↓
Browser
4. Important Maven Concepts
Dependency

A library required by your application.

<dependency>
    ...
</dependency>
Plugin

Used to perform/build/configure Maven tasks.

<plugin>
    ...
</plugin>
JAR

Used mainly for Java libraries/applications.

myapp.jar
WAR

Used for Java web applications.

mywebapp.war
target

Contains Maven-generated output:

target/
├── classes/
├── test-classes/
├── surefire-reports/
└── web_project.war
Maven Lifecycle
validate
   ↓
compile
   ↓
test
   ↓
package
   ↓
verify
   ↓
install
   ↓
deploy
5. Common Practical Errors
Java version error

Check Java:

java -version

Check Maven:

mvn -version

Make sure Eclipse and Maven are using the required Java version.

Dependency problem
mvn dependency:tree
Clean previous build
mvn clean
Rebuild everything
mvn clean install
Maven POM errors

Check:

pom.xml

for incorrect:

groupId
artifactId
version
dependency
plugin
XML tags
6. Git + Maven Practical Flow

If the instructor gives a GitHub repository:

git clone <repository-url>
cd <project-folder>

Work on the project, then:

git status
git add .
git commit -m "Updated Maven project"
git push origin main

Check remote:

git remote -v

Add a new remote:

git remote add origin <repository-url>
⭐ Most Important Commands to Memorize
# Git
git clone <url>
git status
git add .
git commit -m "message"
git remote -v
git remote add origin <url>
git push -u origin main

# Maven
mvn clean
mvn compile
mvn test
mvn package
mvn clean package
mvn clean install
mvn dependency:tree
mvn -DskipTests package

# Run Java
# Eclipse → Right-click class → Run As → Java Application

# Run Web Project
# Eclipse → Right-click project → Run As → Run on Server
🧠 One-line memory trick

Java Maven:
clone → import → pom → clean package → Java Application

Web Maven:
clone → import → pom → WAR → clean package → Tomcat → browser

This is formatted so you can directly paste it into your README.md.
