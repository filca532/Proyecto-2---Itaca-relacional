# Proyecto 2 · Analítica académica ITACA (relacional)

## Descripción y objetivo

Análisis académico con el mismo modelo y dashboard final que P1, partiendo de una réplica de ITACA en PostgreSQL. La extracción vía JDBC y las transformaciones permitirán comparar el recorrido relacional con la ingesta de XML.

Estado actual: entorno base del Bloque 0. La ingesta, el procesamiento y los dashboards todavía no están implementados.

## Arquitectura

Diagrama provisional del pipeline previsto.

~~~mermaid
flowchart LR
    A["Réplica ITACA en PostgreSQL"] --> B["Ingesta JDBC"]
    B --> C["Almacenamiento intermedio"]
    C --> D["ETL y modelo académico"]
    D --> E["Power BI"]
~~~

## Fuentes de datos

| Fuente / origen | Formato | Frecuencia | Licencia / acceso |
|---|---|---|---|
| Réplica de ITACA | PostgreSQL / JDBC | Por definir | Acceso restringido |

Última ingesta: ninguna. Los endpoints, esquemas y licencias pendientes se documentarán al elegir los conjuntos concretos.

## Estructura del repositorio

| Carpeta | Contenido |
|---|---|
| `01_ingesta/` | Extracción y validación inicial de las fuentes. |
| `04_etl/` | Limpieza, transformación y preparación de datos. |
| `08_dashboards/` | Informes y dashboards del proyecto. |
| `docs/` | Diagramas, capturas y evidencias de prácticas. |
| `data/` | Datos locales. Su contenido no se versiona, excepto .gitkeep. |

En la raíz: README.md, .gitignore y .env.example. Las carpetas vacías contienen .gitkeep para conservar su estructura en Git.

## Cómo desplegar el entorno

Requisitos: Git, Python 3.10+ con pip y un editor. Docker y Docker Compose serán necesarios al incorporar los servicios.

Este proyecto todavía no incluye Docker Compose; la infraestructura y los pasos de despliegue se definirán en su bloque correspondiente.

El archivo .env.example está vacío de forma intencionada: las variables de configuración aún no están definidas. Se completará a medida que se incorporen servicios y scripts. Por ahora no es necesario crear un archivo .env.

No se versionan credenciales ni datos reales del alumnado. Los datos locales se guardan en data/ y quedan excluidos de Git.

## Bitácora de prácticas

### Bloque 0 · Entorno

- **Objetivo:** preparar un repositorio independiente y documentar el pipeline.
- **Pasos realizados:** estructura inicial, README, .gitignore y .env.example vacío.
- **Problemas encontrados y solución:** sin incidencias en la creación de la estructura local.
- **Resultado:** estructura inicial preparada y documentada.

Los próximos bloques se registrarán cuando se realicen, con objetivo, pasos, problemas y resultado.

## Decisiones técnicas

| Decisión | Alternativa descartada | Motivo |
|---|---|---|
| Repositorio Git independiente | Un repositorio para los cuatro proyectos | Separar la evolución y entrega de cada proyecto |
| Definir las variables cuando se incorporen servicios y scripts | Anticipar variables sin requisitos confirmados | Mantener .env.example vacío hasta conocer la configuración necesaria; las credenciales futuras irán en .env, excluido de Git |
| Carpetas numeradas de la plantilla | Carpetas sin relación con los bloques | Facilitar la navegación durante el módulo |

## Incidencias resueltas

No hay incidencias resueltas registradas todavía.

## Resultado final

Pendiente de los bloques del módulo. Se incorporarán capturas de los dashboards, métricas y enlaces a la demo cuando existan.
