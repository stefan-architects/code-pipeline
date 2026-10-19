## 🌐 1. CodePipeline Basics Website Exercises
This README covers two CodePipeline deployments designed to help learn the basics by creating a custom two-stage pipeline using a versioned S3 bucket and GitHub as the source repository.
- **Pipeline 1:** Deploys a static website from a private S3 source bucket to both a public S3 bucket and a remote S3 bucket.
- **Pipeline 2:** Deploys the same static website from a GitHub repository to a public S3 bucket.

## 2. 📌 Completed as part of this exercise.
- Built a two‑stage pipeline between versioned S3 buckets  
- Triggered the pipeline by updating the source bucket  
- Reviewed pipeline history and execution details  
- Modified the pipeline and manually triggered a new run  
- Connected GitHub to AWS Dev Tools  
- Created a pipeline linked to my GitHub repository  
- Triggered the pipeline through GitHub commits  
- Removed the pipeline after completing the exercise
- Added a remote bucket to trigger a parallel update

## 3. 🚀 Deployment Architecture
### S3 Source Pipeline & Parallel Deployment
![s3-pipeline-deployment](images/demo-pipleline-s3.png)

### 🦑 GitHub App Deployment
![github-deployment](images/demo-pipleline-github.png)

## 4. ❌ Troubleshooting
### ⚠️ Issue 1: Incorrect Destination Bucket
- **Issue:** The pipeline was configured with the wrong destination bucket.
- **Investigation:** Rechecked bucket permissions, policies, and IAM roles.
- **Resolution:** Reconfigured the pipeline with the correct destination bucket and re-ran deployment.

### ⚠️ Issue 2: Incorrect ZIP File Name
- **Issue:** The pipeline was configured with an incorrect ZIP file name.
- **Investigation:** Reviewed the pipeline configuration and verified the incorrect ZIP file.
- **Resolution:** Updated the pipeline with the correct ZIP file name and re-ran pipeline.

## 5. 👁️ Key Takeaways
- Built and modified multi‑stage pipelines using both versioned S3 buckets and GitHub repositories, gaining hands‑on experience with different source triggers.  
- Triggered automated pipeline runs through S3 updates and GitHub commits, reinforcing how event‑based workflows initiate CI/CD processes.  
- Reviewed pipeline execution history and logs to understand how each stage processes artifacts and how AWS tracks workflow progress.  
- Manually adjusted pipeline configurations, triggered new runs, and removed pipelines after completion to practice full lifecycle management.  
- Added a remote S3 bucket to trigger parallel updates, demonstrating how pipelines can coordinate multiple sources and workflows.

## 6. 🔍 Exploring Next
- CodeBuild