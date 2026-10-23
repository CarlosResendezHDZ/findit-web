# FindIt Web — Adaptación de Mi Librero

Proyecto React + Vite basado en los wireframes compartidos de FindIt. **Es una demostración web funcional, no un backend multiusuario.** Está preparada para verse en navegador móvil y poder conectar Firebase después.

## Pantallas

1. Login de demostración (nombre, sin contraseña real).
2. Inicio con publicaciones recientes y categorías Perdidos / Encontrados.
3. Publicar objeto con imagen opcional, nombre, categoría, descripción, fecha y lugar.
4. Filtros por tipo, categoría, fecha y lugar.
5. Detalle de objeto.
6. Mis publicaciones y favoritos.
7. Buscar objetos.
8. Perfil y cerrar sesión local.

## Instrucciones en Windows 11 y Visual Studio Code

1. Instala Node.js desde https://nodejs.org/ (versión LTS).
2. Descomprime `FindIt_Web.zip`.
3. En VS Code: Archivo > Abrir carpeta > `FindIt_Web`.
4. Terminal > Nueva terminal.
5. Ejecuta `npm install`.
6. Ejecuta `npm run dev`.
7. Abre la dirección mostrada (normalmente http://localhost:5173/).
8. En Login, escribe tu nombre y pulsa Comenzar.
9. Prueba Inicio, Buscar, Publicar, Detalle, Filtros, Favoritos, Mis publicaciones y Perfil.
10. Para compilar, ejecuta `npm run build`.

## Publicar en Firebase Hosting

1. Crea un proyecto en https://console.firebase.google.com/.
2. Instala la CLI: `npm install -g firebase-tools`.
3. Inicia sesión: `firebase login`.
4. Ejecuta `firebase init hosting` dentro de la carpeta del proyecto.
5. Selecciona tu proyecto; carpeta pública: **dist**; SPA rewrites: **Yes**; GitHub: **No**; sobrescribir index.html: **No**.
6. Ejecuta `npm run build`.
7. Ejecuta `firebase deploy --only hosting`.

## Limitaciones actuales

- El nombre de usuario es una simulación local; **no hay autenticación real ni control de acceso**.
- Publicaciones, favoritos y sesión se guardan con `localStorage` en ese navegador. Otros usuarios y dispositivos no ven esos datos.
- Las imágenes pequeñas se guardan como Data URL en el navegador; imágenes grandes pueden agotar el espacio local.
- El indicador sin conexión refleja la red; la app no tiene todavía Service Worker ni soporte PWA offline completo.
- No hay notificaciones reales ni chat/contacto entre usuarios.

## Próxima etapa (Firebase + móvil)

- Firebase Authentication para cuentas seguras.
- Cloud Firestore para publicaciones sincronizadas.
- Cloud Storage para fotos.
- Reglas de seguridad para que cada usuario solo edite sus publicaciones.
- PWA instalable y pruebas móviles; posteriormente se puede empaquetar como app con Capacitor si se desea.

## Estructura

- `src/App.jsx`: rutas, componentes, lógica local de publicaciones y favoritos.
- `src/style.css`: diseño responsive para web y celular.
- `src/main.jsx`: arranque de React y enrutador.
- `index.html`: entrada Vite.
