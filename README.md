# jenkins-operator

Infraestructure As Code (IAC) for the Jenkins Operator and Jenkins

## Deploy Jenkins Operator using Helm Chart

```bash
helm repo add jenkins https://raw.githubusercontent.com/jenkinsci/kubernetes-operator/master/chart
```

TODO: Editar values.yaml para que se ciña a los archivos que he creado

```bash
helm install <name> jenkins/jenkins-operator -n <your-namespace> --values values.yaml
```

## Deploy Jenkins to Kubernetes

```bash
kubectl create -f jenkins_instance.yaml
```

Get Jenkins credentials:

```bash
kubectl get secret jenkins-operator-credentials-<cr_name> -o 'jsonpath={.data.user}' | base64 -d
kubectl get secret jenkins-operator-credentials-<cr_name> -o 'jsonpath={.data.password}' | base64 -d
```

Connect to the Jenkins instance (minikube):

```bash
minikube service jenkins-operator-http-<cr_name> --url
```

Connect to the Jenkins instance (actual Kubernetes cluster):

```bash
kubectl port-forward jenkins-<cr_name> 8080:8080
```

Then open browser with address `http://localhost:8080`.