# 06 · Agenda para la reunión del viernes 4 de septiembre, 16:00

> Objetivo de la reunión: **salir con 8 decisiones tomadas y escritas.**
> No con más análisis. El análisis ya está hecho en los documentos 01 a 05.
>
> Duración sugerida: 75 minutos. 10 min por decisión, 15 de cierre.

---

## Antes de empezar: el contexto que cambia la urgencia

Quedan **87 días** para que se cierre la ventana de venta a anfitriones y **102** para que
parta la temporada. La regla del documento base es clara: se vende entre agosto y noviembre;
en diciembre nadie contesta y en abril ya se olvidó del dolor. **Si no llegamos con
inventario al 1 de diciembre, perdemos 12 meses completos.**

Eso significa que hoy no podemos abrir temas nuevos. Hay que cerrar.

---

## Decisión 1 · Mecánica de cobro

**Lo acordado el viernes pasado:** comisión fija 0, solo comisión variable pagada por el
cliente. **El instinto es correcto.** Pero hay que elegir cómo se cobra, porque de eso
dependen los márgenes:

| Opción | Neto por reserva | % del GMV |
|---|---|---|
| **A · El huésped paga online un cargo de reserva del 12% del total, imputable al precio; el saldo lo paga en el camping** | **$9.546** | **10,6%** |
| B · Recaudamos el total online y le liquidamos al anfitrión menos 12% | $6.220 | 6,9% |
| V · El huésped paga un fee del 8% **encima** del precio | $4.586 | 5,1% |

> **Recomendación: A.** Es la mecánica de Pitchup. Rinde el doble que las alternativas,
> elimina el trabajo de liquidaciones, evita que el huésped pueda ahorrarse plata llamando
> directo (paga lo mismo que por WhatsApp), y es el "modelo agencia" que simplifica lo
> tributario. Detalle en `02-modelo-de-negocio.md` §3.

**Lo que hay que decidir:** A, B o V. Y el porcentaje (recomiendo 12%, con 0% las primeras
20 reservas de cada camping pionero).

---

## Decisión 2 · Qué le prometemos al anfitrión, por escrito

La promesa tiene que quedar en el contrato desde el día uno, porque el error que más mata
estos proyectos es que el anfitrión sienta que le cambiaron las reglas.

> **Propuesta:** *"El software es gratis y es tuyo, para siempre. Las reservas que tú traigas
> —tu WhatsApp, tu Instagram, tu link— no pagan comisión, nunca. Solo cobramos sobre las
> reservas que nosotros te mandamos, y esa comisión la paga el huésped al reservar."*

**Lo que hay que decidir:** si asumimos ese compromiso de 0% permanente sobre las reservas
directas. Mi recomendación es que **sí**, y que quede en el contrato — es lo que elimina de
raíz el problema de la desintermediación y lo que hace que este modelo sea distinto al de
Rutero.

---

## Decisión 3 · Alcance de la categoría

"Camping" solo tiene un techo de ~$500M anuales de ingresos en Chile. **Alojamiento
outdoor** (camping + glamping + domos + cabañas rurales + motorhome + refugios) multiplica
el mercado 5–8x y desestacionaliza.

**Lo que hay que decidir:** que la categoría es alojamiento outdoor. Consecuencias
inmediatas: el **nombre de marca no puede tener la palabra "camping"** dentro, y el esquema
de datos se diseña con tipos de unidad desde hoy.

---

## Decisión 4 · Cabeza de playa geográfica

| Opción | A favor | En contra |
|---|---|---|
| Pucón / Villarrica / Panguipulli | Oferta profesionalizada, tickets altos, marca de destino | Estacional puro, 750 km de Santiago |
| Cajón del Maipo + Litoral Central | 8M de personas a menos de 2h, tráfico todo el año, se puede visitar un sábado | Ticket bajo, mucha informalidad |
| Torres del Paine / Patagonia | Ticket altísimo, demanda internacional | Pocos actores muy poderosos, difícil de negociar |

> **Recomendación: híbrido.** **Cajón del Maipo + Litoral Central** como mercado operativo
> —permite iterar todos los fines de semana sin pedir vacaciones, y tiene demanda fuera de
> temporada, que es justo donde el anfitrión sí nos necesita— **más un viaje de 5 días a
> Pucón/Panguipulli en octubre** para conseguir 15 campings de ticket alto que suban el
> promedio y den prestigio al catálogo.
>
> El documento base recomienda Pucón primero. Cambio el orden por una razón práctica:
> **ninguno de los dos va a dejar su trabajo este año**, y un mercado a 2 horas se trabaja
> 30 fines de semana al año, uno a 750 km se trabaja dos veces.

---

## Decisión 5 · Reparto de trabajo (ajuste al acuerdo del viernes)

**Pablo — producto.** Sin cambios. Es todo el MVP.

**Vicente — cambio de prioridades.** Lo acordado fue: sociedad, channel managers, propuesta
de valor. Propongo reemplazar "investigar channel managers" por el trabajo de calle:

| Prioridad | Tarea | Por qué |
|---|---|---|
| 1 | Catastro de 300 campings | Es el activo. Sin esto no hay a quién vender. |
| 2 | 40 llamadas de descubrimiento | **Es lo que define si el negocio existe.** El error #1 que hunde estos proyectos es construir 8 meses antes de hablar con 40 anfitriones. |
| 3 | 5 cartas de intención | La prueba de fuego. |
| 4 | Constituir la SpA + legal | Urgente, pero después de la Decisión 8. |
| ~~5~~ | ~~Channel managers~~ | **Ya está resuelto: iCal en V1.** Un channel manager real exige certificación de partner y meses de trabajo, y solo sirve para cabañas y domos — Booking ni siquiera sabe modelar un sitio de carpa. No hay nada que investigar. |

**Lo que hay que decidir:** cuántas horas semanales pone cada uno. Con menos de 15 horas
semanales de Vicente en calle durante septiembre y octubre, no llegamos a la temporada.

---

## Decisión 6 · Alcance del MVP — la lista de lo que NO hacemos

Para llegar al 1 de noviembre hay que cortar. Propongo dejar **fuera** del MVP:
app nativa · channel manager · boleta electrónica · liquidaciones y payouts · precios
dinámicos · mensajería interna · multi-idioma · plano del camping con sitios numerados ·
confirmación instantánea · programa de puntos.

Y dejar **dentro**: calendario del anfitrión (móvil) · alta manual de reservas · link de
cobro · ficha pública con solicitud de reserva · checkout con Flow · buscador con mapa y
filtros · WhatsApp transaccional · reseñas verificadas.

> El MVP está listo cuando un anfitrión que no conocemos publica su camping en 15 minutos
> desde el teléfono y anota una reserva de WhatsApp en 30 segundos. Nada más.

**Lo que hay que decidir:** aprobar la lista. Cada cosa que se agregue hoy sale de algo que
está adentro — no se suma tiempo, se resta alcance.

---

## Decisión 7 · Nombre, dominio y marca

Bloqueante para: dominio, redes sociales, INAPI, y las primeras fichas publicadas.

Criterios: que **no** diga "camping" (por la Decisión 3), que sea pronunciable en español e
inglés (por el receptivo), que tenga `.cl` y `.com` disponibles, y que sirva en Argentina y
Perú.

**Lo que hay que decidir:** el nombre, hoy. Si no sale, elegir un nombre de trabajo y
registrar el dominio igual — pero el registro de INAPI no puede esperar más de dos semanas.

---

## Decisión 8 · Sociedad: porcentajes, vesting y capital

La conversación incómoda, y la que hay que tener hoy justamente porque todavía no hay nada
que repartir.

Sobre la mesa:

- **Porcentajes.** Vicente aporta la idea, la red y el trabajo de calle. Pablo aporta el
  producto completo, que a precio de mercado son **$40–50 millones** de desarrollo en el
  primer año (el propio documento presupuesta un desarrollador semi-senior a $2,4M/mes).
  No estoy proponiendo un número: estoy proponiendo que se hable y se escriba.
- **Vesting de 4 años con cliff de 1.** Recomendación explícita del documento base y no
  negociable entre socios que además son familia. Protege a los dos.
- **Capital.** ~$13.000.000 el primer año, ~$6,5M cada uno. ¿Se aporta en partes iguales?
  ¿Se registra como aporte de capital o como préstamo del socio?
- **Dedicación comprometida** por escrito, y qué pasa si uno no la cumple.
- **Qué pasa si uno se baja** (buy-sell, tag-along, drag-along).
- **SpA, nunca EIRL** — la EIRL no permite socios ni recibir inversión.

---

## Cierre: los 7 compromisos de esta semana

| # | Compromiso | Quién | Fecha |
|---|---|---|---|
| 1 | Dominio + redes registradas | Pablo | 5-sep |
| 2 | Landing de captura publicada | Pablo | 8-sep |
| 3 | Planilla de catastro abierta, 20 campings cargados | Vicente | 8-sep |
| 4 | Reserva real hecha en Travana, de punta a punta | Vicente | 8-sep |
| 5 | Mensajes enviados a Rutero y Glampi por LinkedIn | Vicente | 8-sep |
| 6 | Abogado cotizado (T&C + contrato + pacto) | Vicente | 10-sep |
| 7 | Esquema de datos v1 en el repo, revisado por ambos | Pablo | 10-sep |

**Próxima reunión: viernes 11 de septiembre, 16:00.**
Punto único de la agenda: primeros hallazgos de las llamadas.

---

## Lo que NO hay que discutir hoy

Para proteger el tiempo: precios dinámicos, app móvil, expansión a Argentina, seguros,
productos financieros, levantamiento de capital, diseño del logo. Todo eso es real y todo
eso es del año 2. Hoy solo importan las 8 decisiones de arriba.
