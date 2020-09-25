## WARNING - You use this at your own peril

Managed Kubernetes providers perform upgrades by deleting and
recreating your VMs. You must not assume that anything you do
on these VMs will persist. In fact, the VM could be deleted
while you are working on it.

## dssh - Keep your authorized\_keys up to date on a Kubernetes cluster.

### Deploying Your Public Keys

```
helm install dssh . --set "keys={ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIMQWiTqUTFVUMASTPpWLd+tYqQD1BW3AKCZfaczsQvP5 user2@hostname,$(cat ~/.ssh/id_rsa.pub)}"
```

### Updating Your Public Keys

```
helm upgrade dssh . --set "keys={ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIMQWiTqUTFVUMASTPpWLd+tYqQD1BW3AKCZfaczsQvP5 user2@hostname,$(cat ~/.ssh/id_rsa.pub)}"
```

### Removing dssh
```
helm delete dssh
```

### Notes

- Every 60 seconds your public keys will be applied to all Nodes in the cluster.
- You need permission to deploy priviledged pods.

