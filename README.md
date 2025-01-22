Refer to https://github.com/bunkerity/bunkerweb for latest changes.

This is repo to deploy bunkerweb v1.5.12 on a k8s environnement.

In my case, i am using RKE2 as a Kubernetes service.
therefore my dns service is located under kube-system namespace named: 

**rke2-coredns-rke2-coredns**

I am using a basic postgresql instance as backend database, deployed using Cloudnative-pg operator, see: https://github.com/cloudnative-pg/cloudnative-pg

Refer to the official docs to see how you can deploy it (https://cloudnative-pg.io/documentation/1.25/)


# Installation:

Assuming you are running RKE2, you can proceed to the next steps without changing anything

CNPG operator CRDs: Ref (https://cloudnative-pg.io/documentation/1.17/installation_upgrade/)
```
kubectl apply -f https://raw.githubusercontent.com/cloudnative-pg/cloudnative-pg/release-1.17/releases/cnpg-1.17.5.yaml
```
You can verify that with:
```
kubectl get deploy -n cnpg-system cnpg-controller-manager
```

Then run the following command to install all bunkerweb required components:
```
kubectl apply -k .
```

PS: i suppose you're in the current directory where the kustomization.yaml is located.


# Notes:
Make sure to change the username and password of the bunkerweb-ui deployment file.
Make sure to add your static public ip if you want to make it accessible only by you (blacklist entire world).
Make sure to change as well the ingress.yaml by adding your public dns.

