---
title: "Agent for Code Transformation: Java"
date: "`r Sys.Date()`"
weight: 8
chapter: false
pre: " <b> 4.10.8. </b> "
---


#### Amazon Q: Agent for Code Transformation (Java)

Amazon Q Developer Agent helps you transform Java projects (e.g., Java 8 to Java 17). Open your project in the IDE, then use Q Chat with the `/transform` command to start the transformation.

#### Example: Java 8 to Java 17
**Prompt:**
Chuyển đổi dự án Java 8 sang Java 17.

**Amazon Q Answer:**
Amazon Q sẽ hướng dẫn từng bước chuyển đổi, kiểm tra điều kiện dự án và thực hiện chuyển đổi mã nguồn.

> **Note:** Ensure your project meets prerequisites (Maven, JDK version, build success, etc.) before starting transformation.

agent for software development

The Agent for Code Transformation tab will have populated a prompt form, with the options for project to be transformed

location: The root folder of the Java project to be transformed. (Select the project folder if you are not in the root of the Java project)
Source: The current source version (Java 8 or 11)
Target: The target version to be tranformed to (Java 17. Other version comming soon)
Once you have selected the source code location and source and target versions, select confrim.

agent for software development

The Agent for Code Transformation will attempt to build your porject locally before starting the transformation process. By default, and the recommended approach, the Agent for Code Transformation will build your project using mvn test. If you would to build your project without running unit tests, you can select skip from the dropdown options and The Agent for Code Transformation will use mvn test-compile.

Select Confirm.

In order to build your project the Agent for Code Transformation requires the local directory of the JDK installed in your dev environment.

To find the local directory for the Java 8 JDK, open your Commend Line Interface (CLI) and run the command procided in the Agent for Code Transformation chat


Linux/MacOS

Windows
/usr/libexec/java_home -v 1.8

Copy the directory of the local JDK version 8 folder to the Agent for Code Transformation chat, and press enter to begin the local build (and test) of your Java 8 project.

agent for software development

The local build process can take up to 10 minutes, depending on the size of your project.

Once the project has built and tested successfully Agent for Code Transformation will scan the project files and prepare to start the job. To start the job, Agent for Code Transformation needs to upload the project artifacts to your account. Once that is done, Agent for Code Transformation can start the transformation job. The estimated time for this operation ranges from a few seconds to several minutes, based on the size of your project.

Cancel transformation
If for any reason you want to cancel the transformation job, you can select the "Cancel Transformation" button in the Chat tab.

To keep track of the progress of the transformation job, select the "Open Transformation Hub" button in the Chat tab.

Once your project is uploaded the Agent for Code Transformation will build your code using Java 8 in a secure build environment. Then analyzing your code in order to generate a transformation plan.

agent for software development

Once the transformation plan has been generated, the Agent for Code Transformation will open the Transformation Plan in a new tab in your IDE so that you can read through the analyzed required changes. The Agend for Code Transformation will automatically begin executing the plan to transform the Java 8 (or 11) project to Java 17.

The open the following to view an example Transformation plan:

Code Transformation plan by Amazon Q
The Agent for Code Transformation will attempt to:

update the JDK version and change any dependencies and related code.
replace any instances of deprecated code.
Apply code changes for any additional dependencies and resolve compilation errors.
generate code changes that you can review before accepting changes to your files.
You can also view a transformation summary with details about the upgrade and build logs for future reference and troubleshooting.

Accept Transformation
Once the Agent for Code Transformation has complete the transformation plan on the build environmnet in your account. You will be provided an option to download the propsed changes.

By selecting the "Download Proposed Changes" button to download the code and change log as a local folder git pull request.

agent for software development

You can reveiw each of the proposed code changes in each file as a git diff, to see the difference between the source version and target version.

As you can see above, the target version has removed deprecated code and replaced with generated functional code. We can be assured that the generated code is functional as the Agent for Code Transformation successfully builds prior to prpoviding the code for download.

Once you are satisfied with reviewing the code changes you can Accept or Reject by selected the desired option above the list of files changed.

When Accept selected the file changes are pulled to the local folder.

Finally, you can reivew the Code Transformation Summary for infomration and statistics of code changes, and review depricated dependancies.

Expand to view demo summary:

Code Transformation Summary by Amazon Q
Table of Contents
Build log summary
Planned dependencies replaced
Additional dependencies added
Deprecated code replaced
Other changes
All files changed
Next steps
Build log summary Scroll to top
Amazon Q successfully built the upgraded code in Java 17. Here is a relevant snippet from the build log. To view the full build log, open buildCommandOutput.log

The Maven build was successful in compiling, testing, packaging, and repackaging a Java 17 application called simple-java8-project version 1.0-SNAPSHOT. The build compiled 20 source files, did not run any tests since there were none, built a JAR, and repackaged it as a Spring Boot application. One source file used a deprecated API resulting in a deprecation warning.
Planned dependencies replaced Scroll to top
Amazon Q updated the following dependencies that it identified in the transformation plan

Dependency	Action	Previous version in Java 8	Current version in Java 17
com.squareup.okio:okio	Updated	1.17.5	3.9.1
io.springfox:springfox-swagger2	Removed	2.9.2	-
jakarta.persistence:jakarta.persistence-api	Added	-	3.2.0
junit:junit	Removed	4.13.2	-
org.springdoc:springdoc-openapi-starter-webmvc-ui	Added	-	2.6.0
org.springframework.boot:spring-boot-starter-parent	Updated	2.4.13	3.3.4
Additional dependencies added Scroll to top
Amazon Q updated the following additional dependencies during the upgrade

Dependency	Action	Previous version in Java 8	Current version in Java 17
io.springfox:springfox-swagger-ui	Removed	2.9.2	-
org.mockito:mockito-core	Updated	4.11.0	-
org.springframework.boot:spring-boot-maven-plugin	Updated	2.4.13	-
Deprecated code replaced Scroll to top
Amazon Q replaced the following instances of deprecated code. An instance with 0 files changed indicates Amazon Q wasn't able to replace the deprecated code.

Deprecated code	Files changed
java.lang.Byte.Byte(byte)	1
java.lang.Character.isJavaLetterOrDigit(char)	2
java.lang.Character.isSpace(char)	1
java.lang.Short.Short(short)	1
java.lang.reflect.AccessibleObject.isAccessible()	1
java.math.BigDecimal.divide(BigDecimal,int,int)	1
java.math.BigDecimal.setScale(int,int)	1
java.net.MulticastSocket.setInterface(InetAddress)	1
java.net.MulticastSocket.setTTL(byte)	1
java.net.URLDecoder.decode(String)	1
java.net.URLEncoder.encode(String)	1
java.security.cert.X509Certificate.getIssuerDN()	1
java.security.cert.X509Certificate.getSubjectDN()	1
java.util.Date.Date(int,int,int)	1
javax.management.monitor.CounterMonitor.getDerivedGauge()	0
javax.management.monitor.CounterMonitor.getDerivedGaugeTimeStamp()	0
javax.management.monitor.CounterMonitor.getThreshold()	0
javax.management.monitor.GaugeMonitor.getDerivedGauge()	0
javax.management.monitor.GaugeMonitor.getDerivedGaugeTimeStamp()	0
javax.management.monitor.Monitor.getObservedObject()	0
Other changes Scroll to top
All files changed Scroll to top
File	Action
pom.xml	Updated
src/main/java/com/example/Book.java	Updated
src/main/java/com/example/BookCharacterUtils.java	Updated
src/main/java/com/example/BookNetworkUtils.java	Updated
src/main/java/com/example/BookNumberUtils.java	Updated
src/main/java/com/example/BookSecurityUtils.java	Updated
src/main/java/com/example/BookSerializer.java	Updated
src/main/java/com/example/BookURLUtils.java	Updated
src/main/java/com/example/BookUtility.java	Updated
src/main/java/com/example/BookXmlImporter.java	Updated
src/main/java/com/example/ReflectionUtils.java	Updated
src/main/java/com/example/StringUtils.java	Updated
src/main/java/com/example/SwaggerConfig.java	Updated
Next steps Scroll to top
Please review and accept the code changes using the diff viewer.If you are using a Private Repository, please ensure that updated dependencies are available.
In order to successfully verify these changes on your machine, you will need to change your project to Java 17. We verified the changes using Amazon Corretto Java 17  build environment.
If this project uses Maven CheckStyle, Enforcer, FindBugs or SpotBugs plugins, Q Code Transformation will disable those plugins when we build the project to verify proposed upgrades.