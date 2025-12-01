# Buenas prácticas en Jenkins

## 1. Usa Pipelines como código
- Define tus flujos en un `Jenkinsfile`.
- Versiona el pipeline junto con el código fuente.

## 2. Seguridad
- Configura **autenticación y autorización**.
- Activa **CSRF Protection** y **Content Security Policy**.
- Usa credenciales seguras (Credential Store).

## 3. Gestión de plugins
- Instala solo los necesarios.
- Mantén Jenkins y plugins actualizados.

## 4. Escalabilidad
- Usa **agentes distribuidos** para cargas grandes.
- Considera Kubernetes para entornos dinámicos.

## 5. Buenas prácticas en Pipeline
- Usa **Declarative Pipeline** para mayor legibilidad.
- Evita lógica compleja en Jenkinsfile.
- Implementa pruebas y validaciones antes del despliegue.

[Documentación oficial](https://www.jenkins.io/doc/book/using/best-practices/)
