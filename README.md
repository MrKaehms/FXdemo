This Repository contains a few sample JavaFX programs.  In order to create
your own JavaFX programs using these examples, you will need to create a
Java Project <Using Maven - See the screenshots of installed Java and JavaFX extensions>

Maven is one of the build extensions that you will need to install if it isn't
already.  

A good introductory video on how to start a JavaFX program is here:
https://www.youtube.com/watch?v=NYGHL8N6Kc8

To determine the version of Java JDK installed in your computer, open a terminal window in VS Code, and type the following:

java -XshowSettings:properties -version

For my home computer, the lines below identify the jdk version (Note the major number "21". You will need to update the pom.xml file to reflect this):

openjdk version "21.0.5" 2024-10-15 LTS

OpenJDK Runtime Environment Temurin-21.0.5+11 (build 21.0.5+11-LTS)

OpenJDK 64-Bit Server VM Temurin-21.0.5+11 (build 21.0.5+11-LTS, mixed mode)


The major version of your Java JDK needs to match the entries in the pom.xml file that is created when creating your project.  See the above video for
details.  For this repo, and my home computer configuration, the lines modified are:

 <properties>
        <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
        <maven.compiler.source>21</maven.compiler.source>
        <maven.compiler.target>21</maven.compiler.target>
    </properties>

    (Note the "21" in the source and target lines above)

In addition, you will need to update the JavaFX library to the latest version. The above video suggests that you go to the following website, to determine
the latest version for you architecture (click on download, then set the parameters for your computer and architecture):

https://openjfx.io/

For my Mac, the latest release (not an early release) was 23.0.2

Use that information to update the JavaFX dependencies of the pom.xml file (note the 23 set as the version):

      <dependency>
            <groupId>org.openjfx</groupId>
            <artifactId>javafx-controls</artifactId>
            <version>23</version>
        </dependency>

Finally, whenever you add a new java file to your project folder, make sure the first line of the file reflects the package name you set when creating the
maven project.  If you use the default, it will be as follows:

package com.example;

If you create new sample java files you will have to add the above line, or one like it, depending on what you name the package, to the top of the java file,
and you will have to change one more line in the pom.xml file to identify the entry point of your program:

  <configuration>
           <mainClass>com.example.LineChartExample</mainClass>
  </configuration>

In this example, LineChartExample is the entry point, and it is part of the com.example package.


        





    
