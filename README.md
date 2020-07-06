# MetalLB-with-k8s-bare-metal
# Install Metallb:  
kubectl apply -f https://raw.githubusercontent.com/metallb/metallb/v0.9.3/manifests/namespace.yaml  
kubectl apply -f https://raw.githubusercontent.com/metallb/metallb/v0.9.3/manifests/metallb.yaml  
# On first install only  
kubectl create secret generic -n metallb-system memberlist --from-literal=secretkey="$(openssl rand -base64 128)"  
# Install Nginx-Ingress  
- Install Helm:  
$ curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/master/scripts/get-helm-3  
$ chmod 700 get_helm.sh  
$ ./get_helm.sh  
- Install Nginx-Ingress  
$ helm repo add nginx-stable https://helm.nginx.com/stable  
$ helm repo update  
$ helm install my-release nginx-stable/nginx-ingress  
