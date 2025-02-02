# Comandos de Git y GitHub Explicados Detalladamente

Este README proporciona una guía completa de los comandos más comunes de Git y GitHub, con explicaciones detalladas y ejemplos en español latinoamericano.

## Comandos Básicos de Git

*   **`git --version`**: Muestra la versión instalada de Git.

    ```bash
    git --version
    ```

*   **`clear`**: Limpia la terminal.

    ```bash
    clear
    ```

*   **`git init`**: Inicializa un nuevo repositorio Git en el directorio actual.

    ```bash
    git init
    ```

*   **`git config --global init.defaultBranch main`**: Establece la rama predeterminada para los nuevos repositorios como `main`. Esta es una buena práctica para los flujos de trabajo modernos de Git.
``
    ```bash
    git config --global init.defaultBranch main
    ```

*   **`git branch -m main`**: Renombra la rama actual a `main`. Esto se usa a menudo después de `git init` para nombrar explícitamente la rama inicial.

    ```bash
    git branch -m main
    ```

*   **`git --help`**: Muestra una lista de los comandos y opciones disponibles de Git.

    ```bash
    git --help
    ```

*   **`git config --global user.name "Beltran Puma"`**: Establece tu nombre de usuario global para los commits de Git. **Importante:** Reemplaza `"Beltran Puma"` con tu nombre real.

    ```bash
    git config --global user.name "Beltran Puma"
    ```

*   **`git config --global user.email "bpumacc@gmail.com"`**: Establece tu dirección de correo electrónico global para los commits de Git. **Importante:** Reemplaza `"bpumacc@gmail.com"` con tu correo electrónico real.

    ```bash
    git config --global user.email "bpumacc@gmail.com"
    ```

*   **`git config --list`**: Lista todas tus configuraciones de Git.

    ```bash
    git config --list
    ```

*   **`ls -a`**: Lista todos los archivos y directorios en el directorio actual, incluyendo los archivos ocultos (los que comienzan con un punto). Esto puede ser útil para ver si el directorio `.git` (creado por `git init`) está presente.

    ```bash
    ls -a
    ```

*   **`git status`**: Muestra el estado de tu directorio de trabajo, incluyendo los cambios que se han realizado pero aún no se han agregado al área de staging.

    ```bash
    git status
    ```

*   **`git add Testing.txt`**: Agrega el archivo `Testing.txt` al área de staging, preparándolo para el próximo commit.

    ```bash
    git add Testing.txt
    ```

*   **`git rm --cached Testing.txt`**: Elimina `Testing.txt` del área de staging, pero mantiene el archivo en tu directorio de trabajo. Esto es útil si agregaste accidentalmente un archivo que no querías commitear.

    ```bash
    git rm --cached Testing.txt
    ```

*   **`git add .`**: Agrega todos los cambios en el directorio actual y sus subdirectorios al área de staging.

    ```bash
    git add .
    ```

*   **`git commit -m "Dos archivos de Testing"`**: Crea un nuevo commit con los cambios en staging y el mensaje de commit proporcionado. El mensaje debe ser corto y descriptivo.

    ```bash
    git commit -m "Dos archivos de Testing"
    ```

*   **`git log`**: Muestra el historial de commits.

    ```bash
    git log
    ```

*   **`git branch`**: Lista todas las ramas locales.

    ```bash
    git branch
    ```

*   **`git checkout -b thiago`**: Crea una nueva rama llamada `thiago` y se cambia a ella.

    ```bash
    git checkout -b thiago
    ```

*   **`git checkout main` o `git switch main`**: Se cambia a la rama `main`. `git switch` es el comando más nuevo y preferido, pero `git checkout` todavía se usa ampliamente.

    ```bash
    git checkout main
    git switch main
    ```

*   **`git branch -D thiago`**: Elimina la rama `thiago`. ¡Usar con precaución!

    ```bash
    git branch -D thiago
    ```

*   **`git revert dd4cec8530bb29b50d93ee257063dbd228739d5d`**: Crea un nuevo commit que revierte los cambios introducidos por el hash de commit especificado. Esto preserva el historial agregando un nuevo commit en lugar de reescribir el historial.

    ```bash
    git revert dd4cec8530bb29b50d93ee257063dbd228739d5d
    ```

*   **`git reset --soft`**: Mueve el puntero de la rama al commit especificado, pero mantiene los cambios en el área de staging.

*   **`git reset --mixed`**: Mueve el puntero de la rama al commit especificado y elimina los cambios del área de staging. Este es el comportamiento predeterminado de `git reset`.

*   **`git reset --hard dd4cec8530bb29b50d93ee257063dbd228739d5d`**: Mueve el puntero de la rama al commit especificado y descarta todos los cambios en el directorio de trabajo y el área de staging. **Usar con extrema precaución ya que esta es una operación destructiva.**

    ```bash
    git reset --hard dd4cec8530bb29b50d93ee257063dbd228739d5d
    ```

*   **`git clone https://github.com/beltranpuma/miPrimerRepo.git`**: Clona un repositorio desde GitHub (u otro servicio de alojamiento de Git) a tu máquina local.

    ```bash
    git clone [https://github.com/beltranpuma/miPrimerRepo.git](https://github.com/beltranpuma/miPrimerRepo.git)
    ```

## Configuración de Claves SSH en GitHub

Estos pasos son para configurar claves SSH para evitar tener que ingresar tu contraseña cada vez que interactúas con GitHub.

1.  **`ssh-keygen -t ed25519 -C "bpumacc@gmail.com"`**: Genera un nuevo par de claves SSH. Reemplaza `"bpumacc@gmail.com"` con tu dirección de correo electrónico.

    ```bash
    ssh-keygen -t ed25519 -C "bpumacc@gmail.com"
    ```

2.  **`cd .ssh`**: Navega al directorio `.ssh` donde se almacenan las claves.

    ```bash
    cd .ssh
    ```

3.  **`eval "$(ssh-agent -s)"`**: Inicia el agente SSH.

    ```bash
    eval "$(ssh-agent -s)"
    ```

4.  **`ssh-add ~/.ssh/id_ed25519`**: Agrega tu clave privada al agente SSH.

    ```bash
    ssh-add ~/.ssh/id_ed25519
    ```

5.  **`cat ~/.ssh/id_ed25519.pub`**: Muestra el contenido de tu clave pública. Copia esta clave.

    ```bash
    cat ~/.ssh/id_ed25519.pub
    ```

6.  **Agrega la clave pública a la configuración de tu cuenta de GitHub:** Ve a la configuración de tu GitHub, luego "Claves SSH y GPG", y agrega una nueva clave SSH. Pega la clave pública copiada.

7.  **`ssh -T git@github.com`**: Prueba la conexión SSH a GitHub.

    ```bash
    ssh -T git@github.com
    ```

## Conceptos de GitHub

*   **Fork**: Un fork es una copia de un repositorio en GitHub. Forkear te permite realizar cambios en el proyecto de otra persona sin afectar directamente al repositorio original. Luego puedes enviar una solicitud de extracción (pull request) al propietario del repositorio original para fusionar tus cambios.

*   **Pull Request (PR) (Solicitud de extracción)**: Una solicitud de extracción es una solicitud para fusionar cambios de una rama a otra. Es la forma en que propones cambios a un repositorio forkeado u otra rama dentro del mismo repositorio. Las revisiones de código se realizan en las solicitudes de extracción.

*   **Trello en GitHub**:  Trello no está directamente integrado en GitHub. Trello es una herramienta de gestión de proyectos independiente que se puede usar para organizar tareas y flujos de trabajo relacionados con proyectos de software alojados en GitHub. Puedes vincular tarjetas de Trello a problemas o solicitudes de extracción en GitHub para realizar un seguimiento del progreso.

*   **`git push`**:
