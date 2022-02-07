# JavaFX setup on Visual Studio Code

In my case, I have used the following:  
- Intel Mac running macOS Monterey 12.2 (21D49)  
- Visual Studio Code for macOS, version: Version: 1.64.0 (Universal)  
- Java FX version: 17.0.1  

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

