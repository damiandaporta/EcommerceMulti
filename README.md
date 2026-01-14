🛒 Ecommerce Platform – .NET 8 + React

Proyecto E-commerce Fullstack desarrollado con .NET 8 para el Backend y React + TypeScript para el Frontend, diseñado con un enfoque profesional para demostrar seniority, buenas prácticas, arquitectura limpia y estándares utilizados en entornos laborales reales.

El sistema permite la gestión de usuarios con roles, publicación de productos por vendedores y compra de productos por clientes.

🎯 Objetivo del proyecto

El objetivo principal es demostrar:

* Diseño de arquitectura escalable y mantenible
* Separación de responsabilidades
* Buen uso de Entity Framework Core
* Autenticación y autorización con JWT
* Manejo de roles (Admin / Seller / Customer)
* Integración Frontend–Backend
* Commits claros y profesionales
* Testing unitario

Este proyecto no es un tutorial, sino una simulación de un desarrollo real de producto.

🧱 Arquitectura General

El proyecto está dividido en dos grandes partes:

ecommerce-backend
ecommerce-frontend

Cada una sigue principios y patrones ampliamente utilizados en la industria.

⚙️ Backend – .NET 8

🏗️ Arquitectura

Se implementa una Clean Architecture simplificada:

src
 ├── Ecommerce.Api
 ├── Ecommerce.Application
 ├── Ecommerce.Domain
 ├── Ecommerce.Infrastructure
 └── Ecommerce.Tests

📦 Capas

🔹 Domain

* Entidades de negocio
* Enums y Value Objects
* Reglas de dominio

Ejemplos:

* User
* Product
* Order

🔹 Application

* Casos de uso (Use Cases)
* DTOs
* Interfaces (Repositorios, servicios)

Aquí vive la lógica de aplicación, sin dependencias externas.

🔹 Infrastructure

* Entity Framework Core
* Configuraciones Fluent API
* Implementaciones de repositorios
* Autenticación JWT

Esta capa es la única que conoce detalles técnicos.

🔹 Api

* Controllers REST
* Middlewares
* Manejo global de errores
* Swagger

Los controllers son finos y delegan la lógica a Application.

🔹 Tests

* Tests unitarios con xUnit y Moq
* Pruebas sobre casos de uso

No se testean controllers, sino lógica de negocio.

🔐 Seguridad

* Autenticación basada en JWT
* Claims con roles
* Autorización mediante atributos

Ejemplo:

```
[Authorize(Roles = "Seller")]
```

---

🗄️ Persistencia

* Entity Framework Core
* Fluent API
* Migraciones
* Queries optimizadas (`AsNoTracking` en lecturas)

🌐 Frontend – React + TypeScript

🏗️ Estructura

El frontend sigue una organización modular:


src
 ├── api/
 ├── auth/
 ├── components/
 ├── hooks/
 ├── pages/
 ├── router/
 ├── store/
 ├── types/
 ├── utils/

Evita componentes monolíticos y promueve escalabilidad.

🔌 Comunicación con Backend

* Axios centralizado
* Interceptor para JWT
* Variables de entorno

```
VITE_API_URL=https://localhost:5001/api
```

🔐 Autenticación y Roles

* Context API para manejo de sesión
* Rutas protegidas por rol

Ejemplo:

```
<ProtectedRoute roles={["Seller"]}>
```
📄 Funcionalidades principales

* Login y Logout
* Listado de productos
* Creación de productos (Seller)
* Protección de rutas
* Manejo de errores y estados

🧪 Testing

* Backend: xUnit + Moq
* Tests enfocados en casos de uso
* Código preparado para escalar a tests de integración

📝 Convención de Commits

Se utiliza una convención basada en Conventional Commits:

```
feat(scope): description
fix(scope): description
chore(scope): description
refactor(scope): description
test(scope): description
```

Ejemplo:

```
feat(products): add product creation use case
```

Esto permite:

* Historial claro
* Revisión sencilla
* Trabajo en equipo

🚀 Estado del proyecto

Proyecto en desarrollo activo, pensado como **base sólida** para:

* Escalar funcionalidades
* Agregar pagos
* Implementar notificaciones
* Dockerización
* CI/CD

👤 Autor

Desarrollado por **Damián Daporta**

* .NET Backend Developer
* React Frontend Developer
* Enfoque en arquitectura, calidad y buenas prácticas

📌 Nota final

Este proyecto fue construido con mentalidad de **producto real**, priorizando:

* Claridad
* Mantenibilidad
* Escalabilidad

No busca ser un ejemplo académico, sino una demostración práctica de experiencia profesional.
