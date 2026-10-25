# AWS 3-Tier Architecture

## Project overview

This repository documents my AWS infrastructure and deployment work for a three-tier web application. The application source was obtained from an existing project.

## AWS architecture

- Amazon VPC with public and private subnets
- Internet Gateway and NAT Gateways
- Amazon S3 static website hosting
- Application Load Balancer with HTTPS for the API
- Private Amazon EC2 instance running Spring Boot
- Private Amazon RDS for MySQL
- Amazon Route 53 for DNS
- AWS Systems Manager Session Manager
- CloudWatch Agent for EC2 monitoring

## Request flow

Frontend:
Browser -> Route 53 -> S3 static website

Backend:
Browser -> HTTPS API -> Application Load Balancer -> Private EC2

Database:
Spring Boot -> Private Amazon RDS for MySQL

## My contribution

I configured the AWS networking, security groups, compute and database connectivity, DNS, API TLS, instance administration, monitoring setup, and application deployment troubleshooting.

## Known limitation

The direct S3 website endpoint uses HTTP. The API endpoint uses HTTPS. CloudFront was not used in this project.

## Original application source

https://github.com/Dhana57/sample_portfolio

The frontend and backend application code originated from this repository. This project focuses on my AWS infrastructure and deployment work.
