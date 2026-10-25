# AWS 3-Tier Application Deployment

A hands-on AWS infrastructure and deployment project demonstrating networking, security, compute, database integration, DNS, TLS, and monitoring.

> **My contribution:** I configured and deployed the AWS infrastructure and integrated the application with the database. The original frontend and backend application code came from an existing project, which is credited below.

## Architecture Overview

### Frontend
- React/Vite static application hosted on Amazon S3.
- Amazon Route 53 configured for the custom domain.
- **Known limitation:** The direct S3 website endpoint uses HTTP.

### Backend
- Spring Boot REST API running on a private Amazon EC2 instance.
- Application Load Balancer provides the API entry point.
- AWS Certificate Manager (ACM) certificate enables HTTPS for the API.
- Health check configured at `/health`.

### Database
- Amazon RDS for MySQL in private subnets.
- Database security group restricts access to the backend security group.
- Contact form submissions verified in the `contact_messages` table.

### Networking and Security
- Custom Amazon VPC with public, private application, and private database subnets.
- Internet Gateway, NAT Gateways, and route tables.
- Security groups restrict backend and database traffic.
- AWS Systems Manager Session Manager used for instance administration without inbound SSH.

### Monitoring
- CloudWatch Agent installed and configured for EC2 monitoring.
- Further dashboards and alarms are potential improvements unless specifically implemented.

## AWS Services

Amazon VPC · EC2 · S3 · RDS · Application Load Balancer · ACM · Route 53 · IAM · Systems Manager · CloudWatch

## What I Worked On

- Configured AWS networking and subnet isolation.
- Deployed the backend and connected it to private RDS MySQL.
- Configured load balancing, API HTTPS, DNS, and security groups.
- Set up S3 static website hosting.
- Configured IAM and Systems Manager access.
- Troubleshot CORS, application health checks, DNS, environment variables, and database connectivity.

## Documentation

## Documentation

- [Architecture Overview](docs/architecture.md)
- [AWS Project Interview Guide (PDF)](docs/AWS%203-Tier%20Portfolio%20Project.pdf)

The guide covers the AWS architecture, networking, security groups, deployment steps, troubleshooting, monitoring, interview questions, and future improvements.

## Original Application Source

The frontend and backend application code were obtained from:

[Original repository — Dhana57/sample_portfolio](https://github.com/Dhana57/sample_portfolio)

My contribution to this portfolio focuses on AWS infrastructure, deployment, configuration, integration, and troubleshooting. The original repository currently has no visible license file, so this repository does not redistribute its application source code.

## Limitations and Future Improvements

- Configure HTTPS for the frontend using an appropriate TLS-capable hosting solution.
- Store database credentials in AWS Secrets Manager or Systems Manager Parameter Store.
- Add CloudWatch alarms and dashboards.
- Consider AWS WAF and API rate limiting.
- Evaluate Multi-AZ RDS for higher availability.
- Verify automated application bootstrapping before relying on Auto Scaling Group replacement instances.

## Disclaimer

This is a learning and portfolio project, not a claim of a fully production-hardened system. The documentation distinguishes implemented features from planned improvements.
