# Rancher Government - AWS HowdyPartner Demo

![Howdy Partner - Rancher Government](static/howdypartner-rfed.png
)

These are the Fleet GitOps manifests for Rancher's AWS HowdyPartner demo.

## Gitops With Fleet

To demonstrate GitOps using the power of Fleet, check out the [gitops-fleet](gitops-fleet) directory. What is going on:

* Deploys the same demo application across three clusters: dev, staging, prod.
* Each deployment is tracking a different branch (dev, staging, prod) in the same Git repository.
* Using a typical Git flow with merge/pull requests, you can quickly update an application across your environments.
* Fleet empowers you to customize values for your application depending on the environment you are working with.

A little bit more info:

* Since clusters within Rancher/Fleet are just Kubernetes objects, Fleet gives you the ability to target specific clusters for specific applications by using cluster labels. This greatly alleviates some of the traditional pains that go with centralized GitOps, since the "trust" handshake is already taken care of.
* You can also customize specific values for specific clusters with [Target Customizations](https://fleet.rancher.io/gitrepo-targets#customization-per-cluster). This is especially useful if you don't want to maintain multiple `values.yaml` per environments, and just have a subset of values that might change. In this example, we are conditionally utilizing persistent storage for an application.

## Kubernetes Security with Neuvector

Neuvector is an incredibly powerful tool from Rancher to help you secure your entire Kubernetes 