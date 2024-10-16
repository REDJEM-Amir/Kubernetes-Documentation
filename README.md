# Kubernetes Documentation

## Helm Commands

| **Command**                 | **Description**                                         | **Usage**                                          |
|-----------------------------|---------------------------------------------------------|----------------------------------------------------|
| `helm install`               | Installs a chart into a Kubernetes cluster              | `helm install <release_name> <chart>`              |
| `helm upgrade`               | Upgrades an existing chart deployment                   | `helm upgrade <release_name> <chart>`              |
| `helm uninstall`             | Uninstalls a deployed chart                             | `helm uninstall <release_name>`                    |
| `helm list`                  | Lists all installed Helm releases                       | `helm list`                                        |
| `helm repo add`              | Adds a Helm chart repository                            | `helm repo add <repo_name> <repo_url>`             |
| `helm repo update`           | Updates your local Helm chart repositories              | `helm repo update`                                 |
| `helm search repo`           | Searches charts in repositories                         | `helm search repo <keyword>`                       |
| `helm show values`           | Displays the default values of a chart                  | `helm show values <chart>`                         |
| `helm rollback`              | Rolls back a release to a previous version              | `helm rollback <release_name> <revision_number>`    |

## Kubectl Commands

| **Command**                 | **Description**                                         | **Usage**                                          |
|-----------------------------|---------------------------------------------------------|----------------------------------------------------|
| `kubectl get`                | Displays resources in a Kubernetes cluster              | `kubectl get <resource_type>`                      |
| `kubectl describe`           | Shows detailed information about a specific resource    | `kubectl describe <resource_type> <resource_name>` |
| `kubectl apply`              | Applies a YAML configuration file to the cluster        | `kubectl apply -f <file.yaml>`                     |
| `kubectl delete`             | Deletes a resource in the cluster                       | `kubectl delete <resource_type> <resource_name>`   |
| `kubectl logs`               | Shows logs from a specific pod                          | `kubectl logs <pod_name>`                          |
| `kubectl exec`               | Executes a command in a container within a pod          | `kubectl exec -it <pod_name> -- <command>`         |
| `kubectl scale`              | Scales a resource to a specified number of replicas     | `kubectl scale <resource_type> --replicas=<number> <resource_name>` |
| `kubectl rollout restart`    | Restarts a deployment                                   | `kubectl rollout restart deployment/<deployment_name>` |
| `kubectl port-forward`       | Forwards a local port to a pod                          | `kubectl port-forward <pod_name> <local_port>:<pod_port>` |
| `kubectl get nodes`          | Lists all nodes in the cluster                          | `kubectl get nodes`                                |
