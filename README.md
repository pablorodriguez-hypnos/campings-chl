# Campings CHL

Marketplace y sistema de reservas de alojamiento outdoor en Chile
(camping · glamping · domos · cabañas rurales · motorhome · refugios).

**Estado: análisis y planificación.** Todavía no se escribe código de producto — primero se
cierran las decisiones de `docs/06-agenda-reunion.md`.

---

## La tesis en tres líneas

En Chile hay ~2.000 campings que operan con cuaderno, WhatsApp y transferencia.
Nadie tiene la disponibilidad real de ninguno de ellos.
**El que la tenga, manda** — y a partir de ahí el marketplace se construye solo.

## El modelo

```
Software de gestión GRATIS para el anfitrión, condicionado a estar publicado.
  ↓
Reservas que él origina  →  comisión 0%, para siempre.
Reservas que originamos  →  el huésped paga online un cargo de reserva del 12%
                            del total (imputable al precio); el saldo lo paga
                            en el camping.
```

Comisión fija: 0. Variable: la paga el huésped. Solo sobre lo que traemos nosotros.

Es la secuencia que ejecutó [Campspot](https://software.campspot.com/) en EE. UU.
—SaaS en 2015, marketplace en 2020, USD 17,4M de ingresos sin levantar capital de riesgo—
con la mecánica de cobro de [Pitchup](https://www.pitchup.com/).

---

## Documentos

| # | Documento | Qué contiene |
|---|---|---|
| 01 | [Análisis y diagnóstico](docs/01-analisis-y-diagnostico.md) | Evaluación del plan base y de los next steps; los tres riesgos reales; el veredicto |
| 02 | [Modelo de negocio](docs/02-modelo-de-negocio.md) | Pricing, unit economics comparados, presupuesto real, decisiones tributarias |
| 03 | [Benchmark de referencias](docs/03-benchmark-referencias.md) | Campspot, Hipcamp, Pitchup, The Dyrt, PiNCAMP; y los competidores chilenos vivos |
| 04 | [MVP y producto](docs/04-mvp-producto.md) | Alcance, esquema de datos, lista de amenidades, stack, criterios de terminado |
| 05 | [Plan de 90 días](docs/05-plan-90-dias.md) | El calendario contra la temporada, fase por fase, con metas duras |
| 06 | [Agenda de reunión](docs/06-agenda-reunion.md) | Las 8 decisiones que hay que cerrar |

Documento base del proyecto: `plan-campings-chile.pdf` (investigación de mercado,
6 modelos de negocio, agosto 2026).

---

## El reloj

| Hito | Fecha | Días desde el 4-sep-2026 |
|---|---|---|
| Cierre de la ventana de venta a anfitriones | 30 de noviembre | 87 |
| Inicio de la temporada | 15 de diciembre | 102 |
| Fin de la temporada | 15 de marzo | 192 |

Se vende entre agosto y noviembre. En diciembre nadie contesta el teléfono.
**Si no hay inventario al 1 de diciembre, se pierden 12 meses.**

---

## Equipo

- **Pablo** — producto y desarrollo
- **Vicente** — comercial, terreno y sociedad
