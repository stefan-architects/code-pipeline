> [!NOTE]
> In this next phase of the repository, I'm diving deeper into AWS CodePipeline by deploying an Angular application through a series of hands-on labs. Every README adds a new layer to the architecture, resulting in a production-grade CI/CD pipeline. Drawing on what I learned in **code-pipeline-s3**, I’ve set up a fresh environment to tackle these advanced deployment workflows and avoid misconfigurations.

## 1. 🌐 AWS CodeBuild Website
This project explores integrating AWS CodeBuild into AWS CodePipeline to automate build and test stages in a CI/CD workflow. It covers configuring build specifications (*buildspec.yml*), executing automated tests (*buildspec-test.yml*), compiling source code, and generating deployable artifacts for downstream deployment stages.

> [!NOTE]
> This README documents the implementation and execution of an AWS CodePipeline CI/CD workflow, highlighting AWS CodeBuild integration, build validation, and automated testing results. 

> [!IMPORTANT]
> The *buildspec.yml* and *buildspec-test.yml* files are not included in the repository.

## 2. 📐 CodeBuild Resources Utilized
| Service | Purpose |
| --- | --- |
| AWS CodePipeline | Automated the CI/CD deployment workflow |
| AWS CodeBuild | Built, test, and package application code |
| Amazon S3 | Store pipeline artifacts and host static websites |
| AWS IAM | Manage service roles and permissions |
| Amazon CloudWatch | Monitor pipeline executions, build logs, and errors |
| Amazon EventBridge | Triggered pipeline executions in response to events or schedules |
| GitHub | Hosts the source code repository |

## 3. 🔄 CodedBuild Workflow
1. Configured GitHub as the versioned source repository for CodePipeline.  
2. Created destination S3 buckets for build artifacts.  
3. Configured a two‑stage AWS CodePipeline workflow with CodeBuild handling build and test operations.  
4. Created IAM service roles and assigned required permissions for GitHub, CodeBuild, and S3 access.  
5. Pushed source code updates to GitHub to trigger CodeBuild builds and automated tests.  
6. Verified successful test completion and artifact delivery to both destination S3 buckets.

## 4. ✅ Deployment Results
- Verified deployment logs showed successful execution of all lifecycle events without warnings.
- Automated artifact delivery to both a public S3 website bucket and a remote destination bucket.
- Verified successful pipeline execution following updates to source objects.
- Used appspec files to define how application files are installed, validated, and started during deployment.
- Performed manual checks on application endpoints to verify functionality.

## 5. 🐞 Challenges and Troubleshooting
### Buildspec errors 
Fixed indentation, missing phases, or incorrect command syntax.

### Appspec placement errors 
Confirm appspec is located at the application root for proper deployment.

### Public bucket configuration errors
Confirm S3 bucket has public access and the required public access policies are applied.

## 6. 🎓 Knowledge and Skills Gained
### Build & Test Configuration
- Set up CodeBuild projects to run automated build and test steps in a CI workflow.  
- Added unit tests, integration tests, and validation scripts in the buildspec to keep builds reliable.  
- Set up test reports, log exports, and failure rules so CodePipeline can stop deployments when tests fail.

### Pipeline Integration
- Set up CodeBuild as the main build and test step in a multi‑stage CodePipeline.  
- Connected Amazon S3 buckets and GitHub repositories as sources that send code into the pipeline.  
- Updated pipeline steps and ran manual executions to check buildspec updates and confirm expected behavior.  
- Added an appspec file so CodeBuild outputs could move into CodeDeploy for deployment stages.

### CodeBuild Configuration & Management
- Set up CodeBuild environments with the needed runtimes, dependencies, and testing tools.  
- Handled build artifacts, environment variables, and test logs to keep CI runs consistent.  
- Set up parallel builds and tests triggered by GitHub commits and S3 updates.

### IAM & Security
- Created IAM roles for CodeBuild and CodePipeline using least‑privilege access.  
- Set permissions for S3 artifacts, GitHub integration, and test‑related resources.  
- Checked role access and service permissions during builds and tests.

### Monitoring, Logs & Troubleshooting
- Triggered CodeBuild builds and tests through pipeline runs, commits, and S3 updates.  
- Reviewed CodeBuild logs, test output, CloudWatch logs, and pipeline transitions to confirm results.  
- Fixed build and test issues by checking permissions, updating buildspecs, adjusting dependencies, and updating pipeline settings.

### Cleanup
No cleanup needed here — we’ll keep this environment running for the next section.

## 7. 🔍 Exploring Next
- CodeDeploy