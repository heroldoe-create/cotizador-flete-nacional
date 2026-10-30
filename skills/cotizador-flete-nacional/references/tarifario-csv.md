# Formato del tarifario (CSV del usuario)

El CSV es del usuario: la skill no impone columnas, pero reconoce estas cabeceras (en español, sin acentos
preferiblemente). El usuario puede traer solo un subconjunto; lo que no traiga se pide o se deja en pendientes.

| Columna | Para qué sirve | Obligatoria |
|---|---|---|
| `origen` | Ciudad o zona base de salida | Sí |
| `destino` | Ciudad o zona base de llegada | Sí |
| `unidad` | Tipo de unidad (caja 3.5t, torton, tractocamion, rabon) | Si el tarifario distingue por unidad |
| `tarifa_fija` | Precio por viaje completo | Una de las tres de tarifa |
| `tarifa_ton` | Precio por tonelada | Una de las tres |
| `tarifa_m3` | Precio por metro cúbico | Una de las tres |
| `minimo` | Cargo mínimo por viaje | No |
| `moneda` | MXN por defecto si no viene | No |
| `vigencia` | Desde-hasta de la tarifa (AAAA-MM-DD) | No |
| `casetas` | Monto de casetas de esa ruta, si el tarifario las carga aparte | No |
| `maniobras` | Monto o regla de maniobras (ej. `350/hora con min 2h`) | No |
| `estadia` | Regla de estadía (ej. `primeras 2h libres, despues 400/h`) | No |
| `custodia` | Regla de custodia si aplica | No |
| `notas` | Condiciones propias del tarifario | No |

## Reglas de cruce

- La coincidencia de ruta es por `origen` + `destino`. Si el tarifario usa zonas (ej. «RMX» = red metropolitana),
  la zona vale porque así lo define el CSV del usuario, no la skill.
- Si una fila trae `vigencia` y está vencida respecto a la fecha de hoy, la tarifa se marca como **vencida** y se
  pregunta si sigue vigente; no se usa sin confirmar.
- Los extras (casetas, maniobras, estadía, custodia) se cobran **solo si la fila de la ruta los trae** o el
  usuario los autoriza por escrito en el chat. La skill nunca los «completa» con cifras externas.
- El redondeo y los mínimos se aplican tal cual el CSV los diga; si el CSV no dice nada, no se redondea y se anota.
