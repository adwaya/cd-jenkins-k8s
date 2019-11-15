# Continuous Delivery with Jenkins in Kubernetes Engine

## Creating a Kubernetes cluster

Now, run the following command to provision a Kubernetes cluster:

```
gcloud container clusters create jenkins-cd \
--num-nodes 2 \
--machine-type n1-standard-2 \
--scopes "https://www.googleapis.com/auth/source.read_write,cloud-platform"
```

Before continuing, confirm that your cluster is running by running the following command:

`gcloud container clusters list`

Now, get the credentials for your cluster:

`gcloud container clusters get-credentials jenkins-cd`

Kubernetes Engine uses these credentials to access your newly provisioned cluster—confirm that you can connect to it by running the following command:

`kubectl cluster-info`

### Install Helm
In this lab, you will use Helm to install Jenkins from the Charts repository. Helm is a package manager that makes it easy to configure and deploy Kubernetes applications. Once you have Jenkins installed, you'll be able to set up your CI/CD pipeline.
