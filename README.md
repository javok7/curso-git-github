# 📘 Comandos básicos de Git y su explicación

## 🏗️ Inicialización y clonación

### `git init`
Inicializa un nuevo repositorio Git en el directorio actual, creando una carpeta `.git`.

### `git clone https://repo`
Clona un repositorio remoto en tu máquina local.

---

## 📂 Seguimiento de archivos

### `git add file.txt`
Agrega el archivo `file.txt` al área de *staging* (preparación para commit).

### `git rm`
Elimina archivos del repositorio y del área de *staging*.

---

## 💬 Commits y mensajes

### `git commit -m "Patch-commit"`
Crea un nuevo commit con el mensaje `"Patch-commit"`.

### `git add -am "Patch-commit"`
Agrega y commitea los archivos modificados en una sola línea (no incluye archivos nuevos no rastreados).

---

## 🔍 Estado y diferencias

### `git status`
Muestra el estado actual del repositorio (archivos modificados, pendientes, etc.).

### `git status -s`
Muestra el estado de forma corta (compacta).

### `git diff --cached`
Muestra los cambios que están en *staging* (listos para commit).

---

## 📜 Historial de commits

### `git log --oneline --graph --reverse`
Muestra el historial en una sola línea por commit, en forma de gráfico, del más antiguo al más nuevo.

### `git log --oneline -4`
Muestra los últimos 4 commits en formato corto.

### `git log --oneline --after="2025-09-1" --before="yesterday"`
Muestra commits entre el 1 de septiembre de 2025 y el día anterior al actual.

### `git log --oneline -S"hola"`
Muestra commits que introdujeron o eliminaron la palabra `"hola"`.

### `git log --stat`
Muestra el historial con estadísticas de líneas agregadas y eliminadas por archivo.

### `git shortlog`
Agrupa los commits por autor (muestra quién modificó qué).

---

## 👀 Inspección de contenido

### `git show commit_id:index.html`
Muestra el contenido del archivo `index.html` en el commit especificado.

### `git show HEAD~1`
Muestra los cambios realizados en el commit anterior al actual.

### `git ls-tree HEAD~1`
Lista los archivos y directorios que existían en el commit anterior.

---

## 🔄 Restauración y limpieza

### `git restore --staged app.py`
Quita `app.py` del área de *staging* (sin borrar los cambios locales).

### `git clean -f`
Elimina archivos no rastreados (que no están en Git).

### `git restore --source=HEAD~1 index.html`
Restaura el archivo `index.html` al estado que tenía en el commit anterior.

---

## ⚙️ Configuración de diferencias

### `git config --global diff.tool vscode`
Define `vscode` como herramienta para comparar diferencias.

### `git config --global difftool.vscode.cmd 'code --wait --diff $LOCAL $REMOTE'`
Configura el comando exacto que usará Git para abrir la comparación en VS Code.

---

## 🚫 Ignorar archivos

### `.gitignore dep/`
Ignora la carpeta `dep/` y su contenido para que Git no los rastree.

---

## 🗑️ Eliminación de staging

### `git rm --cached`
Elimina un archivo del *staging area* sin borrarlo del sistema de archivos.

---

## 🧪 Experimentación y revertir cambios

### `git checkout commit_id`
Cambia el estado del repositorio al commit indicado (modo "detached HEAD").

### `git revert <commit_id>`
Crea un nuevo commit que revierte los cambios del commit especificado.

### `git reset --hard <commit_id>`
Revierte el repositorio por completo al estado del commit indicado (elimina cambios posteriores).

### `git revert HEAD`
Revierte el último commit realizado.

---

## 💾 Stash (guardar trabajo temporal)

### `git stash -am "nombrestash"`
Guarda temporalmente los cambios actuales y los nombra `"nombrestash"`.

### `git stash list`
Lista todos los *stashes* guardados.

### `git stash drop 1`
Elimina el *stash* número 1.

### `git stash apply 1`
Aplica los cambios del *stash* número 1 (sin eliminarlo de la lista).

### `git stash pop`
Aplica el último *stash* y lo elimina de la lista.

---
