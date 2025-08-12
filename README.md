# AI-Compliance Copilot

MVP para cumplimiento de la Ley de IA de la UE y RGPD.

## Arquitectura

- **apps/web**: Frontend Next.js con Auth0
- **apps/api**: Backend Node.js con autenticación JWT
- **apps/opa**: Servicio Open Policy Agent para evaluación de riesgos
- **PostgreSQL**: Base de datos principal
- **MinIO**: Almacenamiento de evidencias (compatible con S3)

## Configuración rápida

1. **Clonar y configurar dependencias:**
   ```bash
   git clone 
   cd ai-compliance-copilot
   npm install
   ```

2. **Configurar variables de entorno:**
   ```bash
   # En apps/api/
   cp .env.example .env
   # Editar .env con tus credenciales

   # En apps/web/
   cp .env.local.example .env.local
   # Editar .env.local con tus credenciales Auth0
   ```

3. **Levantar servicios con Docker:**
   ```bash
   docker-compose up -d postgres minio
   ```

4. **Ejecutar migraciones:**
   ```bash
   cd apps/api
   npm run migrate
   ```

5. **Iniciar aplicación:**
   ```bash
   # Terminal 1: API
   cd apps/api && npm run dev

   # Terminal 2: Web
   cd apps/web && npm run dev

   # Terminal 3: OPA
   cd apps/opa && npm run dev
   ```

## Funcionalidades Sprint 1

  **Autenticación**: Auth0 con roles admin/member
  **CRUD Sistemas**: Crear y gestionar sistemas de IA
  **CRUD Datasets**: Gestionar conjuntos de datos
  **Evaluación de riesgos**: Integración con OPA
  **Generación DPIA**: Documentos PDF automáticos
  **Almacenamiento evidencias**: MinIO con URLs pre-firmadas
  **UI MVP**: Wizard de 3 pasos
  **CI/CD**: GitHub Actions

## Despliegue

El proyecto está configurado para desplegarse en:
- **API**: Render/Fly.io
- **Web**: Vercel/Netlify
- **Base de datos**: PostgreSQL gestionado
- **Almacenamiento**: S3 o MinIO

## Estructura del proyecto

```
ai-compliance-copilot/
├── apps/
│   ├── web/          # Frontend Next.js
│   ├── api/          # Backend Node.js
│   └── opa/          # Open Policy Agent
├── infra/            # Configuración de infraestructura
└── docker-compose.yml
```

## Próximos sprints

- **Sprint 2**: Colaboración en tiempo real
- **Sprint 3**: RAG con documentos legales
- **Sprint 4**: Dashboards y reportes avanzados
---

