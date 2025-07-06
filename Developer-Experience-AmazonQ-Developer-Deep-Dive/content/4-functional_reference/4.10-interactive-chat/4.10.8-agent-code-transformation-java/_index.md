---
title: "Agent for Code Transformation: Java"
date: "`r Sys.Date()`"
weight: 8
chapter: false
pre: " <b> 4.10.8. </b> "
---

#### Amazon Q: Agent for Code Transformation (Java)

Amazon Q Developer Agent helps you transform Java projects (e.g., Java 8 to Java 17). Open your project in the IDE, then use Q Chat with the `/transform` command to start the transformation.

##### Example: Java 8 to Java 17

1. **Start the Code Transformation Agent**
   - The Agent for Code Transformation tab will display a form with options:
     - Location: The root folder of the Java project to be transformed. (Select the project folder if you are not in the root of the Java project)
     - Source: The current source version (Java 8 or 11)
     - Target: The target version to be transformed to (Java 17. Other versions coming soon)
   - Select Confirm after choosing the options.

2. **Build the Project**
   - The agent will attempt to build the project before starting the transformation process.
   - Select Confirm to proceed.

3. **Provide JDK Path**
   - The agent requires the path to the JDK directory installed in the development environment.
   - Copy the path into the chat and press Enter to start the build.

4. **Build and Analyze**
   - The build process may take up to 10 minutes depending on the project size.
   - Monitor progress using the "Open Transformation Hub" button.

5. **Create Transformation Plan**
   - The agent will build the source code using Java 8 in a safe build environment.
   - Automatically start executing the plan to transform the Java 8 (or 11) project to Java 17.

6. **Transformation Plan Includes**
   - Updating the JDK version and modifying related dependencies and code.
   - Generating code changes for you to review before accepting.

7. **Accept the Transformation**
   - After the agent completes the transformation plan, you will have the option to download the proposed changes.
   - Upon selecting Accept, the file changes will be applied to the local directory.

> **Note:** Ensure your project meets prerequisites (Maven, JDK, build success, etc.) before starting the transformation.