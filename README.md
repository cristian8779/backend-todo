# 📝 Todo App — Backend con Node.js, MongoDB y Socket.IO

Una API RESTful para gestionar tareas con autenticación por JWT y actualizaciones en tiempo real mediante Socket.IO. Ideal para usar con un frontend en React, Vue u otra tecnología.

---

## 🚀 Características principales

✨ Registro e inicio de sesión con JWT  
🛡️ CRUD completo de tareas personales  
👤 Asociación de tareas a usuarios autenticados  
🎨 Personalización visual (color, fuente, estilo)  
📡 WebSockets con Socket.IO (eventos en tiempo real)  
🛠️ Base de datos MongoDB con Mongoose  
🔐 API protegida con middleware de autenticación

---

## ⚙️ Tecnologías utilizadas

- 🚀 Node.js + Express
- 🍃 MongoDB + Mongoose
- 🔑 JSON Web Tokens (JWT)
- 🔒 bcryptjs (hasheo de contraseñas)
- 🧪 dotenv
- 🌐 cors
- 📡 Socket.IO

---

## 📦 Instalación

1. Clona el repositorio:

```bash
git clone https://github.com/tu-usuario/todo-app.git
cd todo-app
```
2 Instala las dependencias:
```bash
npm install
```
3 Crea un archivo .env en la raíz del proyecto:
```bash
PORT=5000
MONGO_URI=mongodb://localhost:27017/todoapp
JWT_SECRET=clave_secreta
```

▶️ Uso
Inicia el servidor local:
```bash
npm start
```
📍 El servidor estará disponible en: http://localhost:5000

## 🔐 Rutas de autenticación

| Método | Ruta                  | Descripción                              |
|--------|-----------------------|------------------------------------------|
| 📨 POST | `/api/users/register` | Registro de usuario                      |
| 🔓 POST | `/api/users/login`    | Inicio de sesión (devuelve token JWT)   |

## ✅ Rutas de tareas (requieren JWT)

### 🔑 Autenticación

Todas estas rutas requieren enviar el token JWT en el header HTTP:


| Método     | Ruta              | Descripción                        |
|------------|-------------------|------------------------------------|
| 📥 GET     | `/api/tasks`      | Obtener todas las tareas del usuario autenticado |
| ➕ POST    | `/api/tasks`      | Crear una nueva tarea              |
| ♻️ PUT     | `/api/tasks/:id`  | Actualizar una tarea existente     |
| ❌ DELETE  | `/api/tasks/:id`  | Eliminar una tarea                 |

## 📄 Ejemplo de tarea (POST)

Cuando creas una nueva tarea, puedes enviar un JSON con los siguientes campos:

```json
{
  "title": "Hacer ejercicios",
  "description": "Ir al gimnasio a las 7 PM",
  "color": "#ffcc00",
  "fontSize": "16px",
  "fontWeight": "bold",
  "fontStyle": "italic",
  "priority": "alta",
  "dueDate": "2025-07-15T23:59:00.000Z"
}
```
## 📡 Eventos en tiempo real (Socket.IO)

El servidor emite eventos en tiempo real usando **Socket.IO** para que el frontend se mantenga sincronizado automáticamente cuando ocurren cambios en las tareas.

Puedes escuchar estos eventos desde el cliente (por ejemplo, en React o Vue) para actualizar la lista sin recargar la página.

| Evento          | Descripción                              |
|------------------|------------------------------------------|
| 📤 `taskCreated`  | Emitido cuando se crea una nueva tarea    |
| 🔄 `taskUpdated`  | Emitido cuando una tarea es actualizada  |
| 🗑️ `taskDeleted`  | Emitido cuando una tarea es eliminada     |

🧠 **Importante:** El evento `taskDeleted` solo envía el ID de la tarea eliminada para que puedas quitarla del frontend fácilmente.

## 📄 Licencia

Este proyecto está bajo la licencia ISC (puedes cambiarla a MIT si prefieres).

---

## 💡 Ideas futuras

📧 Verificación de email o recuperación de contraseña  
🔍 Filtros y búsqueda de tareas  
🏷️ Etiquetas o categorías  
🗃️ Historial o papelera de tareas eliminadas  
🖥️ Frontend en React o Vue  

---

## 🤝 Contribuciones

Las contribuciones son bienvenidas. Haz un fork del repo, crea una rama nueva y envía tu PR. ¡Gracias por mejorar este proyecto! 🙌


---

<p align="center">
  Desarrollado por <a href="https://github.com/cristian8779" target="_blank">cristian8779</a>
</p>

