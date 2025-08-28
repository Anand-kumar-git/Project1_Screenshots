Project: Reactjs E-commerce Application

Overview
This project demonstrates a complete CI/CD pipeline for containerized application deployment using Docker, GitHub, Docker Hub, Jenkins, AWS (EC2), and Uptime Kuma for monitoring and alerts.

The workflow includes:
1. Dockerizing the application
2. Automating build and deploy with Bash scripts
3. Using GitHub branch-based workflows for version control
4. Publishing images to public (dev) and private (prod) repositories in Docker Hub
5. Automating pipelines in Jenkins with GitHub webhooks
6. Deploying on AWS EC2 with secure access
7. Monitoring uptime with Uptime Kuma and Slack notifications

------------------------------------------------------------

1. Docker
- Created a Dockerfile to containerize the application
- Built and verified the Docker image locally
- Used docker-compose to run the application
- Tested the containerized application in the browser

2. Bash Scripting
Two automation scripts were created:
- build.sh → Builds the Docker image
- deploy.sh → Runs the Docker container on the server

These scripts make build and deployment consistent and repeatable.

3. Version Control (GitHub)
- Used GitHub for version control
- Performed all Git operations via CLI in VS Code terminal
- Created a custom branch named "dev" for development work
- Added .gitignore and .dockerignore files to exclude unnecessary files

4. Docker Hub
Created two repositories in Docker Hub:
- dev → Public repository for development builds
- prod → Private repository for production builds

Branch-based tagging ensures that:
1. Images from dev branch are pushed to the dev repository
2. Images from main branch are pushed to the prod repository

5. Jenkins (CI/CD Pipeline)
- Installed Jenkins and configured required plugins (Git, Docker, Pipeline, GitHub)
- Added Docker Hub credentials securely in Jenkins
- Created a Multibranch Pipeline Job
- Connected GitHub repo to Jenkins using webhooks for automated builds

6. AWS EC2 Deployment
- Launched a t2.micro Ubuntu EC2 instance
- Configured Security Groups:
  1. Port 22 (SSH) allowed only from my IP
  2. Port 80/3000 allowed for public application access
- Pulled the Docker image from the prod repository
- Started the container and verified the application in the browser

7. Monitoring (Uptime Kuma)
- Deployed Uptime Kuma to monitor application health
- Configured monitoring for application availability
- Integrated Slack notifications for instant alerts if the application goes down

------------------------------------------------------------

Conclusion
This project demonstrates:
1. End-to-end CI/CD with Docker, GitHub, Jenkins, and AWS
2. Secure handling of development and production workflows via Docker Hub
3. Automated builds and deployments using Jenkins pipelines
4. Real-time monitoring and alerting with Uptime Kuma and Slack

This ensures the application is always available, securely deployed, and automatically updated whenever code changes are pushed.
