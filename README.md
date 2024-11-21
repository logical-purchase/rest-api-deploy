# Movies REST API 🎬

Una REST API sencilla para la gestión de películas, desarrollada con **Express.js**, validación con **Zod**, y habilitada para solicitudes **CORS**. La API permite realizar operaciones CRUD (Crear, Leer, Actualizar, Eliminar) sobre un conjunto de películas almacenadas en memoria.

El proyecto está desplegado en [Render](https://rest-api-deploy-aw5i.onrender.com/movies).

---

## Tabla de Contenidos
- [Características](#características)
- [Uso](#uso)
- [Endpoints](#endpoints)
- [Dependencias](#dependencias)

---

## Características
- Gestión de películas con operaciones CRUD.
- Validación de datos con **Zod**.
- Configuración personalizada de **CORS** para controlar orígenes permitidos.
- Ejemplo funcional desplegado en Render.

---

## Uso
La API incluye endpoints para gestionar películas. Puedes probarlos con herramientas como **Postman**, **Thunder Client** o con el navegador para métodos GET.

El proyecto incluye un archivo `movies.json` con películas de ejemplo.

---

## Endpoints
### Obtener todas las películas
**GET `/movies`**

**Ejemplo de Respuesta:**
```json
[
  {
    "id": "dcdd0fad-a94c-4810-8acc-5f108d3b18c3",
    "title": "The Shawshank Redemption",
    "year": 1994,
    "director": "Frank Darabont",
    "duration": 142,
    "poster": "https://i.ebayimg.com/images/g/4goAAOSwMyBe7hnQ/s-l1200.webp",
    "genre": ["Drama"],
    "rate": 9.3
  }
]
```

### Obtener una película por ID
**GET `/movies/:id`**

**Ejemplo de Respuesta:**
```json
{
  "id": "dcdd0fad-a94c-4810-8acc-5f108d3b18c3",
  "title": "The Shawshank Redemption",
  "year": 1994,
  "director": "Frank Darabont",
  "duration": 142,
  "poster": "https://i.ebayimg.com/images/g/4goAAOSwMyBe7hnQ/s-l1200.webp",
  "genre": ["Drama"],
  "rate": 9.3
}
```

### Crear una nueva película
**POST `/movies`**

**Cuerpo de la solicitud:**
```json
{
  "title": "Inception",
  "year": 2010,
  "director": "Christopher Nolan",
  "duration": 148,
  "poster": "https://example.com/poster.jpg",
  "genre": ["Action", "Sci-Fi"],
  "rate": 8.8
}
```
**Ejemplo de Respuesta:**
```json
{
  "id": "generated-uuid",
  "title": "Inception",
  "year": 2010,
  "director": "Christopher Nolan",
  "duration": 148,
  "poster": "https://example.com/poster.jpg",
  "genre": ["Action", "Sci-Fi"],
  "rate": 8.8
}
```

### Actualizar una película parcialmente
**PATCH `/movies/:id`**

**Cuerpo de la solicitud:**
```json
{
  "rate": 9.0
}
```
**Ejemplo de Respuesta:**
```json
{
  "id": "dcdd0fad-a94c-4810-8acc-5f108d3b18c3",
  "title": "The Shawshank Redemption",
  "year": 1994,
  "director": "Frank Darabont",
  "duration": 142,
  "poster": "https://i.ebayimg.com/images/g/4goAAOSwMyBe7hnQ/s-l1200.webp",
  "genre": ["Drama"],
  "rate": 9.0
}
```

### Eliminar una película
**DELETE `/movies/:id`**

**Ejemplo de Respuesta:**
```json
{
  "message": "Movie deleted"
}
```

---

## Dependencias
- **express**: Framework para crear la API.
- **cors**: Configuración de políticas de CORS.
- **zod**: Validación y gestión de esquemas de datos.
