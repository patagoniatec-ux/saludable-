# WEB SALUDABLE — Conocer para elegir
Plataforma educativa sobre alimentos, nutrientes y bienestar. Navegación por relaciones: **Producto → Nutriente → Bienestar → Fuente**.
Contenido educativo general; no diagnostica ni recomienda tratamientos. Todos los datos son **demostrativos**.

## Estructura
`index.html` · `css/style.css` · `js/script.js` (rutas, vistas, buscador, filtros, admin) · `data/{products,nutrients,wellness,sources}.js` · `assets/` (imágenes)

## Ejecutar
Abrir `index.html` en el navegador (no requiere servidor). Opcional: `python3 -m http.server`.

## Modificar datos
Editar los archivos de `data/` (un objeto por registro; las relaciones se hacen con ids: `p1`, `n1`, `w1`, `f1`). También desde **Administración** (se guarda en localStorage del navegador; "Restablecer datos demo" en Configuración).
- **Productos / nutrientes / contenidos / fuentes:** agregar objetos en el archivo correspondiente, con los campos del ejemplo.
- **Imágenes:** copiar a `assets/` y poner la ruta en el campo `imagen` (ej. `assets/almendras.jpg`).
- Reemplazar los valores `null` y las fuentes "[Pendiente]" por datos verificados. No inventar URLs ni estudios.

## Publicar
- **GitHub Pages:** subir la carpeta, Settings → Pages → rama `main`, carpeta raíz.
- **Netlify / Vercel:** importar el repositorio; sitio estático, sin comando de build, directorio raíz.

## Base de datos real
Cada archivo de `data/` equivale a una tabla (products, nutrients, wellness, sources). Crear tablas con esos campos (relaciones como tablas puente), y reemplazar `window.DB` en `js/script.js` por consultas a Supabase/Firebase/PostgreSQL.

## API de IA
Implementar `askAI(q)` en `js/script.js`: enviar la pregunta y el contexto (productos, nutrientes, bienestar, fuentes) a un backend propio (no exponer claves en el navegador), devolver respuesta + ids de fichas/fuentes usadas. Si no hay información suficiente, mostrar: "Esta información todavía no está disponible en nuestra base de conocimiento."

## Pendiente (próximas versiones)
Comparador de alimentos (sin declarar cuál es "mejor"), recetas, listas de compras, favoritos, usuarios, e-commerce.
