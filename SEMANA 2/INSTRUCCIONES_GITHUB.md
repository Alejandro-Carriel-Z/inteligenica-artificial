# Instrucciones para publicar este repositorio en GitHub

El repositorio ya está inicializado localmente con un commit inicial. Sigue estos pasos para subirlo a GitHub.

## 1. Crear un repositorio vacío en GitHub

1. Inicia sesión en [GitHub](https://github.com) (cuenta asociada a tu correo institucional si aplica).
2. **New repository**.
3. Elige un nombre, por ejemplo: `semana2-clasificacion-ids`.
4. **No** marques “Add a README”, “Add .gitignore” ni “Choose a license” (este proyecto ya los incluye).
5. Crea el repositorio y copia la URL HTTPS que te muestra GitHub.

## 2. Conectar el remoto y subir

En PowerShell, desde la carpeta del proyecto:

```powershell
cd "C:\Users\carri\Desktop\PUCE\Quinto semestre\Inteligencia artificial\semana2-clasificacion-ids"

git remote add origin https://github.com/<USER>/<REPO>.git
git branch -M main
git push -u origin main
```

Sustituye `<USER>` por tu usuario de GitHub y `<REPO>` por el nombre del repositorio creado.

## 3. Notas

- Usuario Git local sugerido en esta máquina: **Alejandro_Carriel** / **ADCARRIEL@puce.edu.ec**.
- No adivines el nombre de usuario de GitHub; usa el de tu cuenta real.
- Si `git push` pide autenticación, usa un **Personal Access Token** (Settings → Developer settings) o GitHub CLI (`gh auth login`).
- No uses `git push --force` sobre `main` salvo que sepas exactamente por qué lo necesitas.

## 4. Verificación

Tras el push, abre la URL del repositorio y comprueba que aparecen `README.md`, `notebooks/`, `data/`, `reports/` y `results/`.
