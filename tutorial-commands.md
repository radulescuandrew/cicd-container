1. Build the docker image from the Dockerfile
   `docker build -t 14112020-youtube:latest .`

2. Check the created image
   `docker images`

3. Run the Docker image in interactive mode (it) and map the local port :80 to :3000 inside the container (Node app listens to 3000)
   `docker run -it -p 80:3000 {imageId}`

4. Login into ECR using get-email-password
   `aws ecr get-login-password --region eu-central-1 | docker login --username AWS --password-stdin 398529876976.dkr.ecr.eu-central-1.amazonaws.com`
   will display "Login Succeeded"
   More: https://docs.aws.amazon.com/cli/latest/reference/ecr/get-login-password.html

5. Tag the image
   `docker tag 14112020-youtube:latest {ECR URL}`

6. Push the image to ECR
   `docker push {ECR URL}:latest`
