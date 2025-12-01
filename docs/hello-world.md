# Tutorial Hello World en GitHub

Este tutorial te guía para crear tu primer repositorio y realizar tu primer commit en GitHub.

## Pasos:

### 1. Crear una cuenta en GitHub
Regístrate en [github.com](https://github.com).

### 2. Crear un nuevo repositorio
- Haz clic en **New repository**.
- Asigna un nombre (ej. `hello-world`).
- Elige público o privado.
- Opcional: Añade un README.

### 3. Clonar el repositorio
```bash
git clone https://github.com/usuario/hello-world.git
cd hello-world
```

### 4. Crear un archivo y hacer commit
```bash
echo "# Hello World" >> README.md
git add README.md
git commit -m "Primer commit"
git push origin main
```

### 5. Crear una rama y hacer cambios
```bash
git checkout -b nueva-rama
echo "Texto adicional" >> README.md
git add README.md
git commit -m "Actualización en nueva rama"
git push origin nueva-rama
```

### 6. Abrir un Pull Request
- Ve al repositorio en GitHub.
- Haz clic en **Compare & pull request**.
- Revisa y confirma el merge.

[Documentación oficial](https://docs.github.com/es/get-started/start-your-journey/hello-world)
