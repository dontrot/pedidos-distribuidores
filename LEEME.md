# Pedidos a distribuidores

Aplicación web adaptable a celular. Todos los que tengan el enlace comparten el catálogo y los pedidos, sin usuarios ni contraseñas.

## 1. Crear la base compartida
1. Entrá en https://supabase.com y creá un proyecto.
2. En el proyecto, abrí **SQL Editor**, pegá todo el contenido de `supabase.sql` y ejecutalo.
3. En **Project Settings > API** copiá la **Project URL** y la clave **anon/public** (nunca uses la `service_role`).

## 2. Configurar la app
1. Copiá `.env.example` como `.env`.
2. Pegá tus datos:
   - `VITE_SUPABASE_URL`: Project URL
   - `VITE_SUPABASE_ANON_KEY`: clave anon/public
3. Instalá Node.js (https://nodejs.org).
4. En esta carpeta ejecutá:
   ```bash
   npm install
   npm run dev
   ```
5. Para publicar, subí el proyecto a GitHub y conectalo con https://vercel.com (Build: `npm run build`; Output: `dist`). Cargá las dos variables `VITE_SUPABASE_URL` y `VITE_SUPABASE_ANON_KEY` en la configuración del proyecto de Vercel y desplegá. Compartí la URL resultante.

## 3. Cargar el catálogo
En la app abrí **Catálogo > Seleccionar Excel o CSV**. El archivo debe tener encabezados `MARCA`, `PRODUCTO` y `PRECIO`. También acepta `DESCRIPCION`/`ARTICULO` como nombre de producto. Los precios se importan como números.

## Importante sobre el acceso sin contraseña
Esta versión está configurada para que cualquiera que tenga el enlace pueda ver, crear, cambiar y borrar pedidos, y modificar el catálogo. No hay identificación de quién hizo cada cambio. El enlace puede reenviarse; no lo publiques si el catálogo o los pedidos son confidenciales. Para una operación comercial con información sensible conviene agregar permisos o un código de acceso.

## Funciones incluidas
- Cliente y pedido con varios productos.
- Selección de marca y luego productos de esa marca.
- Precio unitario, cantidad, subtotal por renglón y total.
- Pedidos compartidos entre dispositivos, historial y estados.
- Importación de Excel/CSV y actualización de precios existentes.
