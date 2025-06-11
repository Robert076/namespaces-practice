# 🌎 namespaces-practice

Namespaces are useful for organizing your cluster. The apps you deploy in your cluster should not have any knowledge about what namespace they are on. Namespaces are only for the cluster administrator. You should be able to redeploy an app from namespace A to namespace B without issues.

A good rule of thumb is to have one namespace per microservice. So every resource used in a certain microservice should go in that namespace.

---

### 🚀 Useful commands:

1. Seeing what namespaces you have in your cluster:
```bash
kubectl get ns
```

2. Creating your first namespacet:
```bash
kubectl create ns custom-ns
```

3. Creating a namespace from a file:
```bash
kubectl apply -f custom-ns-2.yml
```
