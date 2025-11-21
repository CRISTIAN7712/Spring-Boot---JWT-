# Spring Boot JWT Authentication

Proyecto de ejemplo construido con **Spring Boot** que implementa
**autenticación y autorización usando JWT (JSON Web Tokens)**.\
Incluye registro, login, generación de tokens, validación y protección
de endpoints mediante filtros de seguridad.

## 🚀 Tecnologías utilizadas

-   **Java 17+**
-   **Spring Boot**
-   Spring Web
-   Spring Security
-   JWT (io.jsonwebtoken o jjwt)
-   Maven

## 📌 Características principales

-   Registro de usuarios\
-   Inicio de sesión con generación de JWT\
-   Validación de token en cada petición protegida\
-   Configuración de filtros de seguridad personalizados\
-   Roles y autorización por endpoint\
-   Manejo de excepciones\
-   Estructura limpia y separada por capas

## 📂 Estructura del proyecto

    src/
     └── main/
         ├── java/
         │   └── com.example
         │        ├── controller/      
         │        ├── security/        
         │        ├── jwt/             
         │        ├── service/         
         │        └── repository/      
         └── resources/
             ├── application.properties
             └── ...

## 🔑 Endpoints principales

### Auth

Método   Endpoint         Descripción
  -------- ---------------- ------------------------------
POST     /auth/register   Registra un nuevo usuario
POST     /auth/login      Inicia sesión y devuelve JWT

### API protegida

Método   Endpoint     Descripción
  -------- ------------ -------------------
GET      /api/hello   Recurso protegido
GET      /api/admin   Solo ADMIN

## 🛠️ Configuración

### Configurar propiedades JWT

``` properties
jwt.secret=MI_SECRETO_SUPER_SEGURO
jwt.expiration=86400000
```

## ▶️ Ejecución del proyecto

### IDE

Run → SpringBootApplication

### Terminal

``` bash
mvn spring-boot:run
```

## 🔐 Ejemplo de uso del token

### Login

POST → /auth/login

``` json
{
  "username": "test",
  "password": "1234"
}
```

Respuesta:

``` json
{ "token": "eyJhbGciOiJIUzI1NiIsInR..." }
```

### Consumir endpoint protegido

Header:

    Authorization: Bearer <TOKEN>

## 🛡️ Seguridad

-   No almacenar el secreto JWT en el repositorio.
-   Usar HTTPS.
-   Tokens con expiración corta.
-   Rotar claves.

## 📄 Licencia

Libre para uso educativo.

---

## 👨‍⚕️ Autor

Desarrollado por **Ing. Cristian Díaz**

---

<p align="center">
  <img width="300" src="https://i.imgur.com/YYf2LgH.png" alt="Logo del autor">
</p>
