# Kubernetes Party Setup

This repository contains the configuration files for the Kubernetes party. Each team member is responsible for creating their own Pod definition in a single YAML file.

## Repository Structure

- `namespaces/`: Contains YAML files for creating namespaces.
- `nodes/`: Contains YAML files for node taints and labels.
- `pods/`: Each team member has their own YAML file for their Pod.

## How to Contribute

1. Clone this repository.
2. Create a new branch with your code and access it.
3. Create a YAML file under `pods/` with your code (e.g., `2259459.yaml`).
4. Add your Pod definition, tolerations, and node affinity to the file.
5. Push your changes to the branch and start a pull request.

## Applying Configurations

To apply all configurations, run:

kind create cluster --config kind-config.yaml

```
# Add labels
kubectl label node kind-worker style=urbano
kubectl label node kind-worker2 style=metalero
kubectl label node kind-worker3 style=electronico
kubectl label node kind-worker4 style=latino

# Add taints
kubectl taint node kind-worker music=perreo-intenso:NoSchedule
kubectl taint node kind-worker2 music=guitarra-electrica:NoSchedule
kubectl taint node kind-worker3 music=bass-boost:NoSchedule
kubectl taint node kind-worker4 music=sabor-latino:NoSchedule
```

kubectl apply -f namespaces/
kubectl apply -f pods/
