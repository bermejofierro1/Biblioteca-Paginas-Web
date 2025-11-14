# 🌐 Gestor de Páginas Web – JavaFX + MongoDB

### Aplicación de escritorio para la gestión personalizada de páginas web por usuario

Este proyecto es una aplicación desarrollada con JavaFX y MongoDB que permite a los usuarios añadir, consultar, modificar y visualizar páginas web organizadas por categorías. Incluye sistema de login, control de permisos, carga dinámica de vistas y un visor integrado mediante WebView.

## 🚀 Características principales
### 🔐 Sistema de autenticación

Inicio de sesión por correo y contraseña (con hash SHA-256).

Distinción entre usuario normal y administrador.

Gestión de datos del usuario en memoria mediante Stage.setUserData().

### 📄 Gestión completa de páginas web

Añadir páginas web asociadas a un usuario.

Editar nombre, categoría y fecha de actualización.

Eliminar páginas (solo administrador o propietario).

Apertura de páginas dentro de la aplicación mediante WebView.

### 📊 Consultas avanzadas

Filtrado de páginas por usuario.

Búsqueda por nombre.

Tablas dinámicas con JavaFX (TableView).

Indicador de carga mediante ProgressBar.

Efecto visual BoxBlur mientras se consulta.

### 📁 Persistencia en MongoDB

Colección de usuarios y páginas.

Actualización eficiente mediante:

updateOne, updateMany, replaceOne

Filters.eq, Filters.regex

Updates.addToSet, Updates.set

Recuperación de categorías dinámicas desde los documentos almacenados.

## 🧱 Arquitectura del proyecto
### 🖥️ Interfaz gráfica (JavaFX)

Controladores independientes por vista (Login, Bienvenida, Añadir, Modificar, Consulta, Perfil, Página).

Navegación centralizada desde AppController.

Carga de FXML mediante FXMLLoader.

### 🗄️ Persistencia (MongoDB)

Implementada a través de la clase MongoSession y usada por PaginaService:

Inserción de usuarios.

Consulta por nombre o correo.

Gestión de páginas dentro de cada usuario.

Filtros personalizados.

### 📦 Modelo principal

Usuario → contiene datos personales + lista de páginas.

PaginaWeb → nombre, URL, categoría, fecha de actualización.

## 🧩 Funcionalidades destacadas
### ✔️ Añadir páginas

Formulario con:

- Nombre

- URL

- Categoría

- Usuario destinatario

- Fecha automática

### ✔️ Consultar páginas

Tabla filtrada por usuario

Filtro por nombre

Doble clic para abrir la web integrada

### ✔️ Modificar páginas

Edición de categorías y nombre

Validación de permisos

Actualización en tiempo real

### ✔️ Eliminar páginas

Solo permite eliminar si:

La página pertenece al propio usuario, o

El usuario actual es administrador

### ✔️ Abrir páginas Internamente

Al clicar sobre una URL, se abre internamente la WEB.


## 🛠️ Tecnologías utilizadas
### 🔸 Backend / Lógica

Java 17+

MongoDB

MongoDB Java Driver

SHA-256 (hashing)

### 🔸 Frontend de escritorio

JavaFX (FXML, Scene Builder, WebView)

CSS JavaFX

Task + Threading (para evitar bloqueo en consultas)

### 🔸 Organización del proyecto

Patrón MVC simplificado

Controlador principal: AppController

Servicios: PaginaService

## 📂 Estructura del proyecto (resumen)
/app
 ├─ gui
 │   ├─ appController
 │   │    └─ AppController.java
 │   ├─ bienvenida
 │   │    ├─ anhadirController.java
 │   │    ├─ BienvenidaController.java
 │   │    ├─ ConsultaController.java
 │   │    ├─ ModificarController.java
 │   │    └─ PaginaController.java
 │   ├─ login
 │   │    ├─ login.fxml
 │   │    └─ registro.fxml
 │   ├─ modelo
 │   │    ├─ Usuario.java
 │   │    └─ PaginaWeb.java
 │   └─ service
 │        ├─ PaginaService.java
 │        ├─ PaginaWebNotFoundException.java
 │        └─ ExceptionAñadirPaginaAUsuario.java



## 📌 Mejoras futuras

Sistema de roles más avanzado (Admin, Editor, Viewer).

Interfaz más moderna con CSS modular.

Historial de modificaciones.

Exportación de páginas a JSON/CSV.

Integración con APIs externas.

## 🖼️ Vista previa de la app 
<img width="609" height="406" alt="pagweb" src="https://github.com/user-attachments/assets/dea4e658-4d59-4371-bc28-1af7e6ccd477" />
<img width="613" height="408" alt="login" src="https://github.com/user-attachments/assets/79859b3a-6ecb-4316-9590-c8545258c6ec" />
<img width="605" height="405" alt="home" src="https://github.com/user-attachments/assets/54c335b1-40ed-4bcd-b9c7-f733caffeb49" />
<img width="605" height="406" alt="favoritos" src="https://github.com/user-attachments/assets/a2e38440-663b-4935-a331-3abc110d8eae" />
<img width="604" height="403" alt="editar-url" src="https://github.com/user-attachments/assets/156e7deb-e74a-4a59-9228-e563279bfd14" />
<img width="602" height="404" alt="crear-url" src="https://github.com/user-attachments/assets/1f4fd5ad-a5d0-42d5-a9cd-bbd890349a36" />
<img width="601" height="405" alt="perfil" src="https://github.com/user-attachments/assets/cfc23084-9e37-446b-8a3c-c843520eb9dc" />


