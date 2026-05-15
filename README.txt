# Cero Grados 0° | App Helados + Caja

Archivos:
- index.html: listo para GitHub Pages / GitHub Desktop
- supabase_schema.sql: ejecutar en Supabase > SQL Editor

Importante:
- No se usa la API key secreta en el HTML.
- Solo se usa la anon public key para navegador.
- La tabla se llama: cero_grados_orders

Flujo:
1. Helados toma pedido.
2. Caja marca pagado.
3. Helados recibe pedido pagado para entregar.
4. Helados confirma entregado o no entregado.
5. Historial queda guardado.


SOLUCIÓN SI CAJA NO RECIBE PEDIDOS DE OTRA COMPUTADORA:

1. En Supabase entra a SQL Editor.
2. Ejecuta el archivo supabase_schema.sql completo.
3. En Supabase ve a Table Editor y confirma que exista:
   public.cero_grados_orders
4. Haz una prueba:
   - Computadora 1: abre Helados y manda pedido.
   - Computadora 2: abre Caja, inicia sesión y presiona Actualizar pedidos.
5. Si aparece error en la parte superior de la app, revisa:
   - URL de Supabase
   - anon public key
   - políticas RLS
   - que la tabla tenga permisos para anon

IMPORTANTE:
No uses la api key secreta dentro del HTML. Solo anon public.
