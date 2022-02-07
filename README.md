# JavaFX setup on Visual Studio Code

In my case, I have used the following:  
- Intel Mac running macOS Monterey 12.2 (21D49)  
- Visual Studio Code for macOS, version: Version: 1.64.0 (Universal)  
- Java FX version: 17.0.1  

Steps Required at every new project created:
Step 8, Step 10, Step 11

Step 1:  
Download Java FX SDK for Linux, macOS or Windows from: https://gluonhq.com/products/javafx/  
  
Step 2: 
- Unzip it from your download folder  
  
Step 3:
- Inside the unzipped directory you should see 3 elements:
   1. "legal" directory
   2. "lib" directory
   3. src.zip file

Step 4:
- On macOS I have moved this to a location that is easy to find if searched from terminal:

```
marco@MacBook-Pro ~ % pwd
/Users/marco

marco@MacBook-Pro ~ % mkdir java  # This is a comment: You can name this as you prefer

marco@MacBook-Pro ~ % cd java
```

Step 5:
- I then moved the stuff I need from the the download folder to the new directory I created
```
marco@MacBook-Pro java % ls -l
drwxr-xr-x@ 6 marco  staff  192 Feb  2 19:47 javafx-sdk-17.0.1

# Check the content:
marco@MacBook-Pro java % cd javafx-sdk-17.0.1
marco@MacBook-Pro javafx-sdk-17.0.1 % ls -l
drwxr-xr-x@  9 marco  staff      288 Oct 16 21:20 legal
drwxr-xr-x@ 24 marco  staff      768 Oct 16 21:21 lib
-rw-r--r--@  1 marco  staff  6617560 Oct 16 21:20 src.zip
```
  
Step 6:
- These are the files we will need later on:
```
marco@MacBook-Pro javafx-sdk-17.0.1 % ls -l lib/*.jar
-rw-r--r--@ 1 marco  staff    37118 Oct 16 21:20 lib/javafx-swt.jar
-rw-r--r--@ 1 marco  staff   745855 Oct 16 21:20 lib/javafx.base.jar
-rw-r--r--@ 1 marco  staff  2545243 Oct 16 21:20 lib/javafx.controls.jar
-rw-r--r--@ 1 marco  staff   129482 Oct 16 21:20 lib/javafx.fxml.jar
-rw-r--r--@ 1 marco  staff  4371700 Oct 16 21:20 lib/javafx.graphics.jar
-rw-r--r--@ 1 marco  staff   281011 Oct 16 21:20 lib/javafx.media.jar
-rw-r--r--@ 1 marco  staff    88801 Oct 16 21:20 lib/javafx.swing.jar
-rw-r--r--@ 1 marco  staff   720357 Oct 16 21:20 lib/javafx.web.jar
```

Step 7:
- Open Visual Studio Code:
  1. In the left sidebar, select "Extensions"
  2. And then search for "JavaFX Support"
  3. Install it.
  4. VS may need to reload.

<img src="https://github.com/marcomandola/javafx_setup_VS_Code/blob/main/pic1.png" width="300" height="250">

Step 8:
- Open Visual Studio Code:
  1. Lower left Corner, click on the "Settings" icon (gear icon)
  2. Click Command Palette
  3. A pop up will open at the top of the screen, search for: "Java: Create Java Project"
  4. Select: No build tools
  5. VS will ask for the directory where to put all your projects (i.e. on my Mac: /Users/marco/VS_Java )
  6. Click on: "Select the project location"
  7. A pop up will open at the top of the screen, asking for the Project Name itself: "Input a Java Project name (Press "Enter" to confirm)"

<img src="https://github.com/marcomandola/javafx_setup_VS_Code/blob/main/pic2.png" width="300" height="250">
<img src="https://github.com/marcomandola/javafx_setup_VS_Code/blob/main/pic2a.png" width="500" height="50">

Step 9: (This step is needed for the first project only)
- In Visual Studio Code:
  1. Inside the project that has been created, go to the "src" folder, and open the App.java file that was generated automatically. (just open it) 
  2. Now, lower left corner, click on the "Settings" icon (gear icon)
  3. Click Command Palette
  4. A pop up will open at the top of the screen, search for: "Java: Configure Java Runtime"
  5. And install Java from there if you don't see it
  6. PICTURE
```
marco@MacBook-Pro ~ % java --version
openjdk 17.* 2021-10-19
OpenJDK Runtime Environment (build 17.*)
OpenJDK 64-Bit Server VM (build 17.*, mixed mode, sharing)
```

Step 10: IMPORT JAVA FX Library (this will be required for every project)
- In the left sidebar of the project, you will see a ".vscode" directory.
  1. There will be a settings.json file, we will need to add some entries there. 
  Change the file from:
```
{
    "java.project.sourcePaths": ["src"],
    "java.project.outputPath": "bin",
    "java.project.referencedLibraries": [
        "lib/**/*.jar"
    ]
}
```

  To:
```
{
    "java.project.sourcePaths": ["src"],
    "java.project.outputPath": "bin",
    "java.project.referencedLibraries": [
        "lib/**/*.jar",
        "/Users/marco/java/javafx-sdk-17.0.1/lib/javafx-swt.jar",
        "/Users/marco/java/javafx-sdk-17.0.1/lib/javafx.base.jar",
        "/Users/marco/java/javafx-sdk-17.0.1/lib/javafx.controls.jar",
        "/Users/marco/java/javafx-sdk-17.0.1/lib/javafx.fxml.jar",
        "/Users/marco/java/javafx-sdk-17.0.1/lib/javafx.graphics.jar",
        "/Users/marco/java/javafx-sdk-17.0.1/lib/javafx.media.jar",
        "/Users/marco/java/javafx-sdk-17.0.1/lib/javafx.swing.jar",
        "/Users/marco/java/javafx-sdk-17.0.1/lib/javafx.web.jar"
    ]
}
```  

Step 11: SETUP JAVA VM RUNTIME (this will be required for every project)
- Make sure you have your App.java file open and active on screen:
  1. At the top left corner of the screen click on "Run"
  2. Then click on "Add confifguration"
  3. This will bring up a "launch.json" file
  4. We will need to add the following string
  5. You will need to edit, inside the "Configurations" section, the area where you see "mainClass": "App" 
  6. ("App" could be different if you changed Main class name)
  7. We will need to edit here from: 
```
        {
            "type": "java",
            "name": "Launch App",
            "request": "launch",
            "mainClass": "App",
            "projectName": "Test_b89987b8"
        }
```

  To:
```
        {
            "type": "java",
            "name": "Launch App",
            "request": "launch",
            "vmArgs": "--module-path /Users/marco/java/javafx-sdk-17.0.1/lib --add-modules javafx.controls,javafx.fxml",
            "mainClass": "App",
            "projectName": "Test_b89987b8"
        }
```

Step 12: You can now try and run your app




