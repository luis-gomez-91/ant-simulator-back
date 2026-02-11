cat <<EOF > README.md
# 🚗 API REST – Banco de Preguntas ANT Ecuador

![FastAPI](https://img.shields.io/badge/FastAPI-005571?style=for-the-badge&logo=fastapi)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white)
![Railway](https://img.shields.io/badge/Railway-0B0D0E?style=for-the-badge&logo=railway)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)

Backend robusto desarrollado con **FastAPI** para gestionar el banco de preguntas oficial de la **Agencia Nacional de Tránsito (ANT) del Ecuador**. Diseñado para servir como motor de aplicaciones de práctica para el examen teórico de conducción.

---

## 🌟 Características

* ✅ **API RESTful:** Documentación interactiva automática con Swagger y ReDoc.
* 📅 **Versionamiento por Año:** Estructura preparada para los cambios periódicos del banco de preguntas.
* 🪪 **Categorización:** Organización por tipo de licencia (A, B, C, D, E, F, G).
* 🖼️ **Gestión de Multimedia:** Integración con Cloudinary para el manejo de imágenes de señales de tránsito.
* 🚀 **Despliegue Continuo:** Configurado para Railway con base de datos PostgreSQL.
* 🛠️ **Migraciones:** Gestión de base de datos mediante Alembic.

---

## 📂 Estructura del Proyecto

\`\`\`text
ant-simulator-back/
├── alembic/            # Migraciones de base de datos
├── routers/            # Endpoints divididos por recursos
│   ├── licences.py     # Gestión de tipos de licencia
│   ├── questions.py    # CRUD de preguntas
│   └── versions.py     # Gestión de versiones/años
├── database.py         # Configuración de SQLAlchemy
├── main.py             # Punto de entrada de la aplicación
├── models.py           # Modelos de base de datos (SQLAlchemy)
├── schemas.py          # Esquemas de validación (Pydantic)
├── requirements.txt    # Dependencias del proyecto
└── Procfile            # Configuración para despliegue en Railway
\`\`\`

---

## 🛠️ Instalación y Configuración

### 1. Clonar el repositorio
\`\`\`bash
git clone https://github.com/luis-gomez-91/ant-simulator-back
cd ant-simulator-back
\`\`\`

### 2. Entorno Virtual
\`\`\`bash
python -m venv venv
# Linux/Mac
source venv/bin/activate  
# Windows
venv\Scripts\activate
\`\`\`

### 3. Instalar Dependencias
\`\`\`bash
pip install -r requirements.txt
\`\`\`

### 4. Variables de Entorno
Crea un archivo \`.env\` en la raíz del proyecto con la siguiente estructura:
\`\`\`env
DATABASE_URL=postgresql://usuario:password@localhost/nombre_db
CLOUDINARY_CLOUD_NAME='tu_cloud_name'
CLOUDINARY_API_KEY='tu_api_key'
CLOUDINARY_API_SECRET='tu_api_secret'
\`\`\`

---

## 🚀 Ejecución

Para iniciar el servidor de desarrollo:
\`\`\`bash
uvicorn main:app --reload
\`\`\`
La API estará disponible en \`http://localhost:8000\`.

* **Documentación Interactiva (Swagger):** [http://localhost:8000/docs](http://localhost:8000/docs)
* **Documentación Alternativa (ReDoc):** [http://localhost:8000/redoc](http://localhost:8000/redoc)

---

## 🌐 Endpoints Principales (Ejemplos)

| Método | Endpoint | Descripción |
| :--- | :--- | :--- |
| \`GET\` | \`/licences\` | Obtiene todos los tipos de licencia. |
| \`GET\` | \`/questions/{licence_id}\` | Obtiene preguntas filtradas por licencia. |
| \`GET\` | \`/versions\` | Lista los años disponibles del banco de preguntas. |
| \`POST\` | \`/questions\` | Registra una nueva pregunta (Admin). |

---

## ☁️ Despliegue en Producción

El proyecto está configurado para **Railway**. Puedes acceder a la versión en vivo aquí:
🔗 [ANT Simulator API - Producción](https://ant-simulator-back-production.up.railway.app/docs)

---

## 👤 Autor

**Luis Gómez**
* GitHub: [@luis-gomez-91](https://github.com/luis-gomez-91)