## 🟫 ¿Qué es Chocolatey?

Es un **administrador de paquetes para Windows**. Sirve para instalar programas desde la terminal de forma rápida y automatizada. Por ejemplo, instalar `git`, `nodejs`, `googlechrome`, etc., con un simple comando.

---

## ✅ Requisitos antes de instalar

1. **Sistema operativo Windows** (cliente o servidor moderno).
2. **PowerShell v3 o superior**.
3. **.NET Framework 4.8** instalado (si no lo tienes, el instalador intentará instalarlo).
4. Tener **acceso de administrador** (aunque hay un método para instalar sin admin).

---

## 🔐 Seguridad (importante)

El instalador descarga un script remoto (`install.ps1`) desde:

```
https://community.chocolatey.org/install.ps1
```

> 🔎 **Recomendación:** Siempre puedes abrir ese enlace desde el navegador para revisar su contenido antes de ejecutarlo, por seguridad.

---

## ⚠️ Configurar políticas de ejecución en PowerShell

Windows bloquea por defecto la ejecución de scripts por seguridad. Debemos cambiar la política temporalmente para permitirlo.

---

## 🧑‍💻 Instalación paso a paso (como administrador)

### 🥇 Paso 1: Abre PowerShell como Administrador

1. Presiona `Inicio`.
2. Escribe **PowerShell**.
3. Haz clic derecho y selecciona **"Ejecutar como administrador"**.

---

### 🥈 Paso 2: Configura la política de ejecución temporal

Copia y pega esto en PowerShell:

```powershell
Set-ExecutionPolicy Bypass -Scope Process -Force
```

👉 Esto permite ejecutar el script solo durante la sesión actual, sin comprometer la seguridad permanente del sistema.

---

### 🥉 Paso 3: Ejecuta el instalador

Luego, ejecuta este comando completo:

```powershell
[System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
```

Esto:

* Fuerza el uso de TLS 1.2 (necesario para la descarga segura).
* Descarga y ejecuta el instalador de Chocolatey.

---

### ✅ Paso 4: Verifica que se instaló

Una vez finalizado, prueba con este comando:

```powershell
choco -?
```
