## 🧰 Instalar `kubectl` en Windows usando Chocolatey, Scoop o Winget

Puedes instalar `kubectl` fácilmente usando uno de estos tres gestores de paquetes:

* **Chocolatey**
* **Scoop**
* **Winget**

---

### 🔹 Instalación con Chocolatey (recomendado para PowerShell)

Ejecuta este comando en PowerShell como administrador:

```powershell
choco install kubernetes-cli -y
```

---

### 🔹 Verificar la instalación

Asegúrate de que `kubectl` esté correctamente instalado:

```powershell
kubectl version --client
```

Esto debería mostrar la versión del cliente `kubectl` instalado.

---

### 📁 Configurar el acceso al clúster Kubernetes

---

### 🔸 1. Ir al directorio personal del usuario

* Si usas **CMD**:

```cmd
cd %USERPROFILE%
```

* Si usas **PowerShell**:

```powershell
cd ~
```

---

### 🔸 2. Crear la carpeta `.kube`

```powershell
mkdir .kube
cd .kube
```

---

### 🔸 3. Crear un archivo de configuración vacío (simulando `kubeconfig`)

```powershell
New-Item config -type file
```

> Puedes editar este archivo con **Notepad**, **VS Code** u otro editor para agregar la configuración de acceso al clúster (si la tienes).

---

## 🧪 Verificar la configuración de `kubectl`

`kubectl` necesita un archivo de configuración llamado `config` (también llamado **kubeconfig**) ubicado por defecto en:

```
C:\Users\<tu_usuario>\.kube\config
```

Este archivo se **crea automáticamente** si:

* Usas `minikube start`
* Usas scripts como `kube-up.sh`
* Te conectas a un clúster remoto

---

### Verificar si `kubectl` puede acceder al clúster:

```powershell
kubectl cluster-info
```

* ✅ Si ves una respuesta con URLs, entonces está bien configurado.
* ❌ Si ves algo como:

```
The connection to the server <servidor:puerto> was refused...
```

significa que `kubectl` no puede conectar con el clúster.

> En ese caso, asegúrate de que el clúster esté corriendo (por ejemplo, usando **Minikube**) y vuelve a ejecutar el comando.

---

### Si `cluster-info` da URLs pero no puedes acceder, prueba con:

```powershell
kubectl cluster-info dump
```

Esto te mostrará más detalles para depurar la conexión.

---
