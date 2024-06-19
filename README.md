# Static Website Deployment Using AWS CodePipeline

## Project Overview
This project sets up a two-stage CI/CD pipeline to automatically deploy a static website to an Amazon S3 bucket. The website is a simple HTML page displaying my name, <Christian Logotse>. The source code is hosted in my personal GitHub repository.

## Prerequisites
- An AWS account
- AWS CLI configured
- A GitHub account with the source repository
- AWS CodePipeline, and S3 configured

## Pipeline Setup

### 1. Create an S3 Bucket
1. Create an S3 bucket to host your static website.
    ```sh
    aws s3 mb s3://my-static-website-bucket
    ```

2. Enable static website hosting on the bucket.
    ```sh
    aws s3 website s3://my-static-website-bucket/ --index-document index.html
    ```

### 2. Create a GitHub Repository
1. Create a new repository on GitHub <staticweb-cicd-bucket> and push your HTML file. :
   git clone
   git add <filename>
   git commit -m
   git push 
   
    ```

    ```

### 4. Create the CI/CD Pipeline
1. Create a pipeline using AWS CodePipeline with two stages: Source (GitHub) and Deploy (S3).
    ```sh
    aws codepipeline create-pipeline here I use the console to create the pipeline
```

## Accessing the Static Website
- Navigate to your S3 bucket's website endpoint URL, which will look like:
  ```
  http://my-static-website-bucket.s3-website-us-west-2.amazonaws.com
  ```

## Repository Contents
- `index.html`: The HTML file for the static website.
- Screenshots of the CI/CD pipeline stages.

## Showcase
- [GitHub Repository](https://github.com/your-username/your-repository)
- [S3 Website URL](http://my-static-website-bucket.s3-website-us-west-2.amazonaws.com)
- Screenshots of the CI/CD pipeline:
  - ![Pipeline Stage 1](path-to-screenshot-1)
  - ![Pipeline Stage 2](path-to-screenshot-2)

## License
This project is licensed under the @christian@ License.
