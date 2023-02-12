# **HELM** Lab 1
### 1-Add bitnami helm chart repository in the controlplane node.

```bash
helm repo add bitnami https://charts.bitnami.com/bitnami
```
![image info](./Images/1.png)
---

### 2-Deploy the Apache application on the cluster using the apache from the bitnami repository.Set the release Name to: amaze-surf

```bash
helm install amaze-surf bitnami/apache
```
![image info](./Images/2.png)
---

### 3-Uninstall the apache chart release  from the cluster

```bash
helm uninstall amaze-surf
```
![image info](./Images/3.png)
---

### 4- 
#### 1. install specfic version of nginx 1.22.0
```bash
helm search repo  nginx -l | grep 1.22.0
```
![image info](./Images/4.png)
```bash
helm install my-relase-v1 bitnami/nginx --version 12.0.6
```
![image info](./Images/5.png)
#### 2. then update it to specfic 1.23.1 
```bash
helm search repo  nginx -l | grep 1.23.1
```
![image info](./Images/7.png)
```bash
helm upgrade my-relase-v1 bitnami/nginx --version 13.2.10
```
![image info](./Images/6.png)
#### 3.then rollback
```bash
helm history my-relase-v1
```
![image info](./Images/8.png)
```bash
helm rollback my-relase-v1 1  
```
![image info](./Images/9.png)