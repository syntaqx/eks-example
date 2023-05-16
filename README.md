# EKS Workflow

A simple build out workflow that demos the ability to build & push a Docker Container to Docker Hub (for Collaboration), then push the tag to ECR (for deployment sake), and deploy the image on EKS (Elastic Kubernetes Service).

This is the smallest amount of effort to get this functioning, but it works, and is very simple to expand on.

## Secrets

- `EKS_CLUSTER_NAME` - The name of the cluster created via Pulumi in `infra`
- `DOCKERHUB_USERNAME`
- `DOCKERHUB_TOKEN`
- `AWS_ACCESS_KEY_ID`
- `AWS_SECRET_ACCESS_KEY`

## Manual Steps

1. Run `infra` directory using `pulumi up`
2. Grab the `EKS_CLUSTER_NAME` value from AWS and populate the GitHub Secrets
   - TODO: This can be automated in Pulumi, but I'm lazy right now.
