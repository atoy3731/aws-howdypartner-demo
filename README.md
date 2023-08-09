# Rancher Government - AWS HowdyPartner Demo

![Howdy Partner - Rancher Government](static/howdypartner-rfed.png
)

These are the Fleet GitOps manifests for Rancher's AWS HowdyPartner demo.

## Automation
### Fleet: GitOps

To demonstrate GitOps using the power of Fleet, check out the [gitops-fleet](automation/gitops-fleet) directory. What is going on:

* Deploys the same demo application across three clusters: dev, staging, prod.
* Each deployment is tracking a different branch (dev, staging, prod) in the same Git repository.
* Using a typical Git flow with merge/pull requests, you can quickly update an application across your environments.
* Fleet empowers you to customize values for your application depending on the environment you are working with.

A little bit more info:

* Since clusters within Rancher/Fleet are just Kubernetes objects, Fleet gives you the ability to target specific clusters for specific applications by using cluster labels. This greatly alleviates some of the traditional pains that go with centralized GitOps, since the "trust" handshake is already taken care of.
* You can also customize specific values for specific clusters with [Target Customizations](https://fleet.rancher.io/gitrepo-targets#customization-per-cluster). This is especially useful if you don't want to maintain multiple `values.yaml` per environments, and just have a subset of values that might change. In this example, we are conditionally utilizing persistent storage for an application.

## Security

### Neuvector: Kubernetes Security

Neuvector is an incredibly powerful tool from Rancher to help you secure your entire Kubernetes footprint. Some highlights as part of the demo include:

* Behavioral learning of traffic into, out of, and within your cluster to determine full telemetry.
* Enforcement of traffic policy based on learned traffic patterns, providing a path to greatly improve your Zero-Trust architecture.
* Simplistic approach to policy enforcement.
* Layer 7 security features such as Web Application Firewall (WAF) and Deep-Level Packet Inspection (DLP).

For more information, check out Neuvector's [page](https://www.suse.com/neuvector/) and [docs](https://open-docs.neuvector.com/).

### Kubewarden: Policy Enforcement

Kubewarden is Rancher's policy enforcement offering, to give developer's full control over what requests get through to the Kubernetes API.

## Carbide

### STIGATRON: STIG Compliance Validation

Automate validating your entire fleet of RKE2 clusters against the DISA-certified STIG. 

### Airgapped Docs: Accessible Docs Anywhere

Access to all Rancher documentation in any environment, with or without internet connectivity.
