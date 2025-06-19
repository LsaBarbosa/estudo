
# Exercícios Práticos Kubernetes - Roadmap Completo
# 📑 Índice de Exercícios Práticos Kubernetes

- [✅ Fase 1: Fundamentos de Kubernetes](#✅-fase-1-fundamentos-de-kubernetes)
    - [Exercício 1: Criar uma Imagem Docker](#exercício-1-criar-uma-imagem-docker)
    - [Exercício 2: Orquestrar com Docker Compose](#exercício-2-orquestrar-com-docker-compose)
    - [Exercício 3: Criar um Pod no Minikube](#exercício-3-criar-um-pod-no-minikube)
    - [Exercício 4: Criar Deployment e Service](#exercício-4-criar-deployment-e-service)

- [✅ Fase 2: Kubernetes na Prática (Intermediário)](#✅-fase-2-kubernetes-na-prática-intermediário)
    - [Exercício 1: ConfigMap](#exercício-1-configmap)
    - [Exercício 2: Secret](#exercício-2-secret)
    - [Exercício 3: EmptyDir Volume](#exercício-3-emptydir-volume)
    - [Exercício 4: PVC](#exercício-4-pvc)
    - [Exercício 5: Health Checks](#exercício-5-health-checks)
    - [Exercício 6: Rolling Update](#exercício-6-rolling-update)
    - [Exercício 7: Escalamento Manual](#exercício-7-escalamento-manual)
    - [Exercício 8: HPA](#exercício-8-hpa)

- [✅ Fase 3: Operação e Monitoramento (Avançado)](#✅-fase-3-operação-e-monitoramento-avançado)
    - [Exercício 1: Namespaces](#exercício-1-namespaces)
    - [Exercício 2: RBAC](#exercício-2-rbac)
    - [Exercício 3: Ingress Controller](#exercício-3-ingress-controller)
    - [Exercício 4: Autoscaler](#exercício-4-autoscaler)
    - [Exercício 5: Prometheus e Grafana](#exercício-5-prometheus-e-grafana)
    - [Exercício 6: Network Policy](#exercício-6-network-policy)

- [✅ Fase 4: Kubernetes em Cloud Providers](#✅-fase-4-kubernetes-em-cloud-providers)
    - [AWS EKS](#aws-eks)
    - [GCP GKE](#gcp-gke)
    - [Azure AKS](#azure-aks)
    - [LoadBalancer Service](#loadbalancer-service)

- [✅ Fase 5: CI/CD com Kubernetes](#✅-fase-5-cicd-com-kubernetes)
    - [GitLab CI Exemplo](#gitlab-ci-exemplo)
    - [GitHub Actions Exemplo](#github-actions-exemplo)
    - [Blue/Green Deployment](#bluegreen-deployment)
    - [Canary Deployment](#canary-deployment)
    - [Argo CD](#argo-cd)
    - [Argo Rollouts](#argo-rollouts)

- [✅ Fase 6: Preparação para Certificação (CKA / CKAD / CKS)](#✅-fase-6-preparação-para-certificação-cka--ckad--cks)
    - [Criar Pods via linha de comando](#criar-pods-via-linha-de-comando)
    - [Troubleshooting](#troubleshooting)
    - [Node Management](#node-management)
    - [Taints e Tolerations](#taints-e-tolerations)
    - [Jobs e CronJobs](#jobs-e-cronjobs)
    - [Network Policies](#network-policies)
    - [RBAC restrito](#rbac-restrito)

---

## ✅ Fase 1: Fundamentos de Kubernetes

### Exercício 1: Criar uma Imagem Docker

```bash
docker build -t minha-app .
docker run -p 8080:8080 minha-app
```

### Exercício 2: Orquestrar com Docker Compose

```yaml
version: '3'
services:
  app:
    image: minha-app
    ports:
      - "8080:8080"
  db:
    image: mysql
    environment:
      MYSQL_ROOT_PASSWORD: root
```

```bash
docker-compose up
```

### Exercício 3: Criar um Pod no Minikube

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: meu-nginx
spec:
  containers:
  - name: nginx
    image: nginx
    ports:
    - containerPort: 80
```

```bash
kubectl apply -f nginx-pod.yaml
```

### Exercício 4: Criar Deployment e Service

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: meu-app
spec:
  replicas: 3
  selector:
    matchLabels:
      app: minha-app
  template:
    metadata:
      labels:
        app: minha-app
    spec:
      containers:
      - name: minha-app
        image: minha-app
        ports:
        - containerPort: 8080
```

```yaml
apiVersion: v1
kind: Service
metadata:
  name: app-service
spec:
  type: NodePort
  selector:
    app: minha-app
  ports:
    - protocol: TCP
      port: 8080
      targetPort: 8080
```

```bash
kubectl apply -f app-deployment.yaml
kubectl apply -f app-service.yaml
minikube service app-service --url
```

---

## ✅ Fase 2: Kubernetes na Prática (Intermediário)

### Exercício 1: ConfigMap

```yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: app-config
data:
  APP_MODE: production
  APP_VERSION: "1.0.0"
```

### Exercício 2: Secret

```bash
kubectl create secret generic db-secret --from-literal=DB_PASSWORD=senha123
```

### Exercício 3: EmptyDir Volume

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: shared-volume-pod
spec:
  volumes:
  - name: shared-data
    emptyDir: {}
  containers:
  - name: writer
    image: busybox
    command: ['sh', '-c', 'echo "Escrevendo no volume" > /data/saida.txt; sleep 3600']
    volumeMounts:
    - name: shared-data
      mountPath: /data
  - name: reader
    image: busybox
    command: ['sh', '-c', 'sleep 5; cat /data/saida.txt; sleep 3600']
    volumeMounts:
    - name: shared-data
      mountPath: /data
```

### Exercício 4: PVC

```yaml
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: meu-pvc
spec:
  accessModes:
    - ReadWriteOnce
  resources:
    requests:
      storage: 1Gi
```

### Exercício 5: Health Checks

```yaml
livenessProbe:
  httpGet:
    path: /health
    port: 8080
  initialDelaySeconds: 15
  periodSeconds: 20

readinessProbe:
  httpGet:
    path: /ready
    port: 8080
  initialDelaySeconds: 5
  periodSeconds: 10
```

### Exercício 6: Rolling Update

```bash
kubectl rollout status deployment meu-app
kubectl rollout undo deployment meu-app
```

### Exercício 7: Escalamento Manual

```bash
kubectl scale deployment meu-app --replicas=5
```

### Exercício 8: HPA

```bash
minikube addons enable metrics-server
kubectl autoscale deployment meu-app --cpu-percent=50 --min=1 --max=10
```

---

## ✅ Fase 3: Operação e Monitoramento (Avançado)

### Exercício 1: Namespaces

```bash
kubectl create namespace dev
kubectl create namespace prod
```

### Exercício 2: RBAC

```yaml
apiVersion: rbac.authorization.k8s.io/v1
kind: Role
metadata:
  namespace: dev
  name: pod-reader
rules:
- apiGroups: [""]
  resources: ["pods"]
  verbs: ["get", "watch", "list"]
```

### Exercício 3: Ingress Controller

```bash
minikube addons enable ingress
```

### Exercício 4: Autoscaler

```bash
kubectl autoscale deployment meu-app --cpu-percent=50 --min=1 --max=5
```

### Exercício 5: Prometheus e Grafana

```bash
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm install prometheus prometheus-community/prometheus

helm repo add grafana https://grafana.github.io/helm-charts
helm install grafana grafana/grafana
kubectl port-forward svc/grafana 3000:80
```

### Exercício 6: Network Policy

```yaml
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
  name: allow-app1
  namespace: default
spec:
  podSelector:
    matchLabels:
      app: app2
  ingress:
  - from:
    - podSelector:
        matchLabels:
          app: app1
    ports:
    - protocol: TCP
      port: 8080
```

---

## ✅ Fase 4: Kubernetes em Cloud Providers

### AWS EKS

```bash
eksctl create cluster --name meu-cluster-eks --region us-east-1 --nodes 2
kubectl get nodes
```

### GCP GKE

```bash
gcloud container clusters create meu-cluster-gke --num-nodes=2 --zone=us-central1-a
gcloud container clusters get-credentials meu-cluster-gke --zone us-central1-a
```

### Azure AKS

```bash
az aks create --resource-group meuGrupo --name meu-cluster-aks --node-count=2 --generate-ssh-keys
az aks get-credentials --resource-group meuGrupo --name meu-cluster-aks
```

### LoadBalancer Service

```yaml
spec:
  type: LoadBalancer
```

---

## ✅ Fase 5: CI/CD com Kubernetes

### GitLab CI Exemplo

```yaml
stages:
  - build
  - deploy

build:
  stage: build
  image: maven:3.8.1-jdk-17
  script:
    - mvn clean package

deploy:
  stage: deploy
  image: bitnami/kubectl
  script:
    - kubectl apply -f k8s/deployment.yaml
    - kubectl apply -f k8s/service.yaml
```

### GitHub Actions Exemplo

```yaml
name: CI/CD
on:
  push:
    branches: [ "main" ]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v2
    - name: Build
      run: mvn clean package

  deploy:
    runs-on: ubuntu-latest
    needs: build
    steps:
    - uses: azure/setup-kubectl@v3
    - run: kubectl apply -f k8s/deployment.yaml
```

### Blue/Green Deployment

- Dois Deployments: `app-blue` e `app-green`  
- Troca manual de Service selector.

### Canary Deployment

- Deploy inicial com 90% versão antiga + 10% nova versão.  
- Gradual incremento.

### Argo CD

```bash
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

### Argo Rollouts

```bash
kubectl apply -f https://github.com/argoproj/argo-rollouts/releases/latest/download/install.yaml
```

---

## ✅ Fase 6: Preparação para Certificação (CKA / CKAD / CKS)

### Criar Pods via linha de comando

```bash
kubectl run nginx --image=nginx --restart=Never --port=80
```

### Troubleshooting

```bash
kubectl describe pod <nome>
kubectl logs <nome>
```

### Node Management

```bash
kubectl cordon <node>
kubectl drain <node> --ignore-daemonsets
kubectl label node <node> ambiente=dev
```

### Taints e Tolerations

```bash
kubectl taint nodes <node> app=web:NoSchedule
```

### Jobs e CronJobs

```bash
kubectl create job meu-job --image=busybox -- /bin/sh -c "echo Hello World"
kubectl create cronjob meu-cron --image=busybox --schedule="*/1 * * * *" -- /bin/sh -c "date"
```

### Network Policies

```yaml
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
  name: restrict-traffic
spec:
  podSelector:
    matchLabels:
      app: app2
  ingress: []
```

### RBAC restrito

```yaml
apiVersion: rbac.authorization.k8s.io/v1
kind: Role
metadata:
  namespace: dev
  name: pod-reader
rules:
- apiGroups: [""]
  resources: ["pods"]
  verbs: ["get", "list"]
```

---

**Fim do arquivo de exercícios! Bons estudos!**
