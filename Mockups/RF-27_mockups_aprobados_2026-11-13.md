# RF-27 · Curvas de equity ancladas + sincronización manual — APROBADO 13/11/2026

Mockups aprobados por Javier en el chat (13/11/2026). Ver también los dos .html de esta carpeta.

## 1. Curva de equity anclada al balance real (`RF-27_curva_anclada.html`)
- Aplica a la curva de **cartera** (pestaña Cuentas, gráfico `chCartera`) **y a la curva de cada cuenta**.
- Último punto = balance real de la última sincronización + resultados de los trades registrados después.
- Hacia atrás: cada punto = punto siguiente − resultado del trade. El punto de inicio sale calculado (no 25.000 $ fijo).
- Al guardar una sincronización nueva, la curva se recalcula entera.
- Debajo del gráfico: chip «Anclada al balance real del DD/MM» + el aviso existente «+7 días sin sincronizar» + botón «Sincronizar balance».
- Caso real que lo motiva: el 09/11 (2 TP, +289,5 $) la curva bajaba de 24.625,5 a 24.561,5 porque el journal empieza en 25.000 $ sin los trades previos de PRO001 (desfase 353,5 $).

## 2. Ventana «Sincronizar cuentas» (`RF-27_sincronizar.html`)
- Una sola ventana, sin plantillas ni campos extra. Por cuenta: **Balance** y **Min balance (DD)** (copiados de la web de la firma). Placeholder = valor que tiene hoy la app.
- Lo que no se toca no se guarda.
- Columna **Dif.**: diferencia con lo que calcula la app, en $ y % (p. ej. `+35 $ · 0,14 %`). Umbral = **0,2 % del tamaño de la cuenta** (50 $ en 25K, 100 $ en 50K): ≤ umbral verde, > umbral ámbar.
- Se abre desde el botón «Sincronizar balance» bajo la curva (todas las cuentas) y desde un icono en cada tarjeta de cuenta (solo esa).
- Al guardar: se actualiza balance + mínimo, fecha de sync, y se re-anclan las curvas.
- Nombres de métricas en inglés (norma de todas las apps).
