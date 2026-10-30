# Entrada — caso 01 (ficticio, empresa «Andén Norte»)

## solicitud.md (lo que pegó el usuario)

> Buenas, ¿me cotizan un flete de Tijuana BC a Hermosillo Son? Son 22 tarimas de refacciones,
> unas 14 toneladas, caja seca de 48 pies. Descargan con grúa del cliente, sin maniobras nuestras.
> Salida posible el jueves 5-nov-2026 por la mañana. ¿Incluyen casetas? Cliente nuevo, nos piden vigencia.

## tarifario-anden-norte.csv (el tarifario del usuario)

```csv
origen,destino,unidad,tarifa_ton,minimo,casetas,vigencia,notas
Tijuana,Hermosillo,tractocamion 48ft,1850,15000,3050,2026-01-01/2026-12-31,Casetas cobradas aparte; no incluye maniobras
Mexicali,Culiacan,torton,2100,12000,2780,2026-01-01/2026-12-31,
Tijuana,La Paz,torton,3600,18000,4120,2026-01-01/2026-12-31,Requiere custodia autorizada por escrito
```

## Qué debe hacer la skill

1. Empareja origen Tijuana + destino Hermosillo + unidad tractocamion 48ft → fila 1.
2. Tarifa por tonelada: 14 t × 1 850 = 25 900 (arriba del mínimo de 15 000, aplica el calculado).
3. Casetas 3 050 aparte, porque la fila las trae y el cliente las pregunta.
4. Maniobras: la solicitud dice que descarga con grúa del cliente → NO se cobra maniobra.
5. IVA: el tarifario no declara tasa → cotización «más IVA» y se anota para el contador.
6. Vigencia: la del tarifario (hasta 2026-12-31); se recomienda poner 15 días de vigencia comercial.
