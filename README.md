# 🎬 Movies API - Spring Boot 3 + PostgreSQL + Docker

API REST para la gestión de películas.  
Implementada en **Spring Boot 3.5.5**, con **PostgreSQL** como base de datos y documentada con **Swagger UI**.

---

## 🚀 Requisitos previos

Antes de ejecutar el proyecto asegúrate de tener instalado:

- [Java 17+](https://adoptium.net/)  
- [Gradle](https://gradle.org/) (opcional, ya que se incluye el wrapper `./gradlew`)  
- [Docker](https://docs.docker.com/get-docker/) y [Docker Compose](https://docs.docker.com/compose/)  

---

## 📂 Estructura del proyecto
```bash
movies-api/
├── src/                 # Código fuente principal
│   ├── main/            # Código de la aplicación
│   │   ├── java/        # Paquetes Java (controladores, servicios, repositorios, entidades)
│   │   └── resources/   # application.properties, data.sql, schema.sql, etc.
│   └── test/            # Pruebas unitarias y de integración
│
├── build.gradle         # Configuración de dependencias Gradle
├── settings.gradle      # Configuración de Gradle
├── Dockerfile           # Imagen Docker para la aplicación
├── docker-compose.yml   # Orquestación de contenedores
└── README.md            # Documentación del proyecto
```
---

## ⚙️ Configuración

El proyecto usa **Docker Compose** para levantar los servicios:

- **movies-api** → Aplicación Spring Boot (puerto `8081`)  
- **postgres-db** → Base de datos PostgreSQL (puerto `5432`)

## ▶️ Levantar la aplicación

1. Compilar el proyecto

- ./gradlew clean build

2. Construir las imágenes Docker

- docker-compose build

3. Levantar los servicios

- docker-compose up

📌 Esto levantará:

- API en: http://localhost:8081

- PostgreSQL en: localhost:5432

---

## 📖 Endpoints principales

- GET /movie?id={id} → Consulta una película por ID

- GET /movies → Lista todas las películas

- POST /movie → Crea una nueva película

## 📚 Documentación Swagger

Una vez levantado el proyecto:

- Swagger UI: 👉 http://localhost:8081/swagger-ui/index.html

- OpenAPI JSON: 👉 http://localhost:8081/v3/api-docs

---

## 🛠️ Pruebas Unitarias

Ejecutar las pruebas con:

 - ./gradlew test

 Usa JUnit 5, Mockito y H2 Database para pruebas en memoria.

---

 ## 🗑️ Detener servicios

 - docker-compose down

