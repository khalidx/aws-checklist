# aws-checklist

A checklist intended to help organizations evaluate their AWS production readiness.

## Introduction

This checklist is your guide to the best practices and necessary considerations when deploying secure, highly available infrastructure and applications to the Amazon Web Services cloud.

Here are some other great checklists, for your reference:

- [Gruntwork.io Production Readiness Checklist](https://www.gruntwork.io/devops-checklist/)

## Availability

- [ ] Are your applications configured to run across multiple AZs (availability zones)?
- [ ] Are your applications configured to run across multiple regions
- [ ] Have you tested application failover?
- [ ] Do you have at least two copies of every stateless application running?

## Scaling

- [ ] Have you requested an increase for your AWS service limits?

## Fault Tolerance

- [ ] Are your services built for graceful degradation?
- [ ] Do your applications implement patterns such as retries, exponential backoff, circuit breaking, timeouts, deadlines, and rate limiting?
- [ ] Do you run load tests?
- [ ] Have you determined and documented all bottlenecks of your infrastructure?
- [ ] Do you use *chaos engineering* to test the resilience of your infrastructure?

## Continuous Integration

- [ ] Is all code and infrastructure configuration checked in to a version control system (VCS)?
- [ ] Do you have a review process for application code?
- [ ] Do you have a review process for infrastructure configuration?
- [ ] Are all your application dependencies explicitly defined and captured in a lock file?
- [ ] Do you run static analysis on your code for linting and code coverage?
- [ ] Is your code automatically formatted into a consistent style?
- [ ] Does your build system run automated tests on your code?
- [ ] Does your build system run automated tests against your running application?
- [ ] Does your build system publish versioned, immutable artifacts to an artifact repository like ECR or Nexus?

## Continuous Delivery

- [ ] Do you have separate deployment environments?
- [ ] Are you using a separate production account?
- [ ] Is all your infrastructure defined as code?
- [ ] Are you promoting artifacts to higher environments, rather than creating new artifacts?
- [ ] Does your delivery pipeline successfully rollback in case of failure?
- [ ] Are you using blue-green deployments (for stateless applications) and rolling deployments (for stateful applications) for zero-downtime deployments?
- [ ] Do you use canary deployments to minimize the impact of bugs when introducing new changes?
- [ ] Do you use feature toggles to separate the deployment of new code from the release of new features?

## Cost

- [ ] Are you automatically scaling down resources when they are not in use?
- [ ] Are you automatically removing old backups and stale data?
- [ ] Are you automatically migrating data to lower-cost storage tiers?
- [ ] Are you automatically cleaning up old log data?

## Data

- [ ] Are database backups scheduled automatically?
- [ ] Does your database suppoort automatic failover and read replicas?
- [ ] Have you configured cross-account backup for redundancy and attack protection?
- [ ] Have you tested your data backups?

## Networking

- [ ] Have you created custom Virtual Private Clouds (VPCs) in your account with separate IP address ranges?
- [ ] Have you configured three subnet *tiers* in each VPC (public, private, protected)?
- [ ] Have you configured Network Access Control Lists (NACLs) to control traffic between subnets?
- [ ] Have you configured least-privilege security groups?

## Servers

- [ ] Are you building AMIs for any apps running directly on EC2 instances?
- [ ] Are your AMIs deployed using Auto Scaling Groups?
- [ ] Are your Docker images pushed and versioned in the Elastic Container Registry (ECR)?

## Applications

- [ ] Is your application configured to use all available CPU cores and memory?

## Web

- [ ] Are all your CSS, JavaScript, images, and other assets minified and compressed?
- [ ] Are you using CloudFront as a CDN for caching and content distribution?
- [ ] Are you measuring latency for requests to your content?

## Security

- [ ] Are all application secrets encrypted?
- [ ] Are you monitoring changes in CloudTrail to detect undesired resource creation and modification?

## IAM

- [ ] Does each developer have their own EC2 KeyPair to SSH into servers?
- [ ] Are all issued KeyPairs rotated often?
- [ ] Do you have a process for removing a KeyPair when someone leaves the organization?
