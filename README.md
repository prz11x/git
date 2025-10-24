# git

🧭 GUÍA COMPLETA DE GIT Y GITHUB
🧩 1. ¿Qué es Git?

Git es un sistema de control de versiones distribuido.
Sirve para guardar los cambios de tu código, volver atrás, colaborar con otros y mantener un historial completo de tu proyecto.

🌐 2. ¿Qué es GitHub?

GitHub es una plataforma en la nube donde se alojan repositorios Git.
Permite colaborar, revisar código, crear issues y desplegar proyectos.

⚙️ 3. Instalación y configuración inicial
🔧 Instalar Git

Windows: descarga desde git-scm.com/downloads

Linux (Ubuntu):

sudo apt update
sudo apt install git

⚙️ Configurar tu identidad (una sola vez)
git config --global user.name "TuNombre"
git config --global user.email "tuemail@ejemplo.com"


Verifica:

git config --list

📁 4. Crear o clonar un repositorio
🆕 Crear uno nuevo desde cero
git init


Esto crea una carpeta oculta .git con todo el historial.

🔁 Clonar un repositorio existente
git clone https://github.com/usuario/repositorio.git

📄 5. Ciclo básico de trabajo en Git
Fase	Descripción	Comando
1. Modificar archivos	Editas el código	—
2. Añadir al área de preparación (staging)	Git los prepara para el commit	git add nombre_archivo o git add .
3. Confirmar cambios (commit)	Guarda los cambios con un mensaje	git commit -m "Mensaje descriptivo"
4. Subir al repositorio remoto	Envía tus commits a GitHub	git push origin main
🧱 6. Comandos esenciales
🔍 Estado actual
git status

📜 Ver historial de commits
git log


O más compacto:

git log --oneline --graph --decorate --all

🔄 Ver diferencias entre versiones
git diff

🧹 Eliminar archivos del control de Git
git rm nombre_archivo

✏️ Cambiar el mensaje del último commit
git commit --amend -m "Nuevo mensaje"

🌿 7. Ramas (branches)

Las ramas permiten trabajar en funciones o correcciones sin alterar la principal.

Crear una rama nueva
git branch nombre_rama

Cambiar de rama
git checkout nombre_rama


(En versiones modernas puedes usar:)

git switch nombre_rama

Crear y cambiar en una sola línea
git checkout -b nombre_rama

Ver ramas existentes
git branch

Fusionar una rama con otra (merge)

Primero cambia a la rama principal:

git checkout main
git merge nombre_rama

Eliminar una rama
git branch -d nombre_rama

🚧 8. Resolver conflictos

Cuando dos ramas modifican la misma línea de un archivo, Git muestra un conflicto.
Debes abrir el archivo y dejar la versión correcta, luego:

git add archivo_conflictivo
git commit

☁️ 9. Conectar con GitHub
Crear repositorio en GitHub

Ve a github.com/new

Asigna nombre, descripción y elige público o privado.

NO marques "Initialize with README" si ya tienes un proyecto local.

Enlazar tu repositorio local con GitHub
git remote add origin https://github.com/usuario/repositorio.git

Ver repositorios remotos conectados
git remote -v

Subir el proyecto (primera vez)
git push -u origin main


(Usa master si tu rama principal se llama así)

⬇️ 10. Descargar cambios desde GitHub
Traer los últimos commits
git pull origin main

Ver qué hay de nuevo sin descargar
git fetch

🔄 11. Actualizar y mantener sincronizado
Acción	Comando
Guardar cambios locales	git add . && git commit -m "mensaje"
Subirlos al remoto	git push
Bajar los cambios de otros	git pull
🧠 12. Buenas prácticas

✅ Haz commits pequeños y con mensajes claros.
✅ Usa ramas para nuevas funciones.
✅ Siempre haz git pull antes de git push.
✅ Añade un .gitignore para evitar subir archivos innecesarios (por ejemplo: node_modules, *.log, etc).

Ejemplo de .gitignore:

*.log
node_modules/
.env

🧩 13. Revertir o deshacer cambios
Deshacer cambios en archivos no guardados
git restore nombre_archivo

Quitar un archivo del área de preparación
git restore --staged nombre_archivo

Volver a un commit anterior
git checkout id_commit

Crear una nueva versión que deshace una anterior
git revert id_commit

🧭 14. Ejemplo completo de flujo real
# Crear carpeta y entrar
mkdir proyecto
cd proyecto

# Iniciar repositorio
git init

# Crear archivo
echo "Hola mundo" > index.html

# Añadir y hacer commit
git add .
git commit -m "Primer commit"

# Conectar con GitHub
git remote add origin https://github.com/usuario/proyecto.git

# Subir
git push -u origin main

💬 15. Comandos útiles extra
Comando	Descripción
git show	Muestra detalles del último commit
git tag -a v1.0 -m "Versión 1.0"	Crear una etiqueta de versión
git stash	Guarda cambios temporales
git stash pop	Recupera los cambios guardados
git mv viejo nuevo	Renombra un archivo
🧱 16. Autenticación moderna en GitHub

Desde 2021, GitHub ya no acepta contraseñas.
Debes usar un token personal (PAT) o SSH.

Opción HTTPS con Token

Cuando hagas git push, te pedirá usuario y contraseña.
En la contraseña, pegas el token que creas desde
👉 https://github.com/settings/tokens

Opción SSH (más segura)
ssh-keygen -t ed25519 -C "tuemail@ejemplo.com"


Luego añade la clave pública en tu perfil de GitHub:
Settings → SSH and GPG Keys → New SSH key

🔍 17. Recursos oficiales para verificar información

📘 Documentación Git: https://git-scm.com/docs

🧭 Guía de GitHub: https://docs.github.com/es/get-started

🧩 Cheat Sheet de GitHub (PDF oficial): https://training.github.com/downloads/github-git-cheat-sheet.pdf
