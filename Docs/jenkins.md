# To understand Continuous Integration, install and configure Jenkins with Maven

## Installation Steps for Jenkins on Ubuntu 
#### Step 1: Install Java
```
sudo apt-get update
```
```
sudo apt-get install default-jdk
```
#### Step 2: Download the latest jenkins.deb file from jenkins.io website by selecting ubuntu distribution.

>Once downloaded, double click on file and open with software center. 
Click on install button to perform installation.
Once Installation is done, you can test the jenkins on http://localhost:8080 on the browser.
First time, when you open jenkins portal it will ask to put admin default password which is stored in
```
 /var/lib/jenkins/secrets/initialAdminPassword file.
```

```
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```

> Copy the password and paste it in the browser and click on continue.

#### Step 3: Install suggested plugins
```
Once you click on continue, it will ask to install suggested plugins. Click on install suggested plugins.
```
#### Step 4: Create Admin User
```
Once plugins are installed, it will ask to create admin user. Enter username and password and click on save and continue.
```
#### Step 5: Jenkins is ready
```
Once you click on save and continue, it will take you to jenkins home page. 
                    or 
Open Jenkins dashboard using http://localhost:8080 address.
```

### Lab 1.1: Let's Deploy a Freestyle App in Jenkins
#### Step 1: Create a new job
```
Click on new item and enter the name of the job and select freestyle project and click on ok.
```
#### Step 2: Configure the job

>In this project we are going to learn how to run simple shell script on Jenkins. 
>So,Click on Build option select Execute script from dropdown menu.
>Once you click on ok, it will take you to the configuration page of the job.


#### Step 3: Write a Simple Shell command to print the text as Like given below.
>Enter the shell script in the text area and click on save.
    
```
echo "Hello World"
```
>Now click on apply followed by save button.

#### Step 3: Now Build a project to see the output Click on our first build “1” followed by console output to see the output.
```
Hello World
```

### Lab 1.2: 
>Now let us take parameters through files. So, create a new shell script file in local directory.

>Open Terminal and type the following command to create a file.

```
cat example.sh
```

```
#!/bin/bash
name=$1
Address=$2
echo "Hello $name, Welcome to $Address"
```
```
sh example.sh 
```
```
sh example.sh anuj
```
```
sh example.sh anuj thane
```

>After running the shell script locally with no parameter, one parameter and two parameters.
Now. Let us run it through Jenkins Shell. To change existing program, click on configure option
and then modify the script. <Here, change directory to the path where you have stored your
file..You can get the location by pwd command>

```
#!/bin/bash
sh /home/anuj/Desktop/example.sh $name $Address
```
>Now, click on apply and save button. Now, build the project and check the output.

### Lab 1.3: Running a Java Program under jenkins 

#### Step 1: Write a java program and test it locally
```
cat HelloWorld.java
```
```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World"); 
    }
}
```
```
javac HelloWorld.java
```
#### Step 2: Create a new job in Jenkins
```
Click on new item and enter the name of the job and select freestyle project and click on ok.
```
>Go to build option and change path to directory where you have stored java file followed by
compile and run program commands.
>Now if your build fails due to permission problem then give write permission to directory
underneath it.
```
chmod -R 777 /home/anuj/Desktop
```
>And remove existing .class file from your current directory
```
rm HelloWorld.class
```

>Now, build the project and check the output.

## Configure Maven in Jenkins

>Goto Manage Jenkins > Global Tool Configuration > Maven > Add Maven > Name: Maven > Install
>Go to Jenkins Dashboard > New Item > Enter Item Name > Maven Project > OK

>On configure page set the following:
```
Name: Maven
Description: Maven Project
```
>Source Code Management > Git > Repository URL:
```
>Build -> Advanced -> Enable the following options:
```
```java
Goals and options: clean install
```
>Post-build Actions -> Archive the artifacts -> Add the following:
```java
Files to archive: target/*.jar
```
>Build Now


>Go to Jenkins Dashboard > Maven Project > Build Now






