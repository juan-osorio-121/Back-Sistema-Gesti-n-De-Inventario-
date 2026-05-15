# Proyecto Aula Backend

API REST academica en Java con Spring Boot para gestionar usuarios y productos.

## Estructura de paquetes

```text
com.troncosport.aula
  config
  controller
  service
  repository
  model
  dto
  exception
```

## Responsabilidad de cada paquete

- `config`: configuracion de CORS para conectar el frontend con el backend.
- `controller`: recibe peticiones HTTP y llama a los servicios.
- `service`: contiene reglas de negocio y validaciones.
- `repository`: guarda datos en memoria con `Map<Long, ...>`.
- `model`: clases internas `Usuario` y `Producto`.
- `dto`: clases de entrada y salida para la API.
- `exception`: excepciones personalizadas y manejador global de errores.

## Endpoints

### Health

- `GET /health`

### Usuarios

- `GET /api/usuarios`
- `GET /api/usuarios/{id}`
- `POST /api/usuarios`
- `PUT /api/usuarios/{id}`
- `DELETE /api/usuarios/{id}`

### Productos

- `GET /api/productos`
- `GET /api/productos/{id}`
- `POST /api/productos`
- `PUT /api/productos/{id}`
- `DELETE /api/productos/{id}`

## JSON para Postman

### Crear usuario

```json
{
  "nombre": "Laura Martinez",
  "correo": "laura@troncosport.com",
  "edad": 22
}
```

### Actualizar usuario

```json
{
  "nombre": "Laura Martinez Actualizada",
  "correo": "laura.actualizada@troncosport.com",
  "edad": 23
}
```

### Crear producto

```json
{
  "nombre": "Camiseta de compresion Elite",
  "precio": 95000,
  "stock": 18
}
```

### Actualizar producto

```json
{
  "nombre": "Camiseta de compresion Elite Pro",
  "precio": 99000,
  "stock": 12
}
```

## Ejemplos de errores

### Error 400

```json
{
  "nombre": "",
  "precio": 0,
  "stock": -1
}
```

### Error 404

Consultar un id que no exista:

```text
GET /api/productos/999
```

## Como ejecutar

Desde la carpeta `backend`:

```bash
mvn spring-boot:run
```

Si Maven no esta en el PATH, en este computador tambien puedes ejecutar:

```powershell
.\run-backend.ps1
```

El backend queda disponible en:

```text
http://localhost:8080
```

El frontend consume:

```text
http://localhost:8080/api/productos
http://localhost:8080/api/usuarios
```
