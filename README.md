# Guía de Instalación y Ejecución

Este documento explica cómo configurar el entorno de desarrollo local para el proyecto y levantar el servidor.

## 1. Crear y activar un entorno virtual

Utilizar un entorno virtual es fundamental para mantener las dependencias del proyecto aisladas y evitar conflictos con otros proyectos en tu sistema.

**Crear el entorno virtual:**
```bash
python -m venv .venv
```
o bien
```bash
py -m venv .venv
```

**Activar el entorno virtual (Windows PowerShell):**
```powershell
.venv\Scripts\Activate.ps1
```
*(Nota: Si usas la consola CMD de Windows, usa `.venv\Scripts\activate.bat`. Si usas Linux o macOS, el comando es `source .venv/bin/activate`).*

## 2. Instalar dependencias

Una vez activado el entorno (deberías ver `(.venv)` al inicio de tu línea de comandos), instala los paquetes requeridos que están listados en el archivo de configuración:

```bash
cd trotamundos_prototipo
pip install -r requirements.txt
```

## 3. Ejecutar la aplicación

Levanta el servidor local utilizando Uvicorn. El flag `--reload` indica que el servidor se reiniciará automáticamente cada vez que guardes cambios en el código, lo cual es ideal para la etapa de desarrollo.

```bash
cd trotamundos_prototipo
uvicorn app.main:app --reload
```

---

## 🌐 Enlaces y Rutas Disponibles

Con el servidor en ejecución, abre tu navegador web y accede a los siguientes recursos:

- **Interfaz web:** [http://127.0.0.1:8000](http://127.0.0.1:8000) — *Acceso a la vista principal de la aplicación.*
- **API interactiva:** [http://127.0.0.1:8000/docs](http://127.0.0.1:8000/docs) — *Documentación autogenerada (Swagger UI) para explorar y probar los endpoints de la API en tiempo real sin necesidad de herramientas externas.*
- **Estado del servicio:** [http://127.0.0.1:8000/health](http://127.0.0.1:8000/health) — *Endpoint de comprobación (health check) para verificar rápidamente que la aplicación está viva y funcionando.*
