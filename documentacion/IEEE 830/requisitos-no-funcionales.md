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

---

### ⚡ 4.1 Rendimiento  
El sistema Aquamóvil está desarrollado como una aplicación de línea de comandos, lo que permite tiempos de respuesta inmediatos en entornos locales. La autenticación se realiza mediante comparación directa de credenciales en estructuras internas, sin acceso a bases de datos externas ni procesos asincrónicos.

- 🚀 **Tiempo de respuesta:** El sistema responde a entradas del usuario en menos de **2 segundos** en condiciones normales, validado mediante pruebas manuales en CLI.  
- ⏱️ **Autenticación:** El proceso de login se completa en menos de **3 segundos**, gracias a la validación directa en estructuras de datos.  
- 👥 **Concurrencia:** Aunque no se ha implementado concurrencia real, el diseño modular permite escalar hacia múltiples sesiones simultáneas en futuras versiones.

---

### 🎯 4.2 Usabilidad  
La interfaz de Aquamóvil está diseñada para ser clara y funcional en entornos de línea de comandos. Cada rol tiene un menú específico, y las opciones están numeradas y acompañadas de mensajes descriptivos.

- 🧑‍💼 **Interfaz por rol:** Los usuarios acceden a menús diferenciados según su tipo (`Cliente`, `Empleado`, `Administrador`), con opciones específicas para cada perfil.  
- 🛑 **Validaciones:** Todos los campos requeridos son validados. Se implementan mensajes de error específicos como “campo vacío” o “formato incorrecto”.  
- 🔁 **Registro:** El sistema permite hasta **9 intentos** de registro antes de bloquear temporalmente el proceso, con retroalimentación en cada paso.  
- 🧭 **Navegación:** El flujo de interacción es secuencial e intuitivo, con confirmaciones antes de operaciones críticas.

---

### 🔐 4.3 Seguridad  
La seguridad en Aquamóvil se implementa a nivel lógico, con restricciones de acceso y control de autenticación. Aunque no se utiliza cifrado aún, el diseño contempla su incorporación.

- 🔑 **Contraseñas:** Se exige una longitud mínima de **8 caracteres**. La validación incluye presencia de letras y números.  
- 🚫 **Control de acceso:** Los usuarios no registrados no pueden acceder al sistema. Se limita el login a **3 intentos consecutivos** por sesión.  
- 🛡️ **Protección de administrador:** El sistema impide que un administrador elimine su propia cuenta, preservando el control del sistema.  
- 🕵️‍♂️ **Cifrado pendiente:** Actualmente las contraseñas se almacenan en texto plano, pero se ha planificado la implementación de hash con `bcrypt` o `hashlib`.

---

### 🧱 4.4 Fiabilidad  
El sistema maneja errores mediante estructuras `try/except`, evitando caídas inesperadas. Las operaciones críticas requieren validación previa.

- 🧯 **Manejo de errores:** Se implementan bloques `try/except` para capturar excepciones en ingreso de datos y navegación.  
- 🔄 **Reintentos:** En caso de error, el sistema permite reintentar sin perder el estado del flujo.  
- ✅ **Validación previa:** Antes de eliminar usuarios o cambiar roles, se verifica la existencia del usuario en el sistema.

---

### 🛠️ 4.5 Mantenibilidad  
El código está organizado en módulos y clases por tipo de usuario, lo que facilita su extensión y mantenimiento.

- 📦 **Modularización:** Clases como `Cliente`, `Empleado`, `Administrador` y `Direcciones_empleado` encapsulan funcionalidades específicas.  
- 🧾 **Funciones descriptivas:** Los métodos tienen nombres claros como `validar_datos()`, `mostrar_menu()`, `registrar_usuario()`, lo que facilita su comprensión.  
- 📚 **Documentación:** Se han incluido comentarios explicativos en el código. Se recomienda formalizar la documentación con docstrings en formato Google o NumPy.

---

### 🌍 4.6 Portabilidad  
Aquamóvil está desarrollado en Python 3.10, sin dependencias externas, lo que permite su ejecución en múltiples plataformas.

- 🐍 **Entorno:** Compatible con cualquier sistema que soporte **Python 3.10 o superior**.  
- 💻 **Sistemas operativos:** Probado en **Windows** y **Linux**. Se proyecta compatibilidad con **macOS**.  
- 📦 **Dependencias:** No se utilizan librerías externas, lo que simplifica la instalación y despliegue.

---
