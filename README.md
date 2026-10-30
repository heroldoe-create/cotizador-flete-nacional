# Cotizador de flete nacional

Cotiza fletes de carretera dentro de México con **tus propias tarifas**. Lee la solicitud del cliente, la cruza
contra tu tarifario (CSV tuyo), marca los cargos extra que sí aplican (maniobras, estadías, custodia, casetas) y
te entrega la cotización lista para mandar. **Nunca inventa una tarifa**: si la ruta no está en tu tarifario, lo
dice y te pide el dato, no lo estima.

Pre-revisa, cruza y arma evidencia. **No sustituye al contador, al agente aduanal ni al SAT:** no calcula impuestos
por su cuenta, no valida comprobantes y deja el tratamiento fiscal para tu contador.

## Uso en 3 pasos

1. **Pégale la solicitud** del cliente (WhatsApp, correo o formulario: origen, destino, unidad, peso, fechas).
2. **Adjunta tu tarifario** en CSV (o pégalo como tabla). Sin tarifario no cotiza: es su regla de oro.
3. **Copia la cotización** que te devuelve y envíala. Lo que falte va en «Pendientes por confirmar», nunca inventado.

Funciona sin terminal, sin scripts y sin API: se conecta con el conector de Agensi en claude.ai o subiendo el ZIP
de la skill, y trabaja en el chat pegando o adjuntando archivos.

## Qué recibes

- **La cotización en una tabla lista para copiar**: concepto, cantidad, tarifa aplicada (citando la fila de tu
  tarifario) e importe, con subtotal, vigencia y condiciones.
- **Cargos extra marcados con su fuente**: casetas, maniobras, estadías o custodia solo si tu tarifario los trae o
  tú los autorizas por escrito.
- **Una lista de pendientes** con la pregunta exacta cuando falte la ruta, el peso, la unidad o la tasa de IVA.
- **La advertencia de alcance**: qué incluye y qué no incluye la cotización, y que lo fiscal lo confirma tu contador.

## Prueba sin datos propios

La carpeta `ejemplos/caso-01-anden-norte/` trae un caso completo con datos ficticios de la empresa «Andén Norte»:
una solicitud (Tijuana → Hermosillo, 14 t) y un tarifario CSV de 3 rutas. Síguelo a mano: la salida esperada
cuadra exactamente (14 × 1 850 = 25 900, más 3 050 de casetas = 28 950, más IVA) y se reproduce bien al primer
intento pegando los dos archivos de entrada.

## Qué no hace

- No inventa ni interpola tarifas: todo precio sale de tu tarifario o de tu autorización por escrito.
- No calcula impuestos ni dictamina nada fiscal; no sustituye al contador, al agente aduanal ni al SAT.
- No busca casetas en línea ni tránsito en tiempo real.
- No negocia ni responde al cliente por ti: deja la cotización lista para que la revises y envíes.
- No trabaja con datos de terceros ni de empleadores: solo con lo que tú le pegas.

---

## Licencia

**Propiedad intelectual de Heroldo Escobedo**, con el código a la vista ([Licencia de uso de Heroldo 1.0](LICENSE)):

- **Uso personal: gratis.** Léelo, pruébalo y adáptalo para aprender o en tus propios datos.
- **Uso en una empresa o con fines de lucro: solo con compra.** Cómpralo en [Agensi](https://agensi.io/skills/cotizador-flete-nacional)
  o escribe a heroldo@lolo-enterprises.com. La compra cubre a tu empresa.
- **Siempre se cita la fuente:** «Basado en una skill de Heroldo Escobedo — heroldo.org».
- No se revende ni se vuelve a publicar.

> **In English:** Source-available, not open source. Free for personal use. Business use requires purchase on
> [Agensi](https://agensi.io/skills/cotizador-flete-nacional). Attribution to Heroldo Escobedo — heroldo.org is always required.
