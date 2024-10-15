# Kubernetes Documentation

# Installation de Kubernetes

```shell
sudo apt-get install -y apt-transport-https ca-certificates curl gpg

curl -fsSL https://pkgs.k8s.io/core:/stable:/v1.29/deb/Release.key | sudo gpg --dearmor -o /etc/apt/keyrings/kubernetes-apt-keyring.gpg

echo 'deb [signed-by=/etc/apt/keyrings/kubernetes-apt-keyring.gpg] https://pkgs.k8s.io/core:/stable:/v1.29/deb/ /' | sudo tee /etc/apt/sources.list.d/kubernetes.list

sudo apt-get update
sudo apt-get install -y kubelet kubeadm kubectl
sudo apt-mark hold kubelet kubeadm kubectl
```

# Kubernetes / Start / Stop / Logs
| Action                                  | Commande                                                 |
|:----------------------------------------|:---------------------------------------------------------|
| Installation de Kubernetes avec kubeadm | sudo kubeadm init                                        |
| Configurer kubectl pour l'utilisateur   | mkdir -p $HOME/.kube                                     |
|                                         | sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config |
|                                         | sudo chown $(id -u):$(id -g) $HOME/.kube/config          |
| Démarrer Kubernetes                     | sudo systemctl start kubelet                             |
| Arrêter Kubernetes                      | sudo systemctl stop kubelet                              |
| Redémarrer Kubernetes                   | sudo systemctl restart kubelet                           |
| Voir les logs de Kubernetes             | journalctl -xeu kubelet                                  |
| Vérifier le statut du cluster           | kubectl get nodes                                        |

# Installation du client Kubernetes / Start / Stop / Logs
| Action                             | Commande                                                            |
|:-----------------------------------|:--------------------------------------------------------------------|
| Installation de kubectl            | sudo apt-get install -y kubectl                                     |
| Vérifier la version de kubectl     | kubectl version --client                                            |
| Configurer l'accès au cluster      | kubectl config set-cluster <cluster-name> --server=<api-server-url> |
| Démarrer une commande avec kubectl | kubectl <commande>                                                  |
| Arrêter kubectl (arrêt d'un pod)   | kubectl delete pod <pod-name>                                       |
| Voir les logs d'un pod             | kubectl logs <pod-name>                                             |

# Scalabilité & Haute Disponibilité : Auto-scaling, Gestion de Charge et Haute Disponibilité
| Action                                                  | Commande                                                                                                                     |
|:--------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------|
| Auto-scaling d'un déploiement                           | kubectl autoscale deployment <nom-deployment> --min=1 --max=10 --cpu-percent=80                                              |
| Voir les événements de scaling                          | kubectl get hpa                                                                                                              |
| Mettre à jour un déploiement pour ajouter des répliques | kubectl scale --replicas=3 deployment/<nom-deployment>                                                                       |
| Mettre en place un Load Balancer                        | kubectl expose deployment <nom-deployment> --type=LoadBalancer --name=<nom-service>                                          |
| Configurer la haute disponibilité pour un cluster       | Mettre en place plusieurs master nodes et worker nodes avec un load balancer (configuration manuelle selon l'infrastructure) |
