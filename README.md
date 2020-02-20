## dssh - Keep your authorized\_keys up to date on a Kubernetes cluster.

### Deployment

```
cp dssh.yaml.example dssh.yaml
# edit dssh.yaml to include your public keys in the configmap
kubectl apply -f dssh.yaml
```

### Updating Pubkeys

```
# edit dssh.yaml to update your public keys in the configmap
kubectl apply -f dssh.yaml
```

### Notes

Every 60 seconds your public keys will be applied to all Nodes in the cluster.

You need permission to deploy priviledged pods.

