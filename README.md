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

4. Deleting a namespace:
```bash
kubectl delete ns/custom-ns
```

5. Create a resource(eg: configmap) in a certain namespace:
```bash
kubectl create cm configmap-test --from-literal=Lorem=Ipsum -n custom-ns
```

Also, note that you can override the key to the namespaces of the resources that you create declaratively. By adding the -n option to the kubectl create command, you force a namespace as the context for your command: kubectl will take the namespace that was passed in the command into account, not the one present in the YAML file. By doing this, it becomes very easy to duplicate your resources between
different namespaces; for example, a production environment in a production namespace and a test environment in a test namespace. The possibilities are endless!
