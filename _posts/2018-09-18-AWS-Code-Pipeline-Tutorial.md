---
layout: post
title:  "AWS Code Pipeline Tutorial for CI/CD"
description: "Tutorial on how to integrate GitHub repo to Code Deploy and Code Build"
date:   2018-09-18 18:00:00 +0800
categories: tutorial aws
---

{::options parse_block_html="true" /}


It's so convenient when you've implemented CI/CD to your project.
You commit and push to repository and viola, in minutes it will be deployed to your instance.


I Just want to share with you guys how I did CI/CD with AWS Code Pipeline.

summary of aws code pipeline?

1. Fetches changes from github using webhooks.  
2. The Source(github) will then be fed to codeBuild.  
3. codeBuild will pull the script form source/aws then run.  
4. codeBuild will produce output which will then fed to codeDeploy.  
5. codeDeploy will pull/execute the script from source/aws then run.  





### There are 6 Steps to create pipeline.

#### Step 1. Pipeline Name

The instructions is simple, just enter your pipeline name.  

<img class="responsive-img" src="/assets/img/posts/tutorial/aws_pipeline/step1_enter_name.png" alt="Field asking you to enter the name of the pipeline">


#### Step 2. Repository Branch

In Step 2, you have to login and authorize aws to access your repository and pick the repository and branch of your project.  

<img class="responsive-img" src="/assets/img/posts/tutorial/aws_pipeline/step2_repo_branch.png" alt="Fields asking your git Repository and branch">

#### Step 3. CodeBuild

In Step 3, you have to choose which CI to integrate with, you can check other tutorial for this specific parts or my later post.  

You can choose to have no CodeBuild at all by choosing *no build*  

If you choose AWS CodeBuild it will redirect you to codebuild and will let you create one if you didn't have any codeBuild created yet.  

<img class="responsive-img" src="/assets/img/posts/tutorial/aws_pipeline/step3_build.png" alt="Showing Dropdown asking for CodeBuild implementation ex. No Build,Add Jenkins,AWS CodeBuild,Solano CI">

#### Step 4. CodeDeploy

For Code Deploy, you have to create a CodeDeploy first.
If you don't have one yet then you will be redirected to new tab to create your CodeDeploy Project.

<img class="responsive-img" src="/assets/img/posts/tutorial/aws_pipeline/step4_deploy.png" alt="Showing Dropdown of supported codeDeploy / Continuous Deployment platform">

Choose or create a rol that have sufficient permission to access all the resources it needs.  
#### Step 5. Define Service Role
<img class="responsive-img" src="/assets/img/posts/tutorial/aws_pipeline/step5_role.png" alt="AWS Service Role">

#### Step 6. Review

Review All your configurations and settings if correct.

<img class="responsive-img" src="/assets/img/posts/tutorial/aws_pipeline/step6_review.png" alt="Review all your configurations placed">


That's all and you're good to go.

Thanks for reading!
