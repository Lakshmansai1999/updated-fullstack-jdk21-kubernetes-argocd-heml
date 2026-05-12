# Spring Boot Backend Helm Chart

## Prerequisites

Before deploying, create the required secret and configmap:

```bash
kubectl create secret generic db-secret \
  --from-literal=DB_PASSWORD='YOUR_PASSWORD'

kubectl create configmap db-config \
  --from-literal=DB_URL='jdbc:postgresql://postgresql-service:5432/fullstackdb' \
  --from-literal=DB_USERNAME='postgres'
```

## Installation

```bash
# Update image repository in values.yaml
helm install springboot-backend ./springboot-backend-helm

# Upgrade
helm upgrade springboot-backend ./springboot-backend-helm

# Uninstall
helm uninstall springboot-backend
```

## Configuration

Edit `values.yaml` to customize:
- Image repository and tag
- Resource limits
- PostgreSQL storage size
- Replica count
