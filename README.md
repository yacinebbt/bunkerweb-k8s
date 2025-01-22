https://github.com/bunkerity/bunkerweb

This is repo to deploy bunkerweb v1.5.12 on a k8s environnement.

In my case, i am using RKE2 as a Kubernetes service.
therefore my dns service is located under kube-system namespace named: **rke2-coredns-rke2-coredns**

i am using a basic postgresql instance as backend database, deployed using Cloudnative-pg operator, see: https://github.com/cloudnative-pg/cloudnative-pg

Refer to the official docs to see how you can deploy it (https://cloudnative-pg.io/documentation/1.25/)