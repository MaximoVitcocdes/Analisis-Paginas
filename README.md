# APEX Schema Analyzer

Herramienta para analizar paginas Oracle APEX e identificar dependencias de base de datos para validar migraciones entre esquemas.

## Deploy en Vercel

### Opcion A: Vercel CLI
```bash
npm i -g vercel
vercel --prod
```

### Opcion B: Vercel desde GitHub
1. Subi esta carpeta a un repositorio GitHub.
2. Entra a [vercel.com](https://vercel.com) y crea un proyecto nuevo.
3. Importa el repositorio.
4. Despliega sin configuracion adicional.

### Opcion C: Netlify Drag & Drop
1. Entra a [netlify.com/drop](https://app.netlify.com/drop).
2. Arrastra esta carpeta.
3. Listo.

## Uso

1. Abri la app en el browser.
2. Ingresa una API key de OpenAI (`sk-...`).
3. Pega el contenido de tu pagina APEX en los tabs o carga un archivo `.sql`.
4. Haz clic en **Analizar pagina**.
5. Revisa el inventario de objetos, dependencias, riesgos y checklist.
6. Exporta el resultado como `.md`.

## API Key

La API key se usa directamente desde el browser hacia `api.openai.com`.
No se almacena en ningun servidor ni se registra en esta app.

Importante:
- Debe ser una API key de OpenAI con formato `sk-...`.
- Una suscripcion comun de ChatGPT no genera por si sola una API key; la clave se crea en [platform.openai.com](https://platform.openai.com/).
- Si vas a usar esto en equipo, conviene mover la llamada a un backend y guardar la clave del lado del servidor.

## Que analiza

- Tablas directas e indirectas
- Packages, procedures y functions
- Views y materialized views
- Sequences y triggers
- Colecciones APEX
- Dependencias inferidas de packages
- Checklist de validacion entre esquemas
- Riesgos por objetos faltantes o desactualizados
