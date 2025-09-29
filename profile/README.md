# 📘 Parcial II - Desarrollo de una API RESTful para la gestión de automóviles  

**Carrera:** Analista Universitario en Sistemas  
**Materia:** Programación Lógica Aplicada II  
**Fecha de entrega y exposición:** 02/10/2025  
**Integrantes:**
- Cassataro Ignacio 
- Carrazana Pablo 
- Monayar Facundo

---

## 📌 Enunciado  

Se solicita el desarrollo de una API RESTful que permita realizar las operaciones básicas de **CRUD** (Crear, Leer, Actualizar y Eliminar) sobre una entidad **Automóvil**.  

Cada automóvil debe contener la siguiente información obligatoria:  
- **Id**: Identificador único del automóvil (autoincremental).  
- **Marca**: Marca del automóvil (ej. Toyota, Ford, etc.).  
- **Modelo**: Modelo del automóvil (ej. Corolla, Mustang, etc.).  
- **Color**: Color del automóvil.  
- **Fabricacion**: Año de fabricación (formato YYYY).  
- **NumeroMotor**: Número de motor (único por automóvil).  
- **NumeroChasis**: Número de chasis (único por automóvil).  

---

## ⚙️ Requerimientos funcionales de la API  

### 1. Create (Crear un nuevo automóvil)  
**Objetivo:** Permitir el registro de un nuevo automóvil en el sistema.  

- **Método HTTP:** `POST`  
- **Ruta:** `/api/v1/automovil`  
- **Cuerpo de la solicitud (JSON):**  
```json
{
  "marca": "Toyota",
  "modelo": "Corolla",
  "color": "Blanco"
}
```  
- **Respuesta esperada:** `201 Created` - Objeto del automóvil creado con su id asignado.  

---

### 2. Delete (Eliminar un automóvil por ID)  
**Objetivo:** Eliminar un automóvil existente del sistema utilizando su identificador.  

- **Método HTTP:** `DELETE`  
- **Ruta:** `/api/v1/automovil/{id}`  
- **Parámetro de ruta:** `id` (entero)  
- **Respuesta esperada:** `200 OK` - Confirmación de eliminación o error si el automóvil no existe.  

---

### 3. Update (Actualizar los datos de un automóvil)  
**Objetivo:** Actualizar toda la información de un automóvil existente, identificado por su id.  

- **Método HTTP:** `PUT`  
- **Ruta:** `/api/v1/automovil/{id}`  
- **Parámetro de ruta:** `id` (entero)  
- **Cuerpo de la solicitud (JSON):**  
```json
{
  "color": "Rojo",
  "numeroMotor": "DEF789123"
}
```  
- **Respuesta esperada:** Objeto actualizado o error si el automóvil no existe.  

---

### 4. GetById (Obtener un automóvil por su ID)  
**Objetivo:** Recuperar la información completa de un automóvil específico.  

- **Método HTTP:** `GET`  
- **Ruta:** `/api/v1/automovil/{id}`  
- **Parámetro de ruta:** `id` (entero)  
- **Respuesta esperada:** Objeto del automóvil o error si no se encuentra.  

---

### 5. GetByChasis (Obtener un automóvil por número de chasis)  
**Objetivo:** Consultar la información de un automóvil utilizando el número de chasis.  

- **Método HTTP:** `GET`  
- **Ruta:** `/api/v1/automovil/chasis/{numeroChasis}`  
- **Parámetro de ruta:** `numeroChasis` (string)  
- **Respuesta esperada:** Objeto del automóvil o error si no existe.  

---

### 6. GetAll (Obtener todos los automóviles registrados)  
**Objetivo:** Listar todos los automóviles registrados en el sistema.  

- **Método HTTP:** `GET`  
- **Ruta:** `/api/v1/automovil`  
- **Respuesta esperada:** Lista de objetos de automóviles.  

---

## 🗄️ Base de Datos  
Se requiere la conexión y creación de una **base de datos en SQL Server Local** utilizando **Entity Framework con Migraciones**.  

---

## 📑 Resumen de Endpoints  
1. `POST /api/v1/automovil` → Crear un nuevo automóvil.  
2. `DELETE /api/v1/automovil/{id}` → Eliminar un automóvil por ID.  
3. `PUT /api/v1/automovil/{id}` → Actualizar los datos de un automóvil.  
4. `GET /api/v1/automovil/{id}` → Obtener un automóvil por su ID.  
5. `GET /api/v1/automovil/chasis/{numeroChasis}` → Obtener un automóvil por número de chasis.  
6. `GET /api/v1/automovil` → Listar todos los automóviles registrados.  
