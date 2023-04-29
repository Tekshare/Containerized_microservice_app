### The Emart application microservice architecture.

- consist of the Nginx( APi gateway) that recives requests based on urls.
- The client microservice (Angular)recieves url root requests.this loads the front end pages of the website.
- On the backend data micosoft consist of Emart api which is returning nodeJS and the url will be /api, and NodejS apis will need a database and mongodb is been used.
- Another  service is the book api, this is written in java, it uses mysql database and its url is /webapi.


- The dockerfiles for client,nodejsapi and javaapi are multistage dockerfile. First stage is to build the artifact and the second stage is to copy the artifact into the main image or use the artifact. 

-  Using the official Nginx image for the apigateway, this cutomized configuration(default .conf) will be  attached as a volume to the official nginx configuration.

####N>B: after running docker build, the three custom image will be presented. also thi is just a test application.

### To run this application, clone the repository
- *Cd* into the  microsvc directory.
- (Optional)Run the installation script to install docker dependencies. type *./installations.sh* and press enter. also run *sudo chmod +x ./installations.sh*
- *Cd* into the emartapp directory. 
- Run *ls* to list out all files. 
- Next run, *sudo docker-compose build*. this will take a while to finish the build job.
- After completion, run *sudo docker-compose up -d*. this will bring start all microsoervices.
- To access the application, Copy and paste the VM Ip address to your brower and specify the port(<http://ipaddress:80>). (make sure inbound rule is set to allow port 80 on the vm NSG.
