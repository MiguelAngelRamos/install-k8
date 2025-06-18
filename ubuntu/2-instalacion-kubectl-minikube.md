## Pasos para instalar `kubectl` en Ubuntu

### 1. Descargar la última versión estable de `kubectl`:

```sh
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
```

### 2. Hacer el archivo ejecutable:

```bash
chmod +x kubectl
```

### 3. Mover el binario a una ubicación en tu PATH:

```bash
sudo mv kubectl /usr/local/bin/
```

### 4. Verificar la instalación:

```bash
kubectl version --client
```

> Fuente: [Documentación oficial de Kubernetes](https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/)

---

## Pasos para instalar Minikube en Ubuntu

### 1. Descargar la última versión estable de Minikube:

```bash
curl -LO https://github.com/kubernetes/minikube/releases/latest/download/minikube-linux-amd64
```

### 2. Hacer el archivo ejecutable:

```bash
chmod +x minikube-linux-amd64
```

### 3. Mover el binario a una ubicación en tu PATH:

```bash
sudo mv minikube-linux-amd64 /usr/local/bin/minikube
```

### 4. Verificar la instalación:

```bash
minikube version
```

> Fuente: [Documentación oficial de Kubernetes](https://kubernetes.io/docs/tasks/tools/install-minikube/)

---

## Iniciar Minikube

Una vez instalados ambos, puedes iniciar Minikube con:

```bash
minikube start
```

Este comando descargará las imágenes necesarias y configurará un clúster de Kubernetes local.

---

## Verificar el estado del clúster

Para asegurarte de que todo está funcionando correctamente:

```bash
kubectl get nodes
```

Deberías ver un nodo en estado `Ready`.
