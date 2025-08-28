# Gestión de Activos y Hojas de Vida TIC

[![Licencia: MIT](https://img.shields.io/badge/Licencia-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

Una aplicación web completa para la gestión centralizada del inventario tecnológico (equipos, software, periféricos), el seguimiento de hojas de vida de usuarios y el registro de mantenimientos en un entorno multiempresa.

**[Ver Demo en Vivo →](it-asset-manager.netlify.app)**

## Tabla de Contenidos

1.  [Características Principales](#-características-principales)
2.  [Tecnologías Utilizadas](#-tecnologías-utilizadas)
3.  [Instalación y Puesta en Marcha](#-instalación-y-puesta-en-marcha)
4.  [¿Cómo Colaborar?](#-cómo-colaborar)
5.  [Licencia](#-Licencia)
6.  [Apoya este Proyecto](#-apoya-este-proyecto)
7.  [Una Nota Especial](#-una-nota-especial)

## ✨ Características Principales

* **🏢 Gestión Multiempresa:** Crea, gestiona e invita a usuarios a múltiples empresas desde una sola cuenta.
* **💻 Inventario Completo:** Registra y clasifica equipos, software y periféricos con detalles de compra, garantía y costos.
* **👤 Hojas de Vida de Usuarios:** Asigna activos a los usuarios, registra fechas de ingreso, cargos y gestiona sus perfiles.
* **🛠️ Registro de Mantenimiento:** Lleva un historial detallado de todos los mantenimientos realizados a los equipos.
* **📊 Dashboard y Reportes:** Visualiza métricas clave de tu inventario con gráficos interactivos.
* **🔄 Importación/Exportación CSV:** Carga o exporta masivamente datos de usuarios y activos.
* **📄 Exportación a PDF:** Genera hojas de vida completas de los usuarios en formato PDF con un solo clic.
* **🔐 Autenticación Segura:** Sistema de inicio de sesión y registro utilizando Supabase Auth, con opción para proveedores como Google.

## 🚀 Tecnologías Utilizadas

* **Frontend:** HTML5, Tailwind CSS, JavaScript (Vanilla JS)
* **Backend y Base de Datos:** Supabase (Postgres, Auth, Storage, Edge Functions)
* **Librerías Adicionales:**
    * `Chart.js` para gráficos y reportes.
    * `jsPDF` y `jsPDF-AutoTable` para la exportación de PDFs.

## 🔧 Instalación y Puesta en Marcha

Para ejecutar este proyecto localmente, sigue estos pasos:

**1. Clona el Repositorio**
```bash
git clone https://github.com/MiltonEsc/it-asset-manager.git
```
**2. Configura tu Proyecto en Supabase**

Ve a Supabase.io y crea un nuevo proyecto.

Guarda tu URL del Proyecto y tu clave anon public de la sección Project Settings > API.

**3. Ejecuta el Esquema de la Base de Datos**

Dentro de tu proyecto en Supabase, ve a SQL Editor.

Abre el archivo **schema.sql** de este repositorio, copia su contenido, pégalo en el editor y haz clic en "RUN".

**4. Configura el Almacenamiento (Storage)**

En el dashboard de Supabase, ve a Storage y crea los siguientes buckets con acceso público: activos, facturas, evidencias.

Vuelve a SQL Editor, abre **storage_schema.sql**, copia el contenido, pégalo y ejecútalo para crear las políticas de seguridad.

**5. Despliega las Edge Functions (con Supabase CLI)**

Instala la CLI de Supabase en la terminal.
[Documentacion de Supabase](https://supabase.com/docs/guides/local-development/cli/getting-started)

Inicia sesión y vincula tu proyecto:

```bash
supabase login
```
```bash
supabase link --project-ref TU_PROJECT_REF
```
**Despliega las funciones:**

```bash
supabase functions deploy
```
**6. Configura las Claves publicas**

Abre el archivo index.html.

Busca y reemplaza los valores de SUPABASE_URL y SUPABASE_KEY con tus credenciales:

JavaScript

// --- CONFIGURACIÓN DE SUPABASE ---
const SUPABASE_URL = 'URL_DE_TU_PROYECTO_SUPABASE';
const SUPABASE_KEY = 'TU_CLAVE_PUBLICA_ANON';
**7. Configura las URLs de Redirección**

En Supabase, ve a Authentication > URL Configuration.

En Site URL, introduce la URL de tu aplicación (ej: http://localhost:3000).

¡Listo! Abre el archivo index.html en tu navegador para empezar.

🤝 ¿Cómo Colaborar?
¡Gracias por tu interés en colaborar!

Reporta Bugs o Sugiere Mejoras: Abre un nuevo "Issue".

Haz un Fork del repositorio.

Crea una Nueva Rama (git checkout -b feature/nombre-mejora).

Realiza tus cambios y envía un Pull Request con una descripción clara.

##📜 Licencia
Este proyecto está bajo la Licencia MIT. Consulta el archivo LICENSE para más detalles.

##❤️ Apoya este Proyecto
Si esta aplicación te ha sido de utilidad, ¡considera apoyarme con un café! Tu apoyo me motiva a seguir mejorando este proyecto.

##✨ Una Nota Especial
Este proyecto fue desarrollado en colaboración con Gemini, una IA de Google. Sirve como un ejemplo de cómo la inteligencia artificial puede actuar como un compañero de programación, ayudando a resolver problemas, generar código y acelerar el proceso de creación.

