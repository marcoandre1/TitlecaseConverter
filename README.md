# Setting up a Java Development Environment

This README keeps my personal notes from the PluralSight course **Setting up a Java Development Environment** by __

## Writting and Running Java Code

You write code in java files (`Hello.java`). This code is compiled with `javac` into class files (`Hello.class`) which is byte code.
The class files can be executed with the `java` command.  

Actually, the `java` command calls the `Java Virtual Machine (JVM)` and the `Java Standard Edition (SE) APIs`.  

The combination of `java` and `javac` is called the `JDK` for `Java Development Kit`.  

## Installing the JDK

1. Download the latest JDK: <jdk.java.net>  
2. Extract the zip file into the `C:\Program files` directory.  
3. Change the systemd variables: **add** `JAVA_HOME -> C:\Program Files\jdk` and **update** `Path -> C:\Program File\jdk\bin`.  
4. Open a cmd and type `java --version` to make sure.  

## Using IntelliJ for Java Development

1. Donwload IntelliJ and install it.
2. Create new project
3. Add a `Java Class` named `com.github.marcoandre1.Main` to the `src` folder (which creates a `com.github.marcoandre1.Main.java` file).  
4. Add a second `Java Class` named `com.github.marcoandre1.TitlecaseConverter` to the `src` folder.  

## Refactoring (Move code to a package)

1. Select both classes and right click on `Refactor` and chose `Move Classes...`.  
2. To package `com.example` (It is common use, to choose your reverse website for example).
3. Click on `Refactor`.
4. `com.github.marcoandre1.Main` and `com.github.marcoandre1.TitlecaseConverter` are now in the `com.example` package.

## Creating JAR files

1. Java applications are packaged into `JAR` files (for `Java ARchive`) which are basically `zip` files (you can unzip it).
2. A `jar` file contains the packages and a manifest.
3. Add a `TC-MANIFEST.MF` file with the following content: `com.github.marcoandre1.Main-Class: com.example.com.github.marcoandre1.Main`
3. Create a `jar` file: `jar cvmf TC-MANIFEST.MF com.github.marcoandre1.TitlecaseConverter.jar .`  
4. Run the `jar` file with the following command: `java -jar com.github.marcoandre1.TitlecaseConverter.jar`.

## Creating JAR files with IntelliJ

1. `File` menu -> `Project structure...`
2. `Artifacts` -> `+` -> `JAR` -> `From modules with dependencies...`
3. Choose `com.github.marcoandre1.Main Class` -> `OK`
4. Check `Include in project build` and `OK`
5. Build and `jar` file should be in `out` folder.
