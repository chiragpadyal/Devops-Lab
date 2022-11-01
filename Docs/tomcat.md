> Download tomcat from official website tar.gz 

```
cd ~/Downloads
tar xzvf apache-tomcat-9*tar.gz
cd tomcat #folder name differs
cd conf
```
```
gedit server.xml
```
> replace 8080 with 8888
```
cd ..
cd bin
./startup.sh
```
> visit localhost:8888
```
cd ..
cd conf
gedit tomcat-users.xml
```
> add following in center of file not start not end
```
  <user username="manager" password="1234" roles="manager-gui"/>
  <user username="admin" password="1234" roles="admin-gui"/>
  <user username="deployer" password="1234" roles="manager-script"/>
```

> restart server
```
cd ..
cd bin
./startup.sh
```
> visit localhost:8888 , then click manage app and login with 
> username: manager
> password: 1234

```
cd ..
cd webapps
ls
```
> if jenkins.war exist delete it
```
rm jenkins.war
```
```
locate jenkins.war
cp <output from prev command> .
ls
```
> jenkins.war file must there now,

> restart the server
```
cd ..
cd bin
./startup.sh
```

> visit localhost:8888 , then click manage app and login with 
> username: manager
> password: 1234
> new route /jenkins will be visible

```
failed process
Install Deploy to Container Plugin.
Manage Jenkins -> Manage Plugins -> Available -> Deploy to Container Plugin
• Create and Configure a Maven Job with Source Code Management (Github)
New Item -> Maven Project
• Configure the Post-build Action and Specify the Tomcat Server Details
• Drag to the bottom and Go to the Post-build Actions section
• Click on Add post-build action button
• On the available options click on the Deploy war/ear to container
• Execute the Job you have created by clicking on the Build Now button
• Testing the Application
```


