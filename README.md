# www.camel-k.com



## k83 [K3s](https://k3s.io/)

```
curl -sfL https://get.k3s.io | sh - 
```

Check for Ready node, takes ~30 seconds 
```
sudo k3s kubectl get node 
```
sudo k3s server &
Kubeconfig is written to /etc/rancher/k3s/k3s.yaml
```
sudo k3s kubectl get node
```
On a different node run the below command. 
NODE_TOKEN comes from /var/lib/rancher/k3s/server/node-token on your server
```
sudo k3s agent --server https://myserver:6443 --token ${NODE_TOKEN}
```

## [Installing Camel K on K3s :: Apache Camel](https://camel.apache.org/camel-k/1.12.x/installation/registry/k3s.html)

> kubectl -n camel-k-test create secret generic my-registry-secret --from-file=$HOME/.docker/config.json
Installing Camel K on K3s

```shell
kubectl create namespace camel-k-test || true
```
kubectl -n camel-k-test create secret generic my-registry-secret --from-file=$HOME/.docker/config.json




## Install Camel-K

See the Apache Camel K installation page for details: (https://camel.apache.org/camel-k/next/installation/installation.html).


Install Kustomize by downloading precompiled binaries.
```shell
curl -s "https://raw.githubusercontent.com/kubernetes-sigs/kustomize/master/hack/install_kustomize.sh"  | bash
```

if you’re using Linux, you can put kamel in /usr/bin
```shell
cp kamel /usr/bin .
```

# Clone the project repository
```shell
dnf install -y git
git clone https://github.com/apache/camel-k.git
cd camel-k
```

# You can use any release branch or skip this step to use it the last code on `main`
```shell
git checkout release-a.b.x
```

```
cd install
kubectl apply -k setup-cluster
kubectl apply -k setup
kubectl apply -k operator
kubectl apply -k platform
```

## install docker


install docker
```
dnf install -y docker
```

config docker
```
sudo groupadd docker
sudo usermod -aG docker $USER
reboot
```

activate the changes to groups:
```
newgrp docker
```

run docker commands without sudo.
```
docker run hello-world
```

if permission denied
```
sudo chown "$USER":"$USER" /home/"$USER"/.docker -R
sudo chmod g+rwx "$HOME/.docker" -R
```


Configure Docker to start on boot with systemd
```
sudo systemctl enable docker.service
sudo systemctl enable containerd.service
```


## Install minikube

+ [minikube start - minikube](https://minikube.sigs.k8s.io/docs/start/)



```
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube
```

```shell
minikube start
minikube addons enable registry
minikube start --addons registry
```


```
kamel install
```


If you already have kubectl installed, you can now use it to access your shiny new cluster:
```
kubectl get po -A
```

Alternatively, minikube can download the appropriate version of kubectl and you should be able to use it like this:
```
minikube kubectl -- get po -A
```


You can also make your life easier by adding the following to your shell config:
```
alias kubectl="minikube kubectl --"
```

Initially, some services such as the storage-provisioner, may not yet be in a Running state. This is a normal condition during cluster bring-up, and will resolve itself momentarily. For additional insight into your cluster state, minikube bundles the Kubernetes Dashboard, allowing you to get easily acclimated to your new environment:

```
minikube dashboard
```



Create a sample deployment and expose it on port 8080:
```
kubectl create deployment hello-minikube --image=kicbase/echo-server:1.0
kubectl expose deployment hello-minikube --type=NodePort --port=8080
```

It may take a moment, but your deployment will soon show up when you run:
```
kubectl get services hello-minikube
```

The easiest way to access this service is to let minikube launch a web browser for you:

```
minikube service hello-minikube
```

Alternatively, use kubectl to forward the port:

```
kubectl port-forward service/hello-minikube 7080:8080
```

application is now available at http://localhost:7080/.







### Install Karavan
```shell
kubectl apply -k karavan -n default
```

### Open Karavan

Get Karavan URL
```shell
minikube service karavan --url
```

Result should be like
```shell
Tunnel for service camel-karavan:
|-----------|---------------|-------------|------------------------|
| NAMESPACE |     NAME      | TARGET PORT |          URL           |
|-----------|---------------|-------------|------------------------|
| default   | camel-karavan |             | http://127.0.0.1:60708 |
|-----------|---------------|-------------|------------------------|
```
Open url `http://127.0.0.1:60708` in browser



## Security

[4ndersonLin/awesome-cloud-security: 🛡️ Awesome Cloud Security Resources ⚔️](https://github.com/4ndersonLin/awesome-cloud-security)

> # [](https://github.com/4ndersonLin/awesome-cloud-security#contents)Contents
> 
> -   [Standards](https://github.com/4ndersonLin/awesome-cloud-security#standards)
> -   [Tools](https://github.com/4ndersonLin/awesome-cloud-security#tools)
> -   [Reading materials](https://github.com/4ndersonLin/awesome-cloud-security#reading-materials)
> -   [Resource](https://github.com/4ndersonLin/awesome-cloud-security#resource)
> -   [Contributing](https://github.com/4ndersonLin/awesome-cloud-security#contributing)
> 
> # Standards
> 
> -   [Compliances](https://github.com/4ndersonLin/awesome-cloud-security#compliances)
> -   [Benchmarks](https://github.com/4ndersonLin/awesome-cloud-security#benchmarks)
> 
> ## Compliances
> 
> -   [CSA STAR](https://cloudsecurityalliance.org/star/)
> -   [ISO/IEC 27017:2015](https://www.iso.org/standard/43757.html)
> -   [ISO/IEC 27018:2019](https://www.iso.org/standard/76559.html)
> -   [MTCS SS 584](https://www.imda.gov.sg/regulations-and-licensing-listing/ict-standards-and-quality-of-service/IT-Standards-and-Frameworks/ComplianceAndCertification)
> 
> ## Benchmarks
> 
> -   [CIS Benchmark](https://www.cisecurity.org/cis-benchmarks/)
> 
> # Tools
> 
> -   [Infrastrcture](https://github.com/4ndersonLin/awesome-cloud-security#infrastrcture)
> -   [Container](https://github.com/4ndersonLin/awesome-cloud-security#container)
> -   [SaaS](https://github.com/4ndersonLin/awesome-cloud-security#saas)
> -   [Penetration testing/leaerning](https://github.com/4ndersonLin/awesome-cloud-security#penetration-testingleaerning)
> -   [Native tools](https://github.com/4ndersonLin/awesome-cloud-security#nativetools)
