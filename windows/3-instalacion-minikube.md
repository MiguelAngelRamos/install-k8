## 🧭 ¿Qué es Minikube?

**Minikube** es una herramienta que te permite ejecutar un clúster de Kubernetes localmente. Está orientada a facilitar el aprendizaje y desarrollo con Kubernetes de manera sencilla.
Con una sola línea (`minikube start`), puedes tener un entorno de Kubernetes funcionando en tu máquina.

---

## 🛠️ Paso 1: Instalación de Minikube en Windows

> 🧱 **Requisito previo**: Tener [Chocolatey](https://chocolatey.org) instalado. Si no lo tienes, te puedo guiar.

Para instalar la última versión estable de Minikube en **Windows x86-64**, ejecuta desde PowerShell como **administrador**:

```powershell
choco install minikube -y
```

---

## 🚀 Paso 2: Iniciar tu clúster de Kubernetes

Desde una terminal **con permisos de administrador** (pero sin estar como usuario `root`), ejecuta:

```bash
minikube start
```

> ⚠️ Si el comando falla, consulta la [documentación de drivers](https://minikube.sigs.k8s.io/docs/drivers/) para asegurarte de tener instalado un entorno compatible (como Docker o VirtualBox).



