# Continuous Integration and Deployment for a Kubernetes Application

### Introduction

This project showcases the implementation of a continuous integration and deployment (CI/CD) process for a Kubernetes-based application, leveraging Terraform for managing Amazon EKS infrastructure, Jenkins for building and orchestrating the pipeline, and Amazon EKS for a reliable, managed Kubernetes cluster. The main goal is to automate the deployment of an NGINX web application to an Amazon EKS cluster, ensuring efficient and reliable build and deployment processes. The CI/CD pipeline demonstrates the seamless integration of various DevOps tools and practices, each contributing a unique advantage to the pipeline.

### Final Output

The final output of the project is a working NGINX web application deployed to an Amazon EKS cluster. Users can access the app by visiting the load balancer URL of the Kubernetes service. The CI/CD process ensures that any changes made to the code are automatically built and deployed(using webhooks for build triggers), streamlining updates and improvements to the app.

## CI/CD Process
![Screenshot 2023-04-30 at 11 30 27](https://user-images.githubusercontent.com/117165801/235343532-f54ac9e6-8e15-4345-bfd1-8cdbbbd8cd89.png)


1.  Developers push code changes to the repository.
2.  Jenkins detects the changes and triggers a build based on the Jenkinsfile configuration.
Jenkins executes the "Create an EKS Cluster" stage, which uses Terraform (utilizing official modules) to provision the required Amazon EKS infrastructure, including the VPC, subnets, security groups, and other necessary components.
4.  Jenkins moves on to the "Deploy to EKS" stage, where it updates the Kubernetes configuration with the newly created EKS cluster and deploys the NGINX web application using the Kubernetes manifest files (nginx-deployment.yaml and nginx-service.yaml).
5.  The NGINX application is now accessible to users via the load balancer URL of the Kubernetes service.

### Kubernetes Application

NGINX web server deployed to an Amazon EKS cluster. In this project, the application is only used to demonstrate how to integrate Kubernetes deployments with  CI/CD process.

### Conclusion

This project highlights the effectiveness of combining powerful DevOps tools like Terraform, Jenkins, and Amazon EKS to create a robust CI/CD pipeline for a Kubernetes-based application. The automated build and deployment process enables developers to focus on application development, while the pipeline takes care of deploying updates and improvements efficiently and reliably. 
