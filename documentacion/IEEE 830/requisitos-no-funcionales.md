# 📘 Especificación IEEE 830 — Requisitos No Funcionales

## 📚 Tabla de Contenido

- [🧠 4. Requisitos No Funcionales](#-4-requisitos-no-funcionales)
  - [⚡ 4.1 Rendimiento](#-41-rendimiento)
  - [🎯 4.2 Usabilidad](#-42-usabilidad)
  - [🔐 4.3 Seguridad](#-43-seguridad)
  - [🧱 4.4 Fiabilidad](#-44-fiabilidad)
  - [🛠️ 4.5 Mantenibilidad](#-45-mantenibilidad)
  - [🌍 4.6 Portabilidad](#-46-portabilidad)

---

## 🧠 4. Requisitos No Funcionales

### ⚡ 4.1 Rendimiento  
- 🚀 El sistema debe responder a las entradas del usuario en menos de **2 segundos** en condiciones normales de operación.  
- ⏱️ El tiempo de autenticación (validación de usuario y contraseña) no debe exceder los **3 segundos**.  
- 👥 El sistema debe ser capaz de manejar al menos **100 usuarios concurrentes** sin degradación perceptible del rendimiento.

### 🎯 4.2 Usabilidad  
- 🧭 La interfaz de línea de comandos debe presentar opciones claras, numeradas y con mensajes de error comprensibles para el usuario.  
- 🛑 Todos los campos requeridos deben validarse con mensajes específicos que indiquen el tipo de error (e.g., campo vacío, formato incorrecto).  
- 🔁 El sistema debe permitir hasta **9 intentos** de registro antes de bloquear el proceso temporalmente, con retroalimentación clara en cada paso.  
- 🧑‍💼 El flujo de navegación debe ser intuitivo, con menús diferenciados por rol (cliente, empleado, administrador) y opciones específicas para cada tipo de usuario.

### 🔐 4.3 Seguridad  
- 🔑 Las contraseñas deben tener una longitud mínima de **8 caracteres** y se recomienda que incluyan letras mayúsculas, minúsculas, números y símbolos.  
- 🕵️‍♂️ Los datos sensibles como contraseñas no deben mostrarse en pantalla ni almacenarse en texto plano (se sugiere implementar hash en futuras versiones).  
- 🚫 El sistema debe impedir el acceso a usuarios no registrados y limitar los intentos de autenticación a **3 intentos consecutivos** por sesión.  
- 🛡️ Los administradores no pueden eliminar su propia cuenta, evitando la pérdida de control del sistema.

### 🧱 4.4 Fiabilidad  
- 🧯 El sistema debe manejar errores de entrada de forma robusta, evitando caídas por excepciones no controladas.  
- 🔄 En caso de error en el ingreso de datos, el sistema debe permitir reintentos sin perder el estado actual del flujo.  
- ✅ Las operaciones críticas (cambio de rol, eliminación de usuario) deben confirmar la existencia del usuario antes de ejecutarse.

### 🛠️ 4.5 Mantenibilidad  
- 📦 El código debe estar modularizado en clases separadas por tipo de usuario y funcionalidades específicas (e.g., `Cliente`, `Empleado`, `Administrador`, `Direcciones_empleado`).  
- 🧾 Las funciones deben tener nombres descriptivos y estar organizadas por responsabilidad, facilitando futuras extensiones o refactorizaciones.  
- 📚 Se recomienda documentar cada clase y método en los archivos correspondientes para facilitar la comprensión por parte de nuevos desarrolladores.

### 🌍 4.6 Portabilidad  
- 🐍 El sistema debe poder ejecutarse en cualquier entorno que soporte **Python 3.10 o superior**, sin dependencias externas no estándar.  
- 💻 Se debe garantizar compatibilidad con sistemas operativos **Windows**, **Linux** y **macOS**.