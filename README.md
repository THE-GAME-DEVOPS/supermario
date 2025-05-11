## Project Concept

This project covers the full lifecycle of deploying a containerized web application on AWS. It includes designing a custom VPC with subnets and routing, securing resources with Security Groups, launching and configuring an EC2 instance, installing Docker and Docker Compose, and deploying a Docker image from Docker Hub for a browser‑based application.

## Project Overview

The solution consists of the following key elements:

- **VPC & Networking**: Dedicated VPC with a public subnet, Internet Gateway, and routing rules.
- **Security**: Security Group allowing SSH for administration and your chosen application traffic port.
- **Compute**: EC2 instance launched in the public subnet; Docker and Docker Compose installed.
- **Container Deployment**: Running the `pengbai/docker-supermario:latest` image to serve the application.

## Architecture Diagram

![Infrastructure Diagram](diagram.png)

## Deployment

1. **Network Setup**  
   Use the AWS Console to create the VPC, subnet, Internet Gateway, and route table.

2. **Security Group**  
   Create a Security Group with rules for SSH and your chosen application port.

3. **Launch EC2**  
   Select an AWS AMI, place it in the public subnet, and attach the Security Group.

4. **Instance Configuration**  
   Install Docker & Docker Compose — either automatically via EC2 User Data or manually through the terminal—and create a Docker Compose file mapping the container’s internal port to a host port.

## Steps to run container

```bash

docker pull pengbai/docker-supermario:latest


docker run --rm -p 8600:8080 pengbai/docker-supermario:latest
```

- `docker pull` downloads the Super Mario emulator image from Docker Hub.
- `--rm` automatically removes the container when it stops.
- `-p 8600:8080` maps a port on the host to the container’s internal port.
- After running, open `http://localhost:8600` or `http://<IP_SERVER>:8600` to verify the application.

## Final Thoughts

Congratulations on completing this project! You’ve successfully configured AWS networking and security, launched and prepared an EC2 instance, and deployed a containerized application from Docker Hub. These achievements lay the groundwork for more advanced cloud-native development and operations—keep exploring and building on these skills.

<p align="center">
  <img src="https://i.giphy.com/media/v1.Y2lkPTc5MGI3NjExNXY3NDdrZHQwN3dsbmE5eTNnZG10Nm1ucXB1bXRhcHBsNnRrdnJoeSZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/bKBM7H63PIykM/giphy.gif" width="70%">
</p>

