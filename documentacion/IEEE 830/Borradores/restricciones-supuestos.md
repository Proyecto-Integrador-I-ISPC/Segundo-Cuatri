# 2.4 Restricciones



**Tecnologías**: El desarrollo deberá basarse en tecnologías **open-source** ampliamente utilizadas y con soporte activo de la comunidad, tales como:

  * **Motor de base de datos**: MySQL o equivalente (MariaDB, PostgreSQL en caso de migración futura).
  * **Backend**: Python con frameworks como Django, Flask o FastAPI.
  * **Frontend**: HTML5, CSS3, JavaScript (ES6+) y frameworks/librerías opcionales como React, Vue o similares.
  * Se excluye en esta primera etapa el uso de tecnologías propietarias o dependientes de licencias costosas, con el fin de mantener la escalabilidad y sostenibilidad del sistema.

* **Internacionalización e idioma**: La primera versión (MVP) estará disponible únicamente en **idioma español**, aunque se contemplará la integración de servicios externos como **Google Translate** para habilitar la traducción automática a futuro.

* **Compatibilidad y navegadores**: La aplicación debe ser accesible desde **navegadores modernos** (Google Chrome, Mozilla Firefox, Microsoft Edge, Opera y Brave). El sistema deberá garantizar soporte oficial para las **dos últimas versiones estables** de cada navegador, asegurando así compatibilidad y un alcance amplio a usuarios finales.

* **Rendimiento y UX**: El tiempo de respuesta en operaciones estándar (peticiones GET, POST, PUT, DELETE bajo condiciones normales de carga) **no debe superar los 3 segundos**. Para alcanzar dicho objetivo, se priorizará el uso de consultas optimizadas, caching en memoria y un diseño eficiente de la base de datos.

**Seguridad y normativa**: El sistema deberá cumplir en todas sus etapas con la **Ley 25.326 de Protección de Datos Personales (Argentina)** y normativas equivalentes, incorporando:

  * **Autenticación en dos factores (2FA)**.
  * **Cifrado de contraseñas** mediante algoritmos robustos (ej: bcrypt).
  * **Encriptación de datos sensibles en tránsito y en reposo** (HTTPS).
  * **Gestión de sesiones seguras** con expiración automática y JWT.
    Estas medidas buscan resguardar la confidencialidad, integridad y disponibilidad de la información.

**Alcance funcional limitado (MVP)**: La autenticación se realizará únicamente mediante usuario y contraseña internos al sistema. **No se contemplará integración con terceros (ej: redes sociales, SSO corporativos)** en esta primera entrega.

**Integraciones externas**: Se habilitarán únicamente aquellas solicitadas explícitamente por el cliente, siendo la principal la **integración con pasarelas de pago** (ejemplo: MercadoPago). No se prevén integraciones adicionales (ej: sistemas contables o de RRHH) durante la primera versión.

**Reportes**: Los reportes de lavados y facturación deberán generarse en **PDF y/o Excel**, según la preferencia del cliente, garantizando exportación clara, con encabezados, filtros y totales.

**Plazos de entrega**: El software deberá entregarse dentro del **plazo previamente acordado** con el cliente. Cualquier extensión deberá ser validada formalmente.




## 2.5 Supuestos



**Conectividad de los usuarios**: Se asume que los usuarios finales contarán con una **conexión a internet estable y de velocidad media/alta**, condición necesaria para garantizar tiempos de respuesta acordes a los objetivos de UX.

**Volumen inicial de usuarios concurrentes**: Se estima que el sistema deberá soportar hasta **100 usuarios concurrentes** en tiempo real durante la primera etapa. Este límite se toma como referencia para dimensionar la arquitectura y no implica que el sistema no pueda escalar en versiones futuras.

**Validación de datos ingresados**: El sistema asumirá que los **datos provistos por los usuarios serán válidos y completos**, aplicando únicamente validaciones básicas (ejemplo: formato de patente). Casos excepcionales (datos incompletos, tickets perdidos) serán gestionados manualmente por el personal administrativo.

**Despliegue y hosting**: La **infraestructura de producción (servidor, dominio y hosting)** será provista por el cliente, aunque el equipo de desarrollo podrá brindar asesoramiento técnico para la correcta implementación.

**Volumen inicial de datos**: Se prevé que en la primera etapa no se superarán los **5.000 registros de lavados por mes**, siendo una carga fácilmente soportada por la base de datos relacional seleccionada.

**Ámbito de uso**: El sistema estará orientado a una **única sucursal** en su primera entrega. Procesos inter-sucursal o integraciones de múltiples sedes serán responsabilidad del cliente y/o contemplados en futuras versiones.

**Gestión manual de excepciones**: Situaciones fuera de la operatividad estándar, como **pérdida de tickets, lavados no registrados o conciliaciones entre sucursales**, serán resueltas manualmente por el cliente en esta primera etapa.

**Capacitación del personal**: Se asume que el personal administrativo y de atención al cliente recibirá **capacitación adecuada** en el uso del sistema, lo que permitirá reducir incidencias y asegurar un correcto aprovechamiento de las funcionalidades.

**Requisitos técnicos del cliente**: Los usuarios finales deberán disponer de **navegadores actualizados (versiones estables)** para prevenir inconsistencias o errores de compatibilidad.

**Operatividad continua de integraciones**: Se asume que las integraciones externas críticas, como la **pasarela de pagos**, estarán disponibles de forma continua. Caídas prolongadas o incidencias en estos servicios quedan fuera del alcance del presente desarrollo.
