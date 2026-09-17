# HOTSTAR Jenkins CI/CD Project

## 📌 Project Overview

This project demonstrates an end-to-end **CI/CD pipeline** for a Java Maven web application using Jenkins and DevOps tools.

The pipeline automates the process from source-code checkout through compilation, testing, code-quality analysis, artifact creation, artifact storage, and deployment to Apache Tomcat.

## 🚀 CI/CD Pipeline

```text
GitHub
   ↓
Jenkins
   ↓
Maven Compile
   ↓
Maven Test
   ↓
SonarQube Analysis
   ↓
Maven Package
   ↓
Nexus Repository
   ↓
Apache Tomcat
   ↓
Web Application
```

## 🛠️ Technologies Used

* Git & GitHub
* Jenkins
* Maven
* SonarQube
* Nexus Repository
* Apache Tomcat
* Java
* Linux
* AWS EC2

## 🔄 Pipeline Stages

### 1. Checkout Code

Jenkins retrieves the application source code from GitHub.

### 2. Compile Project

Maven compiles the Java application and verifies that the source code can be built successfully.

```bash
mvn clean compile
```

### 3. Test Project

Automated tests are executed using Maven.

```bash
mvn test
```

### 4. SonarQube Scanning

The project is analyzed using SonarQube to perform automated code-quality analysis.

### 5. Package Project

Maven packages the application into a WAR file.

```bash
mvn clean package
```

Generated artifact:

```text
target/myapp.war
```

### 6. Upload to Nexus

The generated WAR file is uploaded to the Nexus repository for artifact storage and version management.

```text
Repository: HOTSTAR
Group ID: in.krishna
Artifact ID: myapp
Version: 8.3.3-SNAPSHOT
```

### 7. Deployment to Tomcat

The WAR file is automatically deployed to Apache Tomcat using the Jenkins deployment process.

Application context:

```text
/myapp
```

## 📂 Project Structure

```text
HOTSTAR-JENKINS-CICD-PROJECT/
│
├── Jenkinsfile
├── pom.xml
├── .gitignore
│
├── src/
│   ├── main/
│   │   ├── java/
│   │   └── webapp/
│   │
│   └── test/
│       └── java/
│
└── screenshots/
```

## 📋 Jenkins Pipeline

The project uses a Jenkins Declarative Pipeline with stages for:

* Source-code checkout
* Compilation
* Unit testing
* SonarQube analysis
* Maven packaging
* Nexus artifact upload
* Tomcat deployment

## 📸 Project Screenshots

Screenshots demonstrating the successful execution of the CI/CD pipeline are included in the `screenshots` directory.

Recommended screenshots:

1. Jenkins pipeline execution
2. Jenkins console output
3. SonarQube analysis
4. Nexus artifact repository
5. Tomcat Manager deployment
6. Deployed web application

## 🎯 Key Learning Outcomes

* Created and executed a Jenkins CI/CD pipeline.
* Integrated Maven with Jenkins for build and test automation.
* Integrated SonarQube for automated code-quality analysis.
* Uploaded build artifacts to Nexus Repository.
* Automated WAR deployment to Apache Tomcat.
* Worked with Linux-based AWS EC2 environments.
* Used Git and GitHub for source-code management.
* Connected multiple DevOps tools into an end-to-end delivery pipeline.

## 🔗 Repository

GitHub:

https://github.com/TSanjayManipalReddy/HOTSTAR-JENKINS-CICD-PROJECT

## 👨‍💻 Author

**T. Sanjay Manipal Reddy**

DevOps Engineer | AWS | Jenkins | Docker | Kubernetes | Terraform | Linux
