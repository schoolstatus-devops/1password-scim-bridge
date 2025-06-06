# 1Password SCIM Bridge deployment examples

You can deploy 1Password SCIM Bridge on any supported infrastructure that allows ingress from your identity provider and egress to 1Password servers. This repository includes examples for deploying 1Password SCIM Bridge on selected platforms, information to help you plan your deployment, and links to related external repositories and support articles.

## Before you begin

Read this documentation to help you plan your deployment:

- Learn more about [automating provisioning in 1Password using SCIM](https://support.1password.com/scim/).
- Review the [Preparation Guide](/PREPARATION.md), which discusses some of the technical components of SCIM bridge deployment and how to avoid potential issues you might encounter along the way.

## Cloud service provider deployments

Solutions for common cloud service platforms:

### Microsoft Azure

- [Azure Container Apps using ARM (Azure Resource Manager) template](https://support.1password.com/scim-deploy-azure/)
- [Azure Container Apps using Cloud Shell](https://support.1password.com/cs/scim-deploy-azure-container-apps/)
- [Azure Kubernetes Service using Cloud Shell](https://support.1password.com/cs/scim-deploy-azure-kubernetes/)


### Amazon Web Services (AWS)

- ✨ **BETA** [Amazon ECS using CloudFormation](/beta/aws-ecsfargate-cfn)
- [Amazon ECS using Terraform](/aws-ecsfargate-terraform)

### Google Cloud (GCP)

- [Cloud Run using Cloud Shell](/beta/google-cloud-run)
- [Google Kubernetes Engine using Google Cloud Marketplace](https://support.1password.com/scim-deploy-gcp/)

### DigitalOcean

- [App Platform using DigitalOcean portal](https://support.1password.com/cs/scim-deploy-digitalocean-ap/)
- [App Platform using DigitalOcean CLI & 1Password CLI](/do-app-platform-op-cli)
- [DigitalOcean Kubernetes using DigitalOcean Marketplace](https://support.1password.com/scim-deploy-digitalocean/)

## Generic cloud deployments

For physical server or virtual machine on-premise or custom cloud deployments:

### Docker

- [Docker Swarm using Docker CLI](/docker)

### Kubernetes

- [Kubernetes using kubectl CLI](/kubernetes)
- [Helm Chart using Helm CLI](https://github.com/1Password/op-scim-helm/tree/main/charts/op-scim-bridge#installation)

## Choosing a deployment method

The choice of deployment method depends on your available or preferred cloud service provider or infrastructure, as well as the platform and tooling that you use or prefer. 

> [!NOTE]
> All deployment examples pull the same public [`1password/scim`](https://hub.docker.com/r/1password/scim) container image from Docker Hub.

Here are some additional details to help you make an informed choice:


### Containers as a Service deployments

Many cloud service providers offer **Containers as a Service** (or **Platform as a Service**) deployment platforms. Compared to other platforms, these solutions offer:

- DNS and TLS certificate management out-of-the-box
- speedier deployment
- lower expected cost and burden of maintenance

These examples are suitable for use in a production environment, include common configuration options, and can be used as a base for your own custom deployment.

We include examples for Azure Container Apps, Google Cloud Run, and DigitalOcean App Platform.

### Marketplace app deployments

For a guided deployment of 1Password SCIM Bridge that connects to your 1Password account to automatically generate and load credentials from 1Password, choose a marketplace app. These are off-the-shelf deployments that may be a suitable choice, but:

- are not customizable
- require creating a public DNS record
- have strict networking requirements

We publish these apps to [DigitalOcean Marketplace](https://marketplace.digitalocean.com/apps/1password-scim-bridge) and [Google Cloud Marketplace](https://console.cloud.google.com/marketplace/product/agilebits-public/op-scim-bridge).

### Beta deployments

Our beta deployment examples represent early efforts to provide a working solution using some new platform or tooling. Each uses the same container image as our stable deployment examples. These deployments _should_ work, but aren't guaranteed and may change in the future.

Learn more about this designation in [`/beta/README.md`](/beta/README.md).

## Deprecated deployment examples

We sometimes deprecate deployment examples that become irrelevant, usually when a new deployment example is released that is a more desirable solution for that cloud service provider or platform.

### Recently deprecated

At the time of deprecation, these deployment examples were fully functional, but will soon become unsupported and removed from the repository:

- _No deployment example have recently been deprecated_

Deprecated deployment examples are moved to the [`/deprecated`](/deprecated) directory. You can learn more about this designation and find suggested alternatives in [`/deprecated/README.md`](/deprecated/README.md).

## Get help

If you encounter issues with your SCIM bridge deployment or have general questions about automated provisioning, [contact 1Password Support](https://support.1password.com/contact/). If you need additional deployment examples or some information in these guides needs improvement, file an issue or open a pull request in this repo to let us know.
