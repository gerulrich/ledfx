# ledfx - Automatización de Releases

Automatización del build y distribución de releases de [ledfx](https://github.com/LedFx/LedFx) en Docker Hub.

## 🎯 Objetivo

Este repositorio automatiza completamente el proceso de generación y distribución de releases de ledfx:

1. **Renovate** monitorea las actualizaciones de versiones de ledfx
2. Crea y mergea automáticamente PRs con las nuevas versiones
3. Al mergear, se disparan automáticamente:
   - Creación de la release
   - Build de la imagen Docker
   - Push de la imagen a Docker Hub

## 🔄 Flujo de Automatización

```
ledfx upstream → Renovate detecta actualización
                    ↓
                 Crea PR con nueva versión
                    ↓
                 Mergea PR automáticamente
                    ↓
                 GitHub Actions dispara:
                    • Crea release
                    • Build imagen Docker
                    • Push a Docker Hub
```

## 🛠️ Herramientas Utilizadas

- **Renovate**: Detección y actualización automática de versiones
- **GitHub Actions**: Orquestación del pipeline de CI/CD
- **Docker**: Build y distribución de imágenes
- **Docker Hub**: Registry de imágenes Docker

## 📋 Requisitos

- Repositorio en GitHub
- Cuenta en Docker Hub con credenciales configuradas
- GitHub Actions habilitado en el repositorio
- Renovate App instalada y configurada

## ⚙️ Configuración

Consulta los archivos de configuración en el repositorio:

- `.github/workflows/` - Workflows de GitHub Actions
- `renovate.json` - Configuración de Renovate
- `Dockerfile` - Definición de la imagen Docker

## 🚀 Uso

Una vez configurados el flujo y Renovate:

1. Las actualizaciones se detectan automáticamente
2. Se crean PRs automáticamente
3. Tras el merge, se generan automáticamente las releases y se publican en Docker Hub

No requiere intervención manual en el proceso de actualización.