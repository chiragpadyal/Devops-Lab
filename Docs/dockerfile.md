# Build an image for a sample web application from a docker file using various docker file instructions

> To perform this experiment we will use https://labs.play-with-docker.com/
1. Once your session is active click on “Add New Instance”:

2. A new instance will start with a Docker Engine ready to accept commands
![image](https://user-images.githubusercontent.com/89484481/198840211-979e4fdd-c45a-46ea-a62e-898665c26c09.png)


3. Next create/edit the Dockerfile. Run “vi Dockerfile”, press “i” to switch to “Insert Mode”, copy/paste the contents of our Dockerfile, 
  press “Esc” to exit “Insert Mode”, and save+exit by typing “:x”
![image](https://user-images.githubusercontent.com/89484481/198840238-ea267497-ddfc-49f5-be5e-7866f9d0c862.png)


4. Build the new image using the command docker build <path>. Path refers to the directory containing the Dockerfile.
![image](https://user-images.githubusercontent.com/89484481/198840257-4751d003-43e0-4ce7-bb35-317705f0b7fc.png)


5. At the end of the process you should see the message “Successfully built <image ID>”
![image](https://user-images.githubusercontent.com/89484481/198840282-d086dafd-433d-4173-bb10-4291be45df72.png)

  
6. Start the new image and test connectivity to NGINX. Run the command 
```bash
docker run -d -p 80:80 <image ID>
```
>The option -p 80:80 exposes the Container port 80 as the Host port 80 to the world
![image](https://user-images.githubusercontent.com/89484481/198840301-c37993cd-9ef9-4647-a5d6-4a479d38e86c.png)


7. As a result a port 80 link should have become active next to the IP. Click on it to access your NGINX service
![image](https://user-images.githubusercontent.com/89484481/198840318-db76fb0a-aedc-41e7-b616-f1af3270d801.png)
