k8s-config

https://refactored.xyz/k3s-traefik-2/

curl -sfL https://get.k3s.io | sh -s - --disable=traefik --write-kubeconfig-mode 644

curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/master/scripts/get-helm-3

# Install helm
chmod 700 get_helm.sh

./get_helm.sh

export KUBECONFIG=/etc/rancher/k3s/k3s.yaml

# Install Traefik2
helm repo add traefik https://helm.traefik.io/traefik

helm repo update

helm install traefik traefik/traefik

# Verify Traefik2 install
kubectl get pods --selector "app.kubernetes.io/name=traefik"

kubectl get svc --selector "app.kubernetes.io/name=traefik"


minotoring:
uptime kuma

file sharing:
https://nextcloud.com/

