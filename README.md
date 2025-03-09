🚀 FastAPI + MongoDB + OpenAI + MySQL + Gatsby + Nginx - Kubernetes CI/CD

📌 Descripción

Este proyecto automatiza el despliegue de una aplicación desarrollada con FastAPI, MongoDB, OpenAI, MySQL, Gatsby y Nginx. Cada vez que se hace un push al main o se acepta un pull request, se generan nuevas imágenes Docker, se publican en Docker Hub y un cluster de Kubernetes las actualiza automáticamente, garantizando alta disponibilidad y resiliencia.

🛠️ Tecnologías Utilizadas

FastAPI: API principal.

MongoDB: Base de datos NoSQL.

OpenAI: Integración con modelos de IA.

MySQL: Base de datos relacional.

Gatsby + Nginx: Frontend y servidor web en una sola imagen.

Docker & Docker Hub: Contenerización y distribución de imágenes.

Kubernetes: Orquestación de contenedores.

AWS Ingress: Administración de tráfico de entrada.

⚙️ Flujo de Trabajo CI/CD

Código actualizado en main → Se activa el pipeline de CI/CD.

Construcción de imágenes Docker → Se generan nuevas imágenes para cada servicio.

Publicación en Docker Hub → Las imágenes son subidas al registro.

Kubernetes actualiza los pods → Descarga las nuevas imágenes y las pone en producción.

Auto-restart de servicios → Kubernetes reinicia cualquier pod que falle.

📁 Estructura de Archivos Kubernetes (.yml)

deployment-database.yml → Despliegue de la base de datos MySQL.

deployment-generate.yml → Despliegue del servicio de generación con OpenAI.

deployment-mongo.yml → Despliegue de la base de datos MongoDB.

deployment-nginx-gatsby.yml → Despliegue del frontend con Gatsby y Nginx en una sola imagen.

deployment-user.yml → Despliegue del servicio de usuarios.

ingress-aws.yml → Configuración de Ingress en AWS para manejar tráfico externo.

service-database.yml → Servicio para la base de datos MySQL.

service-generate.yml → Servicio para el backend de generación con OpenAI.

service-mongo.yml → Servicio para la base de datos MongoDB.

service-nginx-gatsby.yml → Servicio para el frontend.

service-user.yml → Servicio para el backend de usuarios.

volumen-persistent.yml → Configuración de volúmenes persistentes para almacenamiento de datos.

🔄 Mecanismos de Resiliencia

✔️ Auto-restart: Kubernetes reinicia los pods si fallan.✔️ Rolling Updates: Actualización sin downtime.✔️ Health Checks: Verificación del estado de los contenedores.✔️ Load Balancing: Distribución eficiente del tráfico con Ingress.

🚀 Cómo Implementarlo

Clonar el repositorio:

git clone https://github.com/tu-usuario/tu-repo.git
cd tu-repo

Aplicar los manifiestos en Kubernetes:

kubectl apply -f k8s/

Verificar los pods en ejecución:

kubectl get pods

Acceder a la aplicación desde el dominio configurado en Ingress.
