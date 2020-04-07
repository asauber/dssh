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

### Notes

- Every 60 seconds your public keys will be applied to all Nodes in the cluster.
- You need permission to deploy priviledged pods.

