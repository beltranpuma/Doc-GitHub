# 📌 Guía Completa de Comandos Git y GitHub (Español Latinoamericano)

Este documento proporciona una guía detallada sobre los comandos más utilizados en **Git** y **GitHub**, con explicaciones claras y ejemplos adaptados al español latinoamericano.

---

## 🚀 Comandos Básicos de Git

### 🔹 Verificar versión de Git
```bash
git --version
```
Muestra la versión instalada de Git en tu sistema.

### 🔹 Limpiar la terminal
```bash
clear
```
Limpia la pantalla de la terminal.

### 🔹 Inicializar un repositorio
```bash
git init
```
Crea un nuevo repositorio Git en el directorio actual. Genera la carpeta oculta `.git`.

### 🔹 Configurar la rama principal por defecto
```bash
git config --global init.defaultBranch main
```
Establece la rama `main` como la predeterminada al inicializar un repositorio nuevo.

### 🔹 Renombrar la rama actual a `main`
```bash
git branch -m main
```
Si ya iniciaste un repositorio, usa este comando para renombrar la rama principal a `main`.

### 🔹 Ver ayuda de Git
```bash
git --help
```
Muestra una lista de comandos y opciones disponibles en Git.

---

## 🛠️ Configuración de Usuario en Git

### 🔹 Configurar nombre de usuario
```bash
git config --global user.name "Tu Nombre"
```
Reemplaza `"Tu Nombre"` con tu nombre real.

### 🔹 Configurar correo electrónico
```bash
git config --global user.email "tuemail@gmail.com"
```
Reemplaza `"tuemail@gmail.com"` con tu dirección de correo.

### 🔹 Ver configuraciones de Git
```bash
git config --list
```
Muestra todas las configuraciones establecidas en Git.

---

## 📂 Administración de Archivos y Cambios

### 🔹 Ver archivos ocultos en el directorio
```bash
ls -a
```
Muestra todos los archivos, incluyendo `.git`.

### 🔹 Ver el estado del repositorio
```bash
git status
```
Muestra los cambios realizados y su estado.

### 🔹 Agregar archivos al area de staging
```bash
git add nombre_archivo.txt
```
Reemplaza `nombre_archivo.txt` por el nombre del archivo que deseas agregar.

### 🔹 Agregar todos los archivos al staging
```bash
git add .
```
Incluye todos los cambios en el área de staging.

### 🔹 Eliminar un archivo del staging
```bash
git rm --cached nombre_archivo.txt
```
Elimina el archivo del staging, pero lo mantiene en el directorio local.

### 🔹 Crear un commit con mensaje
```bash
git commit -m "Mensaje descriptivo"
```
Guarda los cambios en el repositorio con un mensaje explicativo.

---

## 🔀 Trabajando con Ramas

### 🔹 Ver todas las ramas
```bash
git branch
```
Lista todas las ramas locales.

### 🔹 Crear una nueva rama y cambiar a ella
```bash
git checkout -b nombre_rama
```
Crea una nueva rama llamada `nombre_rama` y la activa.

### 🔹 Cambiar a una rama existente
```bash
git checkout main
```
O también:
```bash
git switch main
```

### 🔹 Eliminar una rama
```bash
git branch -D nombre_rama
```
Elimina la rama especificada.

---

## 🔄 Deshacer Cambios

### 🔹 Revertir un commit sin eliminar historial
```bash
git revert HASH_DEL_COMMIT
```
Genera un nuevo commit que deshace los cambios del commit especificado.

### 🔹 Resetear un commit (varias opciones)
```bash
git reset --soft HASH_DEL_COMMIT
```
Mantiene los cambios en staging.
```bash
git reset --mixed HASH_DEL_COMMIT
```
Quita los cambios del staging pero los mantiene en el directorio de trabajo.
```bash
git reset --hard HASH_DEL_COMMIT
```
Elimina por completo los cambios (no recuperables). **Usar con precaución**.

---

## 🌍 Trabajando con GitHub

### 🔹 Clonar un repositorio remoto
```bash
git clone https://github.com/usuario/repositorio.git
```
Descarga el repositorio a tu equipo.

### 🔹 Subir cambios a GitHub
```bash
git push origin main
```
Envía los commits locales al repositorio remoto.

---

## 🔑 Configuración de Claves SSH en GitHub

1️⃣ **Generar una clave SSH**
```bash
ssh-keygen -t ed25519 -C "tuemail@gmail.com"
```

2️⃣ **Agregar clave al agente SSH**
```bash
ssh-add ~/.ssh/id_ed25519
```

3️⃣ **Copiar clave pública y agregarla en GitHub**
```bash
cat ~/.ssh/id_ed25519.pub
```

4️⃣ **Probar conexión con GitHub**
```bash
ssh -T git@github.com
```

---

## 📝 Conceptos Clave de GitHub

### 🔹 **Fork** 🏗️
Un fork es una copia de un repositorio en GitHub. Permite hacer cambios sin afectar el original.

### 🔹 **Pull Request (PR)** 🔄
Solicita la fusión de cambios de una rama a otra. Es esencial en trabajo colaborativo.

### 🔹 **GitHub Actions** ⚙️
Automatiza flujos de trabajo, como pruebas y despliegues automáticos.

---

## 🎯 Conclusión
Con esta guía, puedes gestionar tus proyectos con Git y GitHub de manera eficiente. ¡Practica y domina estas herramientas esenciales para el desarrollo moderno! 🚀

