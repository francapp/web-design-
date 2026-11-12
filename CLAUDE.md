# Portfolio Franco Preci

Este es el portfolio de Franco Preci (francopreci.com). El sitio es estático y se publica en Netlify (NO en Vercel), conectado al repo de GitHub francapp/web-design- con deploy automático al hacer push a la rama main. No hay build command; el publish directory es la raíz. Cada cambio se hace en esta carpeta, se commitea y se pushea a main.

## Arquitectura de las páginas .dc.html

`support.js` reemplaza el elemento `<x-dc>` completo con un root de React antes de que el browser procese el contenido del template. Por eso, cualquier `<script>` o `<style>` escrito dentro del template (dentro de `<x-dc>` pero fuera de `<helmet>`) nunca se ejecuta ni aplica. Todo JS y CSS nuevo debe ir en el bloque `<helmet data-dc-atomics>`, que se procesa antes del render de React y se inyecta en el `<head>`.
