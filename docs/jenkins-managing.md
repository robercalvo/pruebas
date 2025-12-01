# Administración de Jenkins

## Configuración del sistema
- Ajusta parámetros globales desde **Manage Jenkins > Configure System**.
- Configura herramientas (JDK, Git, Maven).

## Gestión de nodos
- Añade agentes para distribuir cargas.
- Configura etiquetas para asignar jobs a nodos específicos.

## Gestión de plugins
- Instala y actualiza desde **Manage Plugins**.
- Haz backup antes de actualizaciones críticas.

## Seguridad
- Control de acceso basado en roles.
- Aísla el controlador (Controller Isolation).
- Protege credenciales y SCM.

## Backup y restauración
- Copia el directorio `JENKINS_HOME`.
- Usa herramientas externas para snapshots.

## Monitorización
- Revisa logs y métricas.
- Configura alertas para fallos.

[Documentación oficial](https://www.jenkins.io/doc/book/managing/)
