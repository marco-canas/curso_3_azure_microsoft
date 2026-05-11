Para la **Fase 1: Fundamentos de Cloud y Datos**, el objetivo es que dejes de ver a Azure como "una página web con botones" y empieces a verla como una infraestructura programable desde Python.

Esta es una secuencia detallada de 4 sesiones (2 semanas):

---

# Sesión 1: El Ecosistema de Datos en Azure

**Objetivo:** Comprender dónde encaja el Científico de Datos en la infraestructura de nube.

* **Teoría:**
* Introducción a la arquitectura de Azure: Regiones, Grupos de Recursos y Suscripciones.
* Diferencia entre **IaaS** (Maquinas Virtuales) y **PaaS** (Servicios administrados como Azure ML).
* Exploración del portal de Azure y el CLI (Command Line Interface).


* **Práctica:**
* Creación de una cuenta gratuita y configuración de un **Resource Group** dedicado al curso.
* Instalación de la extensión de Azure en VS Code.



---

# Sesión 2: Almacenamiento y Conectividad con Python

**Objetivo:** Mover datos entre tu entorno local y la nube sin usar el navegador.

* **Teoría:**
* **Azure Blob Storage:** El "disco duro" de la nube. Contenedores, Blobs y Niveles de acceso (Hot, Cool, Archive).
* Seguridad: Claves de acceso vs. Firmas de Acceso Compartido (SAS).


* **Práctica (Python):**
* Uso de la librería `azure-storage-blob`.
* **Script de carga:** Crear un script que suba automáticamente archivos `.csv` o imágenes a un contenedor de Azure.
* **Script de descarga:** Leer un dataset directamente desde el Blob Storage a un DataFrame de Pandas.



---

# Sesión 3: El Workspace de Azure Machine Learning

**Objetivo:** Configurar el "centro de mando" para tus experimentos de ML.

* **Teoría:**
* Componentes del Workspace: Datastores, Compute, Experiments y Models.
* Concepto de **Compute Instance** (tu estación de trabajo en la nube) vs. **Compute Cluster** (poder de procesamiento escalable).


* **Práctica:**
* Despliegue de un Workspace de Azure ML desde el portal.
* Configuración de una **Compute Instance** ligera (tipo DS11_v2) para desarrollo interactivo.
* Conexión de VS Code remoto a la instancia de Azure.



---

# Sesión 4: Entornos y Autenticación (El "Pegamento")

**Objetivo:** Asegurar que tu código Python pueda "hablar" con Azure de forma segura y consistente.

* **Teoría:**
* Autenticación mediante `DefaultAzureCredential`.
* Gestión de entornos con archivos `conda.yml`: ¿Por qué es vital para la reproducibilidad en la nube?


* **Práctica (Python):**
* Instalación del SDK v2: `pip install azure-ai-ml azure-identity`.
* Escritura del primer script de conexión:
```python
from azure.ai.ml import MLClient
from azure.identity import DefaultAzureCredential

# Conexión al workspace
ml_client = MLClient(DefaultAzureCredential(), subscription_id, res_group, workspace_name)
print(f"Conectado a: {ml_client.workspace_name}")

```
# Entregable de la Fase 1:

Al finalizar estas sesiones, deberás tener un **script de Python** que tome un dataset local, lo suba a Azure Blob Storage, y confirme que el Azure ML Workspace puede "verlo" como un **Data Asset** registrado.

¿Quieres que te proporcione el código base para la Sesión 2, específicamente para la carga de archivos a Blob Storage?