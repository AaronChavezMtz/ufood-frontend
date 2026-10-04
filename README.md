# UFood — Marketplace móvil de alimentos

<p align="center">
  <img src="./assets/icon.png" width="120" alt="UFood Logo">
</p>

<p align="center">
  Aplicación móvil desarrollada con React Native y Expo para conectar estudiantes universitarios con vendedores de alimentos dentro y cerca del entorno universitario.
</p>

---

## Sobre el proyecto

**UFood** es una aplicación móvil desarrollada como proyecto académico en equipo durante 2025.

El proyecto propone un marketplace orientado al entorno universitario, donde los estudiantes pueden descubrir productos y platillos ofrecidos por vendedores locales, consultar su información y establecer contacto directamente con ellos.

La aplicación fue desarrollada para Android utilizando **React Native y Expo**, con una arquitectura de frontend modular preparada para consumir servicios REST proporcionados por un backend independiente.

El sistema contempla funcionalidades para usuarios, vendedores y administración, incluyendo autenticación, publicación y gestión de productos, búsqueda, filtrado, interacción con productos y contacto mediante WhatsApp.

> **Nota:** El backend utilizado durante el desarrollo fue desplegado mediante servicios gratuitos. Actualmente esos servicios ya no se encuentran disponibles, por lo que algunas funcionalidades que dependen de la API no están operativas. La aplicación y el código del frontend corresponden a la versión desarrollada durante el proyecto académico.

---

## Diseño y prototipo

El diseño de la aplicación fue realizado previamente al desarrollo de las interfaces.

### Figma

**Prototipo y diseño de UFood:**
[Ver prototipo en Figma](https://www.figma.com/proto/RSHdXW03TWzHwBnlzr1H6I/Proyecto-Unifood?node-id=203-91&t=YW8KWwt7WpPUUCtV-1&scaling=scale-down&content-scaling=fixed&page-id=92%3A2089)

### Landing Page

**Landing page del proyecto:**
https://matrark.github.io/ufood-landing/

La landing presenta el concepto general de UFood y sirve como complemento visual del proyecto.

---

## Mi participación

Mi participación en UFood estuvo enfocada principalmente en el **desarrollo del frontend de la aplicación móvil**.

Entre las actividades realizadas se encuentran:

* Desarrollo y modificación de interfaces con **React Native**.
* Implementación de pantallas y componentes de la aplicación.
* Desarrollo de la pantalla principal.
* Implementación de interfaces para consulta y gestión de productos.
* Desarrollo y modificación del formulario para publicar productos.
* Implementación de validaciones de formularios.
* Implementación de búsqueda y filtrado de productos.
* Integración del contacto con vendedores mediante WhatsApp.
* Implementación de interacción y votación sobre productos.
* Manejo de sesión y almacenamiento local.
* Integración del frontend con los servicios REST del backend.
* Implementación de monitoreo mediante **Datadog**.
* Configuración de la aplicación para Android.
* Corrección y mejoras de interfaz y experiencia de usuario.
* Preparación del proyecto para su compilación y distribución mediante Expo/EAS.

La documentación técnica describe el frontend como una aplicación React Native + Expo organizada mediante pantallas, navegación, componentes, hooks, estilos y recursos estáticos.

---

## Funcionalidades

### Usuarios

* Registro e inicio de sesión.
* Autenticación mediante JWT.
* Persistencia de sesión.
* Edición del perfil.
* Eliminación de cuenta.
* Consulta de productos.
* Publicación de productos.
* Edición y gestión de productos.
* Selección de imágenes desde el dispositivo.
* Búsqueda de productos.
* Filtrado por categorías.
* Ordenamiento de productos.
* Interacción y votación de productos.
* Contacto con vendedores mediante WhatsApp.
* Cierre de sesión.

### Gestión de productos

* Creación de productos.
* Edición de productos.
* Eliminación de productos.
* Consulta de productos.
* Consulta de productos asociados a un vendedor.
* Validación de información.
* Selección de imágenes mediante cámara o galería.
* Actualización de productos.
* Búsqueda y filtrado.

### Administración

El proyecto contempla interfaces administrativas para:

* Dashboard administrativo.
* Consulta de estadísticas.
* Gestión de usuarios.
* Búsqueda de usuarios.
* Activación y desactivación de usuarios.
* Consulta y gestión de productos.
* Eliminación de productos.
* Diferenciación entre usuarios y administradores.

### Contacto mediante WhatsApp

Los usuarios pueden iniciar contacto con el vendedor de un producto directamente mediante WhatsApp.

Esta funcionalidad utiliza la información del vendedor disponible en el sistema y permite establecer la comunicación fuera de la aplicación.

---

## Monitoreo con Datadog

Se integró **Datadog** en el frontend para registrar información relacionada con el uso y funcionamiento de la aplicación.

Entre los eventos contemplados se encuentran:

```text
screen_view
screen_duration
app_started
search_performed
product_voted
whatsapp_contact_initiated
products_refreshed
product_interaction
http_request
user_logged_in
user_logged_out
```

El sistema permite recopilar información relacionada con:

* Navegación entre pantallas.
* Tiempo de permanencia.
* Búsquedas.
* Interacciones con productos.
* Votos.
* Contactos mediante WhatsApp.
* Errores.
* Rendimiento de peticiones HTTP.

La documentación indica que el tracker fue diseñado para funcionar dentro de Expo Go y registrar eventos de navegación, rendimiento y comportamiento.

---

## Tecnologías utilizadas

### Frontend

* **React Native**
* **Expo**
* **JavaScript**
* **React Hooks**
* **React Navigation**
* **NativeWind**
* **Axios**
* **AsyncStorage**
* **Expo Image Picker**
* **Expo StatusBar**

La documentación técnica identifica React Native/Expo como la base de la aplicación Android y React Navigation, Axios/Fetch, AsyncStorage y Expo Image Picker como dependencias relevantes del frontend.

### Backend

El frontend consume una API REST desarrollada independientemente del cliente móvil.

* **.NET**
* **Microservicios**
* **MongoDB**
* **APIs REST**
* **JWT**
* **Docker**
* **Render**

La arquitectura general documentada sigue el flujo:

```text
Aplicación Android
       │
       ▼
API / Microservicios .NET
       │
       ▼
MongoDB
```

> El desarrollo del backend no forma parte de mi contribución principal en este repositorio.

### Herramientas

* **Git**
* **GitHub**
* **Figma**
* **Datadog**
* **Expo Go**
* **EAS Build**
* **Google Play Console**

---

## Arquitectura del frontend

El frontend utiliza una estructura modular basada en una adaptación del patrón **MVC**, separando la presentación de la lógica de interacción y manejo de datos.

```text
                    ┌─────────────────────┐
                    │        Views        │
                    │    React Native     │
                    │      Screens        │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │   Control / Logic   │
                    │   Hooks / States    │
                    │    Validations      │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │      Services       │
                    │   API / Storage     │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │      REST API       │
                    │       .NET          │
                    └─────────────────────┘
```

La documentación describe esta separación mediante vistas, modelos y lógica/control basada principalmente en hooks y manejo de estados.

---

## Estructura principal

La estructura del frontend está organizada alrededor de pantallas, servicios, modelos, hooks, navegación y lógica de presentación.

```text
UFOOD/
│
├── src/
│   ├── config/
│   ├── hooks/
│   ├── models/
│   ├── services/
│   ├── utils/
│   ├── viewmodels/
│   ├── views/
│   └── navigation/
│
├── assets/
├── App.js
├── app.json
├── package.json
└── ARCHITECTURE.md
```

Entre los módulos principales se encuentran:

```text
views/
├── LoginScreen
├── RegisterScreen
├── HomeScreen
├── ProductsListScreen
├── ProductFormScreen
├── ProfileScreen
├── AdminHomeScreen
├── AdminProductsScreen
├── AdminProductDetailScreen
└── AdminUsersScreen
```

---

## Autenticación

El frontend implementa un flujo de autenticación basado en JWT proporcionado por el backend.

Incluye:

* Registro.
* Inicio de sesión.
* Persistencia de sesión.
* Almacenamiento local del token.
* Interceptores HTTP.
* Control de expiración de sesión.
* Cierre de sesión.
* Validación de credenciales.
* Manejo de errores.
* Control de acceso a funcionalidades administrativas.

---

## Gestión de imágenes

La aplicación utiliza **Expo Image Picker** para seleccionar imágenes desde el dispositivo.

El flujo principal es:

```text
Usuario
   │
   ├── Cámara
   │
   └── Galería
        │
        ▼
  Selección de imagen
        │
        ▼
Formulario de producto
        │
        ▼
      API
```

Esta funcionalidad está principalmente relacionada con la publicación y administración de productos.

---

## Búsqueda y filtrado

La pantalla principal permite consultar los productos disponibles mediante diferentes interacciones.

Se implementaron:

* Búsqueda por texto.
* Búsqueda por nombre.
* Búsqueda por categoría.
* Búsqueda por descripción.
* Búsqueda por precio.
* Filtrado por categoría.
* Ordenamiento por precio.
* Ordenamiento por nombre.
* Ordenamiento por fecha.
* Actualización de resultados.

---

## UI / UX

La interfaz fue desarrollada buscando mantener una experiencia sencilla y orientada a las funciones principales del marketplace.

Entre las consideraciones documentadas se encuentran:

* Diseño limpio.
* Colores consistentes.
* Botones accesibles.
* Interfaces enfocadas en la funcionalidad.
* Adaptación a diferentes dispositivos Android.
* Separación de componentes y lógica.
* Validaciones para mejorar la experiencia de usuario.

La documentación señala específicamente el uso consistente de colores, botones grandes y accesibles y un diseño enfocado en funcionalidad.

---

## Instalación

### Requisitos

* Node.js
* npm
* Expo
* Android Studio, en caso de desarrollo/emulación Android.

### Clonar el repositorio

```bash
git clone https://github.com/AaronChavezMtz/ufood-frontend.git

cd ufood-frontend
```

### Instalar dependencias

```bash
npm install
```

### Configuración de la API

Las rutas utilizadas para comunicarse con el backend se encuentran centralizadas dentro de la configuración del proyecto.

```text
src/config/app.config.js
```

Para utilizar actualmente todas las funcionalidades de la aplicación sería necesario contar nuevamente con una instancia activa del backend y actualizar los endpoints correspondientes.

### Ejecutar con Expo

```bash
npm start
```

También pueden utilizarse los comandos configurados para las diferentes plataformas:

```bash
npm run android
```

```bash
npm run ios
```

```bash
npm run web
```

---

## Distribución

El proyecto fue preparado para Android y se utilizó **Expo/EAS Build** para generar una versión distribuible de la aplicación.

Durante el desarrollo se utilizó Expo Go y posteriormente EAS Build para generar el paquete Android.

El proyecto llegó a ser distribuido mediante **Google Play Console** como parte del proceso académico. La documentación registra el proceso de compilación con EAS y la creación de una prueba cerrada para dispositivos físicos.

---

## Estado actual del proyecto

**Estado: Proyecto académico finalizado / Backend no disponible actualmente**

La aplicación fue desarrollada y se generó una versión instalable para Android.

Sin embargo, actualmente los servicios backend utilizados durante el desarrollo ya no se encuentran activos debido a que fueron desplegados utilizando infraestructura gratuita.

Por esta razón:

* La aplicación puede instalarse.
* La interfaz y navegación del frontend están disponibles.
* El código fuente del frontend está disponible en este repositorio.
* El prototipo de Figma continúa disponible.
* La landing page continúa disponible.
* Las funcionalidades que requieren comunicación con la API actualmente no pueden utilizarse correctamente.

Para volver a ejecutar el sistema completo sería necesario desplegar nuevamente los microservicios y la base de datos y actualizar los endpoints utilizados por la aplicación.

---

## Roadmap original

Durante la documentación del proyecto se contemplaron futuras funcionalidades como:

* Sistema de pedidos dentro de la aplicación.
* Chat interno entre clientes y vendedores.
* Integración de pagos en línea.
* Historial de compras y ventas.
* Panel de estadísticas para vendedores.
* Seguimiento de entregas mediante GPS.
* Notificaciones push.
* Integración de herramientas adicionales de monitoreo.
* Posible integración de IA para validación de imágenes.

Estas funcionalidades forman parte del roadmap planteado durante el proyecto y no deben interpretarse como funcionalidades actualmente implementadas.

---

## Contexto académico

UFood fue desarrollado como un proyecto académico colaborativo durante 2025.

El proyecto permitió aplicar conocimientos relacionados con:

* Desarrollo de aplicaciones móviles.
* React Native.
* Expo.
* Arquitectura de software.
* Consumo de APIs REST.
* Autenticación.
* Manejo de estados.
* Persistencia local.
* Diseño de interfaces.
* UX/UI.
* Integración con servicios externos.
* Monitoreo de aplicaciones.
* Git y GitHub.
* Despliegue de aplicaciones móviles.

La documentación técnica del proyecto comprende arquitectura, frontend, backend, despliegue, mantenimiento y monitoreo.

---

## Equipo

Proyecto desarrollado colaborativamente.

### Frontend

**Aaron Yosef Chávez Martínez**

Participación principal en:

* Desarrollo del frontend móvil.
* Interfaces y componentes.
* Pantallas de usuario.
* Gestión de productos.
* Validaciones.
* Búsqueda y filtrado.
* Integración con WhatsApp.
* Manejo de sesión.
* Integración con APIs.
* Monitoreo con Datadog.
* Configuración y distribución de la aplicación Android.

---

## Documentación

La documentación técnica completa del proyecto incluye información sobre:

* Arquitectura.
* Frontend.
* Backend.
* Base de datos.
* Despliegue.
* Mantenimiento.
* Monitoreo con Datadog.
* Convenciones del proyecto.
* Flujos de usuario.

---

## Licencia

Proyecto desarrollado con fines académicos.
