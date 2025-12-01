# Flujo de trabajo GitHub Flow

GitHub Flow es un flujo ligero para trabajar con ramas y Pull Requests.

## Principios:
1. **Rama principal estable** (`main`).
2. **Crear ramas para nuevas funcionalidades**.
3. **Commits frecuentes y descriptivos**.
4. **Pull Request para revisión**.
5. **Pruebas antes de fusionar**.
6. **Deploy desde main**.

## Pasos detallados:

### 1. Crear una rama
```bash
git checkout -b feature-nueva
```

### 2. Hacer cambios y commits
```bash
git add .
git commit -m "Implementa nueva funcionalidad"
```

### 3. Subir la rama al remoto
```bash
git push origin feature-nueva
```

### 4. Abrir un Pull Request
- Desde GitHub, selecciona la rama y crea el PR.
- Solicita revisión y aprueba.

### 5. Fusionar y desplegar
- Haz merge en `main` cuando esté aprobado.
- Despliega desde `main`.

[Documentación oficial](https://docs.github.com/es/get-started/using-github/github-flow)
