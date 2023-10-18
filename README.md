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