# **HELM** Lab 1
### 1-Add bitnami helm chart repository in the controlplane node.

```bash
helm repo add bitnami https://charts.bitnami.com/bitnami
```
![home_Page Image](./Images/1.png)
---

### 2-Deploy the Apache application on the cluster using the apache from the bitnami repository.Set the release Name to: amaze-surf

```bash
helm install amaze-surf bitnami/apache
```

---

### 3-Uninstall the apache chart release  from the cluster

```bash
helm uninstall amaze-surf
```

---

### 4- 
#### 1. install specfic version of nginx 1.22.0
```bash
helm search repo  nginx -l | grep 1.22.0
helm install my-relase-v1 bitnami/nginx --version 12.0.6
```
#### 2. then update it to specfic 1.23.1 
```bash
helm search repo  nginx -l | grep 1.23.1
helm upgrade my-relase-v1 bitnami/nginx --version 13.2.10
```
#### 3.then rollback
```bash
helm history my-relase-v1
helm rollback my-relase-v1 1  
```
