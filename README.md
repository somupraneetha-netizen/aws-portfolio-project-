# AWS Portfolio Website with CI/CD

## Project Overview
A personal portfolio website hosted on AWS to showcase my technical skills, projects, and professional profile. The project uses GitHub Actions to automate website deployment to Amazon S3 and refresh the CloudFront cache whenever changes are pushed to the `main` branch.

## Technologies Used
- **Frontend:** HTML, CSS, JavaScript
- **Hosting:** Amazon S3
- **Content Delivery:** Amazon CloudFront
- **Access Security:** CloudFront Origin Access Control (OAC)
- **CI/CD:** GitHub Actions
- **Authentication:** AWS IAM with GitHub OIDC
- **Monitoring:** Amazon CloudWatch
- **Version Control:** Git and GitHub

## Website Pages
- Home — Introduction and professional profile
- About — Personal and educational background
- Skills — Technical skills
- Projects — Project portfolio
- Contact — Contact information

## Architecture

Developer → GitHub Repository → GitHub Actions → AWS IAM via OIDC → Amazon S3 → Amazon CloudFront → Website Visitors

CloudWatch is used to monitor CloudFront metrics through a dashboard and alarm.

## CI/CD Workflow
1. Update the website source code.
2. Commit and push changes to the `main` branch.
3. GitHub Actions starts the deployment workflow.
4. GitHub authenticates with AWS using OpenID Connect (OIDC).
5. AWS credentials are configured by assuming the deployment IAM role.
6. The workflow synchronizes website files to the S3 bucket.
7. CloudFront cache invalidation makes updated content available.
8. Verify the deployment through the live website and GitHub Actions logs.

## Security
- The S3 bucket is kept private.
- CloudFront Origin Access Control restricts origin access.
- GitHub Actions uses OIDC to obtain temporary AWS credentials instead of storing long-lived AWS access keys in GitHub secrets.
- IAM permissions are configured for the deployment tasks.

## Key Learnings
- Hosting a static website on AWS.
- Configuring CloudFront with a private S3 origin.
- Implementing CI/CD using GitHub Actions.
- Configuring IAM roles and OIDC authentication.
- Automating S3 synchronization and CloudFront invalidation.
- Monitoring CloudFront metrics with CloudWatch.

## Future Enhancements
- Configure a custom domain.
- Add a functional contact form.
- Improve accessibility and responsive design.
- Extend monitoring and deployment validation.

## Project Links
- **Live Website:** [d2jpzwr8dk18em.cloudfront.net]
- **GitHub Repository:** https://github.com/somupraneetha-netizen/aws-portfolio-project
