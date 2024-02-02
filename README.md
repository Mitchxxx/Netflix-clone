<center>

<img src="./netflix.png" alt="amazon Poster"/>

# Steps to Execute

## Clone and build project
```
1. Fork or Clone Repository
2. cd into the app directory
3. Install dependencies, use Yarn install
4. Run app locally,  use Yarn start
5. Check the app on your Browser using localhost or server ip and the port it is listening on.
```
## Dockerize Application
```
6. Create Dockerfile for your react app, use nginx to serve the static assets

7. Build Docker Image by using the docker build command
   a. docker build -t repoName/imageName:tag .

8. Run the container by using the docker run command to confirm application still works
  a. docker run -d -p 3000:80 nameOfImage
  b. Go to Browser and confirm your containerised app works using your localhost or server IP and the port e.g localhost:3000

9. Log onto your AWS Console and type ECR on the search bar and click on it. ECR = Elastic Container Registry

10. Create a repository,
   a. click on private
   b. type in repo name
   c. Enable Scan on Push
   and Click on Create

11. Click or enter into your repository and click on the view push commands

12. Go to your terminal and follow each steps provided by aws

13. Congratulations, You have made your first ECR push
```

## AUTOMATE THE ENTIRE STEPS TO PUSH YOUR IMAGE TO ECR USING JENKINS
```
1. Create an ECR key in Jenkins Key Storage using your aws access and secret key
2. Create a Jenkinsfile or Add one
3. Go to your Jenkins workspace and Create a Pipeline Job
4. Build your Job
5. Go to ECR and confirm Image was succesfully pushed
```


</center>

