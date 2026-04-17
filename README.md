# APEX Schema Analyzer

Herramienta para analizar páginas Oracle APEX e identificar todas las dependencias de base de datos necesarias para validar una migración entre esquemas.

## Deploy en Vercel

### Opción A: Vercel CLI (más rápido)
```bash
npm i -g vercel
vercel --prod
```

### Opción B: Vercel desde GitHub
1. Subí esta carpeta a un repositorio GitHub
2. Entrá a [vercel.com](https://vercel.com) → New Project
3. Importá el repositorio
4. Sin configuración adicional → Deploy

### Opción C: Netlify Drag & Drop
1. Entrá a [netlify.com/drop](https://app.netlify.com/drop)
2. Arrastrá la carpeta `apex-analyzer`
3. Listo ✓

## Uso

1. Abrí la app en el browser
2. Ingresá tu API Key de Anthropic (`sk-ant-...`)
3. Pegá el contenido de tu página APEX en los tabs:
   - **Export / SQL**: código SQL, PL/SQL, dynamic actions, LOVs, validaciones
   - **Packages / Procs**: código de packages o procedures referenciados
   - **Contexto adicional**: esquema origen/destino, errores observados
4. Clic en **Analizar página**
5. Revisá el análisis: inventario de objetos, dependencias, tabla completa y checklist
6. Exportá el resultado como `.md`

## API Key

La API Key se usa directamente desde el browser hacia `api.anthropic.com`.  
No se almacena en ningún servidor ni se registra.  
Para un deploy de equipo, considerá agregar una variable de entorno en el servidor.

## Qué analiza

- Tablas directas e indirectas
- Packages, procedures, functions
- Views y materialized views
- Sequences y triggers
- Colecciones APEX
- Dependencias inferidas de packages
- Checklist de validación entre esquemas
- Riesgos por objetos faltantes
