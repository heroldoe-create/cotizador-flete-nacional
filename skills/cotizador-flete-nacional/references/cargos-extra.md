# Cargos extra: cuándo se marcan

La skill marca un cargo extra solo con una de estas dos fuentes, en este orden de preferencia:

1. **El tarifario del usuario**: la fila de la ruta trae el concepto tarifado (columna `casetas`, `maniobras`,
   `estadia` o `custodia`).
2. **Autorización explícita del usuario en el chat** (con cifra y condición). Se cita en la cotización como
   «autorizado por el usuario».

Si ninguna de las dos existe, el concepto va a «Pendientes por confirmar» con la pregunta exacta, nunca con una
cifra inventada.

| Cargo | Cuándo se marca | Qué se pide si falta fuente |
|---|---|---|
| Maniobras | La solicitud pide carga/descarga con equipo o personal extra | «¿Cobras maniobras en esta ruta? ¿cuánto?» |
| Estadía | La solicitud advierte espera en origen o destino | «¿Tu tarifario cobra estadía? ¿desde qué hora y cuánto?» |
| Custodia | La mercancía o el cliente piden custodia | «¿Tienes tarifa de custodia o la subcontratas?» |
| Casetas | El tarifario las carga aparte del flete | Se toman del tarifario; si no vienen, se preguntan por ruta |

## Lo que la skill NO hace con los extras

- No busca montos de casetas en internet ni los recuerda de memoria.
- No asume que «el flete ya incluye» casetas si el tarifario no lo dice: se pregunta.
- No agrega margen, comisión ni utilidad que el usuario no haya declarado: la cotización reproduce el tarifario
  del usuario, no lo mejora ni lo infla.
