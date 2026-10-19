# WHAT IF? — Interfaz web

Interfaz de WHAT IF? conectada a la API Flask/PostgreSQL que está en `what-if-backend`. Espacios, cuentas, preferencias, escenarios, distribuciones y resultados se consultan y guardan en la API.

## Iniciar la aplicación

1. En `C:\Users\eliez\Documents\Codex\2026-09-21\act-a-como-un-desarrollador-backend\what-if-backend`, copia `.env.example` como `.env` y coloca la conexión real de PostgreSQL y una clave JWT privada.
2. Crea la base indicada en `DATABASE_URL` y ejecuta `database/schema.sql`. Si ya tenías la base, vuelve a ejecutar el esquema para aplicar las nuevas tablas y columnas.
3. En PowerShell, inicia Flask desde la carpeta del backend:

   ```powershell
   cd C:\Users\eliez\Documents\Codex\2026-09-21\act-a-como-un-desarrollador-backend\what-if-backend
   .\venv\Scripts\Activate.ps1
   python app.py
   ```

4. En otra terminal sirve esta carpeta:

   ```powershell
   python -m http.server 5500
   ```

5. Abre `http://127.0.0.1:5500` y usa **Solicita acceso** para crear tu cuenta.

La interfaz espera Flask en `http://127.0.0.1:5000/api`. Si usas otro host o puerto, define `window.WHATIF_API_URL` antes de `js/api/api.js` en las páginas.

## Datos que se guardan

- Cuentas y datos del perfil, con contraseñas cifradas por el backend.
- Preferencias de unidades y cuadrícula.
- Espacios, dimensiones, imágenes de planos y escenarios.
- La distribución completa independiente de cada escenario, incluidos objetos agregados o quitados.
- Simulaciones estimadas e historial.

Los elementos del plano se representan en coordenadas físicas al guardarse. La detección de objetos desde imágenes todavía es una vista de demostración; los objetos se guardan al editarlos en el editor.
