Gestión de Activos y Hojas de Vida TIC
Una aplicación web completa para la gestión centralizada del inventario tecnológico (equipos, software, periféricos), el seguimiento de hojas de vida de usuarios y el registro de mantenimientos en un entorno multiempresa.

<p align="center">
<a href="https://it-asset-manager.netlify.app/" target="_blank">
<img src="https://placehold.co/800x400/e2e8f0/667eea?text=Ver+Demo+en+Vivo" alt="Captura de pantalla de la aplicación"/>
</a>
</p>

<p align="center">
<a href="https://it-asset-manager.netlify.app/" target="_blank">
<strong>Ver Demo en Vivo &rarr;</strong>
</a>
</p>

✨ Características Principales
🏢 Gestión Multiempresa: Crea, gestiona e invita a usuarios a múltiples empresas desde una sola cuenta.

💻 Inventario Completo: Registra y clasifica equipos, software y periféricos con detalles de compra, garantía y costos.

👤 Hojas de Vida de Usuarios: Asigna activos a los usuarios, registra fechas de ingreso, cargos y gestiona sus perfiles.

🛠️ Registro de Mantenimiento: Lleva un historial detallado de todos los mantenimientos realizados a los equipos, incluyendo descripciones y evidencias.

📊 Dashboard y Reportes: Visualiza métricas clave de tu inventario, como el estado de los equipos, licencias por vencer y costos totales.

🔄 Importación/Exportación CSV: Carga masivamente datos de usuarios y activos o exporta tus inventarios a formato CSV.

📄 Exportación a PDF: Genera hojas de vida completas de los usuarios en formato PDF con un solo clic.

🔐 Autenticación Segura: Sistema de inicio de sesión y registro de usuarios utilizando Supabase Auth.

🚀 Tecnologías Utilizadas
Frontend: HTML5, Tailwind CSS, JavaScript (Vanilla JS)

Backend y Base de Datos: Supabase (Base de datos Postgres, Autenticación, Storage)

Librerías Adicionales:

Chart.js para gráficos y reportes.

jsPDF y jsPDF-AutoTable para la exportación de PDFs.

🔧 Instalación y Puesta en Marcha
Para ejecutar este proyecto, necesitas configurarlo con tu propia instancia de Supabase.

Clona el repositorio:

1. git clone https://github.com/TU_USUARIO/TU_REPOSITORIO.git
2. Crea tu proyecto en Supabase:

  2.1 Ve a Supabase.io y crea un nuevo proyecto.

  2.2 En el dashboard de tu proyecto, ve a la sección SQL Editor.

  2.3 Abre el archivo schema.sql de este repositorio, copia todo su contenido, pégalo en el editor de Supabase y haz clic en "RUN". Esto creará todas las tablas, funciones y políticas de seguridad necesarias.

3. Ve a la sección Storage y crea los buckets necesarios con acceso público: activos, facturas, evidencias.

  3.1 Abre el archivo storage_schema.sql de este repositorio, copia todo su contenido, pégalo en el editor de Supabase y haz clic en "RUN". Esto creará todas las políticas de los buckets necesarias.

4. Instalar la CLI de Supabase
Si aún no la tienes, primero debes instalar la Command Line Interface (CLI) de Supabase. Puedes encontrar las instrucciones detalladas y actualizadas para tu sistema operativo directamente en la documentación oficial de Supabase.

5. Desplegar las Edge Functions
Ahora que tienes la CLI y estás dentro de la carpeta supabase, sigue estos pasos para desplegar las funciones.

  5.1. Inicia sesión en la CLI de Supabase
  Este comando te conectará con tu cuenta de Supabase.
  
  supabase login
  Esto abrirá tu navegador para que autorices el acceso.

  5.2 Vincula tu carpeta local con tu proyecto remoto
  Necesitas el Project Ref (la ID de tu proyecto), que puedes encontrar en el panel de control de Supabase, en Project Settings > General.

  Reemplaza 'TU_PROJECT_REF' con la ID de tu proyecto
  
  supabase link --project-ref TU_PROJECT_REF
  La CLI te pedirá la contraseña de tu base de datos para verificar la conexión.

  5.3 Verifica la conexión (Opcional pero recomendado)
  Asegúrate de que estás conectado al proyecto correcto.

  supabase status
  Este comando te mostrará la información del proyecto remoto al que estás vinculado actualmente. 

  5.4 Ahora sí, despliega tus funciones
  Con tu proyecto ya vinculado, despliega todas tus funciones con este comando.

  supabase functions deploy

6. Configura las claves de Supabase en el código:

  6.1 Abre el archivo index.html.
  Busca la sección // --- CONFIGURACIÓN DE SUPABASE --- en el script.
  Deberás reemplazar SUPABASE_URL y SUPABASE_KEY con las credenciales de tu proyecto.
 
 ¿Cómo buscar la API Key y la URL en Supabase?
 
 Dentro de tu proyecto en Supabase, ve a Project Settings (el ícono de engranaje en el menú lateral izquierdo).

  Selecciona la pestaña API.

  En la sección Project URL, encontrarás la URL que necesitas. Cópiala.

  En la sección Project API Keys, copia la clave que dice anon y public. Importante: No uses la clave service_role en el frontend por seguridad.

  Pega las credenciales en tu código JavaScript

const SUPABASE_URL = 'URL_DE_TU_PROYECTO_SUPABASE'; // Pega aquí la URL
const SUPABASE_KEY = 'TU_CLAVE_PUBLICA_ANON';      // Pega aquí la clave anon public

(Opcional) Habilitar autenticación con Google:

Si deseas permitir que los usuarios se registren o inicien sesión con su cuenta de Google, ve a la sección Authentication > Providers en tu dashboard de Supabase.

Busca Google en la lista y habilítalo.

Deberás seguir las instrucciones para configurar tus credenciales de cliente OAuth desde la Google Cloud Console. Puedes encontrar una guía detallada en la documentación de Supabase.

(Opcional) Redireccionar la URL a tu servidor:

Por defecto, después de acciones como la confirmación de correo o el inicio de sesión, Supabase redirige a su propia URL. Para que los usuarios regresen a tu sitio web, ve a Authentication > URL Configuration.

En el campo Site URL, introduce la URL donde tendrás alojada la aplicación (por ejemplo, http://localhost:3000 para desarrollo local o https://tu-dominio.com para producción).

¡Listo! Abre el archivo index.html en tu navegador para empezar a usar la aplicación.

🤝 ¿Cómo Colaborar?
¡Gracias por tu interés en colaborar! Toda ayuda es bienvenida. Si quieres contribuir al proyecto, por favor sigue estos pasos:

Reporta Bugs o Sugiere Mejoras: Si encuentras un error o tienes una idea para una nueva funcionalidad, por favor abre un "Issue" para que podamos discutirlo. (Nota: si el repositorio es privado, necesitarás invitar a los colaboradores para que puedan ver y crear issues).

Haz un Fork del Repositorio: Crea una copia del proyecto en tu propia cuenta de GitHub.

Crea una Nueva Rama:

Bash

git checkout -b feature/nombre-de-tu-mejora
Realiza tus Cambios: Escribe tu código y asegúrate de que todo funcione correctamente.

Envía un Pull Request: Una vez que termines, envía un "Pull Request" desde tu rama a la rama main de este repositorio. Por favor, incluye una descripción clara de los cambios que realizaste.

❤️ Apoya este Proyecto
Si esta aplicación te ha sido de utilidad, te ha ahorrado tiempo o te ha ayudado a aprender, ¡considera apoyarme con un café! Tu apoyo me motiva a seguir manteniendo y mejorando este proyecto.

<a href='https://ko-fi.com/miltondemo' target='_blank'>
<img height='36' style='border:0px;height:36px;' src='https://storage.ko-fi.com/cdn/kofi2.png?v=3' border='0' alt='Buy Me a Coffee at ko-fi.com' />
</a>

✨ Una Nota Especial
Este proyecto fue desarrollado en colaboración con Gemini, una IA de Google. Sirve como un ejemplo de cómo la inteligencia artificial puede actuar como un compañero de programación, ayudando a resolver problemas, generar código y acelerar el proceso de creación.
