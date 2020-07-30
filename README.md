## WARNING - You use this at your own peril

Managed Kubernetes providers perform upgrades by deleting and
recreating your VMs. You must not assume that anything you do
on these VMs will persist. In fact, the VM could be deleted
while you are working on it.

## dssh - Keep your authorized\_keys up to date on a Kubernetes cluster.

### Deploying Your Public Keys

```
cp keys.yaml.example keys.yaml

# Edit keys.yaml to include your public keys

kubectl apply -f daemonset.yaml
kubectl apply -f keys.yaml
```

### Updating Your Public Keys

```
# Edit keys.yaml to update your public keys

kubectl apply -f keys.yaml
```

### Updating dssh

```
kubectl apply -f daemonset.yaml
```

### Removing dssh
```
kubectl delete daemonset -n kube-system root-ssh-manager
```

### Notes

- Every 60 seconds your public keys will be applied to all Nodes in the cluster.
- You need permission to deploy priviledged pods.

