# DevOps Project - Continuous Integration of Vprofile Project on AWS Cloud

This is a DevOps project for _Continuous Integration_ of vprofile project on [AWS Cloud](https://aws.amazon.com/) using [AWS CodeCommit](https://aws.amazon.com/codecommit/), [AWS CodeArtifact](https://aws.amazon.com/codeartifact/), [AWS Systems Manager Parameter Store](https://docs.aws.amazon.com/systems-manager/latest/userguide/systems-manager-parameter-store.html), [SonarCloud](https://www.sonarsource.com/products/sonarcloud/), [Amazon S3](https://aws.amazon.com/s3/), [AWS CodeBuild](https://aws.amazon.com/codebuild/), [AWS CodePipeline](https://aws.amazon.com/codepipeline/), [Amazon SNS](https://aws.amazon.com/sns/).

[Link](https://github.com/durrezahmed/vprofile-project-devops) for vprofile app repository.

## Problems with CI Server:

- CI Server Maintenance

- Operational Overhead to maintain Servers like Jenkins, Nexus, Sonar, Git etc

## Solution - Fix:

- Cloud Services for CI to Remove Ops Overhead

## CI Pipeline on AWS - Benefits:

- Short MTTR (Mean Time to Recovery)

- No Human Intervention

- Fault Isolation

- Agile

- No Ops

## AWS Services and Tools used in the Project:

- **AWS CodeCommit** - Version Control System

- **AWS CodeArtifact** - Maven Repository for Dependencies

- **AWS CodeBuild** - Build Service from AWS

- **Amazon S3** - Artifact Deployment

- **Checkstyle** - Code Analysis Tool

- **SonarCloud** - SonarQube Cloud based Tool

- **AWS CodePipeline** - Service to Integrate all Jobs Together

- **Amazon SNS** - Notification Service from AWS

## Usage (Flow of Execution):

1. **Login to AWS account** - [Link](https://aws.amazon.com/marketplace/management/signin) to Login to your AWS Account.

2. **AWS CodeCommit**

   a. Create CodeCommit repo

   b. Create IAM user with CodeCommit policy

   c. Generate SSH keys locally

   d. Exchange keys with IAM user

   e. Put source code from github repo to cc repository and push

3. **AWS CodeArtifact**

   a. Create an IAM user with code artifact access

   b. Install AWS CLI, configure

   c. Export Auth token

   d. Update settings.xml file in source code top level directory with below details

   e. Update pom.xml file with repo details

4. **SonarCloud**

   a. Create Sonar Cloud account

   b. Generate token

   c. Create SSM parameters with Sonar details

   d. Create Build project

   e. Update CodeBuild role to access SSM Parameter Store

5. **Create Notifications for SNS or Slack**

6. **Build Project**

   a. Update pom.xml with artifact version with timestamp

   b. Create variables in SSM - Parameter Store

   c. Create Build project

   d. Update CodeBuild role to access SSM Parameter Store

7. **Create Pipeline**

   a. CodeCommit

   b. Test Code

   c. Build

   d. Deploy to S3 Bucket

8. **Test Pipeline**
