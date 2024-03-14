# Dockerizing a simple HTML page using Nginx as the web server.

•	Create a plain HTML page named index.html with some content (e.g., "Hello, Docker!").
•	Nginx Configuration (nginx.conf)
•	Create an Nginx configuration file named nginx.conf that serves the index.html page.
•	Configure Nginx to listen on port 80.
•	Create a Dockerfile to define the Docker image.
•	Use an official Nginx base image.
•	Copy the index.html and nginx.conf files into the appropriate location in the container.
•	Ensure that the Nginx server is started when the container is run.
•	Build the Docker image using the Dockerfile run command: 
       docker build –t <your image name> . 
                        -t is denotes for giving a tag.
                        - . is denotes  for giving the path
•	After run this command build is successfully created 

•	Also check is image is created or not in desktop Docker run command : docker images

•	To run image into the container execute command: 
    docker run -it -p 80:80 -d <your – image- name>
                          -it denotes for to run in interwactive mode TTY
                          -p denotes for ports
                          -d denotes for detached mode (The Docker container running in the background).
 
•	Now we have to push our image into ECR (Elastic Container Registry)
                   Step: 1: Go to your AWS account.
                   Step: 2: Go to the services and search with ECR or Elastic Container Registry.
                   Step: 3: Create a public repository in ECR.
•	After create a repository now we have to install AWS CLI in our machine. Foe download the AWS CLI prefer official site: https://awscli.amazonaws.com/AWSCLIV2.msi
•	After setup the AWS CLI into the machine, now have to configure AWS CLI with our AWS account we need “I AM” or “Secret keys” and “Access Keys”
•	Now go to your command prompt and run command: aws configure; after run the command just copy paste your access key and secret key, region name.
•	AWS configure successfully.
•	Next step is we have to push or image into ECR (Elastic Container Repository). Below are the steps for that:
                  Step: 1: Go to your ECR Repository there is a button called “View Push command” click on it, then you will get the commands:
                  Step: 2: Copy first command and execute into your VS code terminal.
Note*:-
Now you may facing an error in execution of the command, for resolving this issue we have to follow few steps:
  Step: 1: Goto your .docker folder it is present in the c drive for my system the path is “C:\Users\pc\.docker” .
  Step: 2: There is file with name “Config.json”, make a duplicate file of itv and name it “Configbackup.json”.
  Step : 3: We have to make some correction in the main file “Config.json”, there is a line "credsStore": "desktop",   remove this and save.
  Step: 4 : Now go to your docker folder C:\Program Files\Docker\Docker\resources\bin, upto bin folder and rename a file “docker-credential-wincred” to “docker-credential-wincred.backup”. Just add.backup in the end and save it.

•	Now again execute the first command again, and its running fine.
Step 3: Run second command to build: 
Step 4: Run third command:
 
Make changes in the, if you want you can execute version.
Step: 5: Run fourth command:
If you have already pushed this image with the same name so its shows layer already exist: but in your case it will show the image pushing:

•	After pushing the image it will refelect in the ECR.
My Image url is: public.ecr.aws/s7f2n3x3/ankur_docker:V1.0
 
