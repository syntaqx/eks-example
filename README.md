# EKS Workflow

A simple build out workflow that demos the ability to build & push a Docker Container to Docker Hub (for Collaboration), then push the tag to ECR (for deployment sake), and deploy the image on EKS (Elastic Kubernetes Service).

This is the smallest amount of effort to get this functioning, but it works, and is very simple to expand on.

## Variables & Secrets

To make the workflow as modification free as possible, all the values you should require to enable this for yourself are set via Variables & Secrets.

### Variables

- `EKS_CLUSTER_NAME` - The name of the cluster created via Pulumi in `infra`

### Secrets

- `DOCKERHUB_USERNAME`
- `DOCKERHUB_TOKEN`
- `AWS_ACCESS_KEY_ID`
- `AWS_SECRET_ACCESS_KEY`

## Manual Steps

1. Run `infra` directory using `pulumi up`
2. Grab the `EKS_CLUSTER_NAME` value from AWS and populate the GitHub Secrets
   - TODO: This can be automated in Pulumi, but I'm lazy right now.

## TODO

- [ ] Use GitHub OIDC to authenticate to EKS directly
- [ ] Use GitHub Actions to deploy the Pulumi stack
- [ ] Use Pulumi to set required GitHub Secrets

## Note

This flow does function, and you can see it functioning historically, but I've destroyed the eks-cluster configured as I don't wanna spend money on it ;)
