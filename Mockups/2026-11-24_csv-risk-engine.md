# Mockup aprobado 24/11/2026 · Botón «⬇ CSV» (Risk engine y Trades)

Cabecera de Risk engine (el resto no cambia):

    Risk engine        [Challenge] [Funded]     Modelo [Todos ▾]  · Informativo…  [⬇ CSV]

Cabecera de Trades:  `Trades … [⬇ CSV] [+ Nuevo trade]`

- Risk engine: descarga los trades que cuentan para el motor (con MFE y «volvió a BE»), filtrados por el selector Modelo.
- Trades: descarga los trades con los filtros globales activos (todos los registrados).
- Una fila por trade: todo lo registrado en el formulario + R de cada gestión (vacío si el trade no entra en el motor).
- Formato Excel España: separador «;», decimales con coma, UTF-8 con BOM.
