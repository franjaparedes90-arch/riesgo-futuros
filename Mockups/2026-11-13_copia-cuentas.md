# Copia de cuentas (copiador del broker) — APROBADO 13/11/2026

Mockup v3 aprobado por Javier en el chat (13/11/2026): `2026-11-13_copia-cuentas.html` (4 pantallas). Original: https://claude.ai/artifact/PudrpkJv5qs1ReJpcR9pHZ

## Reglas
- **Grupo de copia** = funded líder + challenge(s) copiada(s). En la app funciona como **una sola cuenta**: ocupa una posición en la cola de rotación.
- Copia **1:1**: riesgo y target salen de la **escalera y el estado de la funded líder** (no se recorta a la regla v7 de challenge).
- **TP máx. hoy del grupo** = el de la cuenta más restrictiva. La consistency se toma de la ficha de cada cuenta (lo comprado); en el grupo manda el % más bajo (p. ej. 40 % frente a 50 % → 40 %).
  - Caso A: TP máx. ≥ target → se opera normal.
  - Caso B: 0,4 % de la cuenta ≤ TP máx. < target → cortar las dos en el TP máx.
  - Caso C: TP máx. < 0,4 % → grupo bloqueado hoy; va el siguiente de la cola; mañana se empieza por el grupo.
- Tras un SL: la rotación actual (el grupo cuenta como una posición).
- Si un trade llega a lo que le falta a la challenge para pasar → aviso: cortar ahí y cerrar las dos.
- La copia **no se apaga nunca**: las cuentas del grupo llevan siempre los mismos trades.
- Tope diario en el broker: 600 $ solo en la funded líder («Liquidate and Block»); las copias sin tope (el corte lo marca la tarjeta). La app solo lo muestra como recordatorio.
- Plan B de la tarjeta: la siguiente cuenta de la cola si el SL no entra en el grupo.

## Pantallas
1. **Journal · riesgo**: tarjeta del grupo con desplegable (cuentas, rol, consistency, ganado hoy, TP máx. hoy, tope del broker); variantes B y C.
2. **Cuentas**: columna «Grupo de copia» en la tabla; sección **«Gestión de copias»** (crear / editar / deshacer grupo: líder, copias, tope diario); en la ficha, Consistency con selector «Sin consistency / Con %» (sin consistency deja de aplicar el 50 % por defecto).
3. **Registro del trade**: **un solo trade** (R sistema, cuenta una vez para el Risk engine) con **una ejecución por cuenta** (MNQ, resultado $, comisiones) y el grupo en turno. Si se pasó del corte del día, la app pide el motivo:
   - «El precio corrió, no dio tiempo a poner el TP» → incidencia de ejecución, plan respetado, R sistema = R del corte.
   - «Busqué más que el target» → plan no respetado (P2), R sistema = R del target vigente.

## Notas
- En la app se dice «broker» (genérico), nunca el nombre de la plataforma; no se menciona Tradinverso.
- Nombres de métricas en inglés (Consistency, etc.).
- Tradinverso (fuera de la app): un trade por cuenta con el mismo R y la etiqueta «Copia».
