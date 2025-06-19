
# Roadmap Completo de Estudos Kubernetes (DevOps)
# 📑 Índice - Roadmap Completo de Estudos Kubernetes (DevOps)

- [📍 Fase 1: Fundamentos](#📍-fase-1-fundamentos)
    - [1. Conceitos de Containers](#1-conceitos-de-containers)
        - [O que é um Container?](#o-que-é-um-container)
        - [Diferença entre Containers e VMs](#diferença-entre-containers-e-vms)
        - [Imagens Docker](#imagens-docker)
        - [Dockerfile](#dockerfile)
        - [Docker Compose](#docker-compose)
    - [2. Orquestração de Containers](#2-orquestração-de-containers)
        - [O que é um Orquestrador?](#o-que-é-um-orquestrador)
        - [Por que usar Kubernetes?](#por-que-usar-kubernetes)
    - [3. Arquitetura do Kubernetes](#3-arquitetura-do-kubernetes)
        - [Cluster](#cluster)
        - [Node (Master/Worker)](#node-masterworker)
        - [Pods](#pods)
        - [ReplicaSets](#replicasets)
        - [Deployments](#deployments)
        - [Services](#services)

- [📍 Fase 2: Kubernetes na Prática (Intermediário)](#📍-fase-2-kubernetes-na-prática-intermediário)
    - [1. ConfigMaps e Secrets](#1-configmaps-e-secrets)
    - [2. Volumes e Persistência](#2-volumes-e-persistência)
    - [3. Health Checks](#3-health-checks)
    - [4. Rolling Updates e Rollbacks](#4-rolling-updates-e-rollbacks)
    - [5. Escalabilidade](#5-escalabilidade)

- [📍 Fase 3: Operação e Monitoramento (Avançado)](#📍-fase-3-operação-e-monitoramento-avançado)
    - [1. Namespaces e RBAC](#1-namespaces-e-rbac)
    - [2. Ingress Controller](#2-ingress-controller)
    - [3. Autoscaling Avançado](#3-autoscaling-avançado)
    - [4. Monitoramento](#4-monitoramento)
    - [5. Logging](#5-logging)
    - [6. Network Policies](#6-network-policies)

- [📍 Fase 4: Kubernetes em Cloud Providers](#📍-fase-4-kubernetes-em-cloud-providers)
    - [1. AWS EKS](#1-aws-eks)
    - [2. GCP GKE](#2-gcp-gke)
    - [3. Azure AKS](#3-azure-aks)
    - [4. Deploy com LoadBalancer](#4-deploy-com-loadbalancer)
    - [5. Monitoramento via Cloud Provider](#5-monitoramento-via-cloud-provider)
    - [6. Storage Classes (EBS, GCE PD, Azure Disk)](#6-storage-classes-ebs-gce-pd-azure-disk)
    - [7. Ingress Controller em Cloud](#7-ingress-controller-em-cloud)

- [📍 Fase 5: CI/CD com Kubernetes](#📍-fase-5-cicd-com-kubernetes)
    - [1. CI/CD com GitLab CI ou GitHub Actions](#1-cicd-com-gitlab-ci-ou-github-actions)
    - [2. Blue/Green Deployment](#2-bluegreen-deployment)
    - [3. Canary Deployment](#3-canary-deployment)
    - [4. GitOps com Argo CD](#4-gitops-com-argo-cd)
    - [5. Rollouts com Argo Rollouts](#5-rollouts-com-argo-rollouts)
    - [6. Pipeline CI → Deploy → Monitoramento](#6-pipeline-ci-→-deploy-→-monitoramento)

- [📍 Fase 6: Preparação para Certificações (CKA / CKAD / CKS)](#📍-fase-6-preparação-para-certificações-cka--ckad--cks)
    - [1. Ambiente de Simulação (Killer.sh, KodeKloud)](#1-ambiente-de-simulação-killersh-kodekloud)
    - [2. Administração de Cluster (CKA)](#2-administração-de-cluster-cka)
    - [3. Desenvolvimento de Aplicações (CKAD)](#3-desenvolvimento-de-aplicações-ckad)
    - [4. Segurança de Cluster (CKS)](#4-segurança-de-cluster-cks)
    - [5. Troubleshooting](#5-troubleshooting)
    - [6. Taints, Tolerations, Network Policies](#6-taints-tolerations-network-policies)
    - [7. RBAC avançado](#7-rbac-avançado)
    - [8. Rollbacks e Health Checking](#8-rollbacks-e-health-checking)
    - [9. Execução cronometrada de tarefas](#9-execução-cronometrada-de-tarefas)

## 📍 Fase 1: Fundamentos

### 1. Conceitos de Containers
- O que é um Container?
- Diferença entre Containers e VMs
- Imagens Docker
- Dockerfile
- Docker Compose

### 2. Orquestração de Containers
- O que é um Orquestrador?
- Por que usar Kubernetes?

### 3. Arquitetura do Kubernetes
- Cluster
- Node (Master/Worker)
- Pods
- ReplicaSets
- Deployments
- Services

---

## 📍 Fase 2: Kubernetes na Prática (Intermediário)

### 1. ConfigMaps e Secrets
- Criar ConfigMaps
- Criar Secrets
- Usar em Deployments

### 2. Volumes e Persistência
- EmptyDir
- PersistentVolume e PVC

### 3. Health Checks
- Liveness Probe
- Readiness Probe

### 4. Rolling Updates e Rollbacks

### 5. Escalabilidade
- Escalamento manual
- Horizontal Pod Autoscaler (HPA)

---

## 📍 Fase 3: Operação e Monitoramento (Avançado)

### 1. Namespaces e RBAC
- Criar Namespaces
- Criar Roles e RoleBindings

### 2. Ingress Controller
- NGINX Ingress Controller

### 3. Autoscaling Avançado
- Cluster Autoscaler

### 4. Monitoramento
- Prometheus
- Grafana

### 5. Logging
- EFK Stack (Elasticsearch, Fluentd, Kibana)

### 6. Network Policies

---

## 📍 Fase 4: Kubernetes em Cloud Providers

### 1. AWS EKS
### 2. GCP GKE
### 3. Azure AKS
### 4. Deploy com LoadBalancer
### 5. Monitoramento via Cloud Provider
### 6. Storage Classes (EBS, GCE PD, Azure Disk)
### 7. Ingress Controller em Cloud

---

## 📍 Fase 5: CI/CD com Kubernetes

### 1. CI/CD com GitLab CI ou GitHub Actions
### 2. Blue/Green Deployment
### 3. Canary Deployment
### 4. GitOps com Argo CD
### 5. Rollouts com Argo Rollouts
### 6. Pipeline CI → Deploy → Monitoramento

---

## 📍 Fase 6: Preparação para Certificações (CKA / CKAD / CKS)

### 1. Ambiente de Simulação (Killer.sh, KodeKloud)
### 2. Administração de Cluster (CKA)
### 3. Desenvolvimento de Aplicações (CKAD)
### 4. Segurança de Cluster (CKS)
### 5. Troubleshooting
### 6. Taints, Tolerations, Network Policies
### 7. RBAC avançado
### 8. Rollbacks e Health Checking
### 9. Execução cronometrada de tarefas

---

**Bons estudos e boa jornada DevOps com Kubernetes!**
