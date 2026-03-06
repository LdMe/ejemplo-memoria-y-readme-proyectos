

# ⚡ Evaluat.io

> **Plataforma SaaS para la gestión de evaluaciones cruzadas (peer-review) basada en rúbricas dinámicas.**

[Ver Demo Desplegada](https://www.google.com/search?q=https://evaluatio.vercel.app) · [Reportar Bug](https://www.google.com/search?q=https://github.com/usuario/evaluatio/issues) · [Leer Memoria Técnica](https://www.google.com/search?q=./MEMORIA.md)

---

## 📸 Screenshots

| Dashboard Profesor | Vista Evaluación Mobile |
| --- | --- |
|  |  |

---

## 🚀 Características Principales

* **Rúbricas Dinámicas:** Creación de criterios de evaluación con pesos personalizados (JSONB).
* **Asignación Inteligente:** Algoritmo *Fisher-Yates* para distribuir pares aleatoriamente evitando auto-evaluaciones.
* **Cálculo Automático:** Nota final ponderada (60% Profesor + 40% Peers).
* **Seguridad:** Autenticación JWT y protección de rutas por roles (RBAC).

---

## 🛠️ Stack Tecnológico

* **Cliente:** React, TailwindCSS, Vite.
* **Servidor:** Node.js, Express.
* **Base de Datos:** PostgreSQL (Supabase/Railway).
* **Testing:** Vitest + Supertest.

---

## ⚙️ Instalación y Configuración Local

Sigue estos pasos para levantar el proyecto en tu entorno local.

### 1. Prerrequisitos

Asegúrate de tener instalado:

* Node.js (v18 o superior)
* PostgreSQL (o una instancia en Docker)
* Git

### 2. Clonar el repositorio

```bash
git clone https://github.com/usuario/evaluatio.git
cd evaluatio

```

### 3. Configuración del Backend

```bash
cd server
npm install

```

Crea un archivo `.env` en la carpeta `server` basado en el ejemplo:

```env
PORT=3000
DATABASE_URL="postgres://user:password@localhost:5432/evaluatio_db"
JWT_SECRET="tu_secreto_super_seguro"
CORS_ORIGIN="http://localhost:5173"

```

Ejecuta las migraciones para crear las tablas:

```bash
npm run migrate
# Opcional: Poblar con datos de prueba
npm run seed

```

Levanta el servidor:

```bash
npm run dev
# El servidor correrá en http://localhost:3000

```

### 4. Configuración del Frontend

Abre una nueva terminal:

```bash
cd client
npm install

```

Crea un archivo `.env` en la carpeta `client`:

```env
VITE_API_URL="http://localhost:3000/api"

```

Levanta el cliente:

```bash
npm run dev
# La app correrá en http://localhost:5173

```

---

## 🧪 Ejecutar Tests

Para validar que la lógica de asignación y cálculo de notas funciona correctamente:

```bash
# Tests de Backend
cd server
npm run test

# Tests de Frontend
cd client
npm run test

```

---

## 📂 Estructura del Proyecto

```text
evaluatio/
├── client/              # Single Page Application (React)
│   ├── src/
│   │   ├── components/  # Componentes reutilizables (Botones, Inputs)
│   │   ├── pages/       # Vistas principales (Dashboard, Login)
│   │   ├── context/     # Estado global (AuthContext)
│   │   └── hooks/       # Custom Hooks
├── server/              # API REST (Express)
│   ├── src/
│   │   ├── controllers/ # Lógica de los endpoints
│   │   ├── models/      # Modelos de Base de Datos
│   │   ├── routes/      # Definición de rutas
│   │   └── services/    # Lógica de negocio compleja (Calculadora, Asignador)
├── MEMORIA.md           # Documentación detallada del proyecto
└── README.md            # Este archivo

```

---

## ✒️ Autores

* **Tu Nombre** - *Desarrollo Full Stack* - [GitHub Profile](https://www.google.com/search?q=https://github.com/tu-usuario)

---

## 📄 Licencia

Este proyecto está bajo la Licencia MIT - mira el archivo [LICENSE.md](https://www.google.com/search?q=LICENSE.md) para detalles.

---

###  ¿Cuál es la diferencia con la Memoria?



| Característica | **README.md** 🛠️ | **MEMORIA.md** 🧠 |
| --- | --- | --- |
| **Objetivo** | Que el código **funcione**. | Que el proyecto se **entienda**. |
| **Audiencia** | Desarrolladores que quieren probarlo. | Jefes técnicos, profesores, reclutadores. |
| **Contenido** | Comandos, instalación, configuración. | Por qués, arquitectura, decisiones, retos. |
| **Lectura** | Rápida (escaneo visual). | Profunda (lectura reflexiva). |
| **Diagramas** | Screenshots de la App. | UML, Entidad-Relación, Gantt. |

El README vende el **producto**, la Memoria vende al **ingeniero**.