# Sistema de Farmacia en PHP (MVC)

## 📌 Descripción
Aplicación web para la gestión de una farmacia desarrollada en **PHP con patrón MVC** y **MySQL**.  
Incluye un **panel de administración** (gestión de productos, usuarios, ventas) y un **panel de cliente** (catálogo y compras).  

Se añadió autenticación de clientes con registro desde la misma pantalla de login y un panel de cliente aislado del administrador.

---

## ✨ Características

### Panel Administrador
- Gestión de productos  
- Gestión de usuarios del sistema  
- Registro de ventas y detalle de venta  
- Reportes básicos  

### Panel Cliente
- Inicio de sesión y registro en la misma vista  
- Catálogo de productos  
- Flujo de compra simplificado  
- Interfaz limitada a **Productos** y **Comprar**  

### Autenticación
- Administradores/usuarios internos  
- Clientes (tabla dedicada para login de clientes)  

### Base de datos
- Basada en `v_farmacia` con tablas como:  
  - `cliente`  
  - `usuario`  
  - `producto`  
  - `ventas`  
  - `detalle_venta`  
- Tabla adicional: `cliente_login` para credenciales de clientes  

---

## ⚙️ Requisitos
- PHP **7.4** o superior  
- MySQL **5.7** o superior (o MariaDB compatible)  
- Servidor web (Apache recomendado: XAMPP/WAMP/LAMP)  
- Extensión **mysqli** habilitada  

---

## 📂 Estructura general del proyecto
- `src/` → código fuente principal (MVC)  
- `index.php` → pantalla de login principal (incluye login/registro de clientes)  
- `assets/` → recursos estáticos (css, js, imágenes)  
- `views/` → vistas para admin y cliente  
- `controllers/` → controladores  
- `models/` → modelos de acceso a datos  
- `sql/` → scripts de base de datos  

---

## 🚀 Instalación
1. Clona o copia el proyecto en el directorio del servidor web.  
2. Crea la base de datos `v_farmacia` en MySQL.  
3. Importa las tablas base y asegúrate de tener:  
   - `cliente`, `usuario`, `producto`, `ventas`, `detalle_venta`  
   - `cliente_login` para inicio de sesión de clientes  
4. Configura la conexión a la base de datos en el archivo de conexión del proyecto.  
5. Verifica permisos de escritura si se generan archivos o reportes.  
6. Inicia el servidor y accede a:  
   ```
   http://localhost/tu-carpeta/
   ```

---

## 🖥️ Uso
- **Administrador**  
  - Inicia sesión con un usuario interno.  
  - Accede al panel para gestionar productos, usuarios y ventas.  

- **Cliente**  
  - Desde `index.php`, inicia sesión o regístrate.  
  - Visualiza **Productos** y realiza compras desde **Comprar**.  
  - El cliente no tiene acceso al panel administrador.  

---

## 🗄️ Tablas relevantes
- `producto` → catálogo de productos  
- `usuario` → usuarios internos (administración)  
- `cliente` → datos generales de clientes  
- `cliente_login` → credenciales de acceso de clientes  
- `ventas` → encabezados de ventas  
- `detalle_venta` → líneas de venta  

---

## 🔒 Seguridad
- Contraseñas con `password_hash` y `password_verify`.  
- Restricción de áreas según rol/sesión.  
- Validación y sanitización de entradas.  
- Configuración de HTTPS en producción.  

---

## 🎨 Personalización
- Estilos: modificar CSS en `assets/`.  
- Navegación cliente limitada a **Productos** y **Comprar**.  
- Agregar notificaciones o toasts si se desea.  
- Integración con pasarela de pagos opcional.  

---

## 🛠️ Solución de problemas
- **Error de conexión:** revisar credenciales y host/puerto MySQL.  
- **Sesiones:** verificar `session.save_path` y permisos de carpeta.  
- **Rutas:** confirmar `DocumentRoot` y URLs relativas.  

