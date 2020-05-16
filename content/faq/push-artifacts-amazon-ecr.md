---
title: "Can we push Docker images to Amazon ECR for faster pulls?"
description: "Yes, we use ECR with some of our customers."
tags:
- Docker
- Amazon ECR
- repository
- microservice
---

## Question

Can we push artifacts to Amazon ECR for faster pulls, instead of using Codefresh's Docker repository?


## Answer

Yes, we use ECR with some of our customers. The downside is that it does not support multiple image names per repository; they can only vary by tag. Anytime you want to deploy a new microservice, you must provision a new ECR repo, which makes things slightly more cumbersome albeit ultimately more secure. It requires a one-time ECR configuration via a [Terraform module](https://github.com/cloudposse/terraform-aws-ecr) (deployed with Atlantis) per new microservice.
