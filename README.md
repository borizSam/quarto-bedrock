# 🤖 Bedrock-IA — Generación Automática de Contenido DevOps

## Descripción

Este proyecto implementa un **pipeline completamente automatizado** que genera y publica contenido técnico DevOps utilizando **IA generativa**, **arquitectura serverless en AWS** y **CI/CD con GitHub Actions**.

Cada día, el sistema crea un nuevo post técnico, lo renderiza como sitio web con **Quarto** y lo publica automáticamente en **GitHub Pages**.

---

## 🧠 Arquitectura General

```bash
GitHub Actions (cron)
        ↓
Amazon API Gateway
        ↓
AWS Lambda (Python)
        ↓
Amazon Bedrock (LLM)
        ↓
Archivo .qmd (Quarto)
        ↓
Quarto Render
        ↓
GitHub Pages
```

## 🚀 Flujo de Trabajo

Programación diaria
- GitHub Actions ejecuta un job automático cada día mediante cron.

Llamada a la API
- El job invoca un endpoint REST expuesto en Amazon API Gateway.

Procesamiento Serverless
- Una función AWS Lambda (Python) orquesta la solicitud.

Generación de contenido con IA
- Lambda consulta Amazon Bedrock para generar un post técnico DevOps.

Creación del documento
- GitHub Actions genera automáticamente un archivo .qmd (Quarto Markdown).

Renderizado automático
- Quarto procesa el archivo y lo convierte en HTML.

Despliegue continuo
- GitHub Pages publica el contenido automáticamente.

## 🛠️ Stack Tecnológico

CI/CD: GitHub Actions

Cloud: AWS

Amazon API Gateway

AWS Lambda (Python)

Amazon Bedrock

IA Generativa: Amazon Bedrock (LLM)

Static Site Generator: Quarto

Hosting: GitHub Pages

Formato de contenido: Quarto Markdown (.qmd)

## 📂 Estructura del Proyecto

```bash
├── .github/workflows/
│   └── autopost.yml        # Workflow de GitHub Actions
├── posts/                  # Posts generados automáticamente (.qmd)
├── docs/                   # Sitio renderizado (GitHub Pages)
├── styles.css              # Estilos personalizados
├── _quarto.yml             # Configuración del sitio Quarto
└── README.qmd
```

## 🔐 Seguridad
La URL del endpoint NO está expuesta en el repositorio.

Se gestiona mediante GitHub Secrets.

La API está pensada para uso controlado desde GitHub Actions.

Arquitectura adecuada para proyectos personales y demos técnicos.

## 📈 Objetivo del Proyecto
Automatizar la creación de contenido técnico

Aplicar principios DevOps y CI/CD

Explorar IA generativa en flujos reales

Demostrar un caso práctico de Serverless + IA

## 🧪 Estado del Proyecto
✅ Pipeline funcional

✅ Publicación automática diaria

✅ Integración con Amazon Bedrock

## 🚧 Mejoras futuras:

Imágenes generadas por IA

Optimización SEO / OpenGraph

Mejora del prompt de generación