# Launch agent chart (no build)
Helm chart/repo for no-build W&B launch agent. In theory should work with any K8s setup but only tested on minikube.

# Minikube setup (macos)

### Step 0: Install `docker` and `brew`

### Step 1: Setup `helm` and `minikube`

```
$ brew install kubernetes-cli helm minikube && minikube start
```

`minikube start` should configure `kubectl` and `helm` to act on your `minikube` cluster by default.

### Step 2: Add helm repo

```
$ helm repo add launch-agent-nobuild https://bcsherma.github.io/launch-agent-chart
```

### Step 3: Install agent 

```
$ helm install agent launch-agent-nobuild/launch-agent --set secret=<your-wandb-api-key>,project=<your-wandb-project>,entity=<your-wandb-entity>
```

Be sure to fill in the `<...>` values above with your api key, project, and entity.
