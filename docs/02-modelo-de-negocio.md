# 02 · Modelo de negocio, pricing y números

> Todas las cifras en CLP. Supuestos base tomados del documento de trabajo y marcados como
> tales. **Hay que re-validarlos con las 40 llamadas antes de comprometer capital.**

---

## 1. Supuestos de modelación

| Variable | Valor | Origen |
|---|---|---|
| Ticket promedio por reserva (GMV) | $90.000 (3 noches × $30.000) | Doc §2 — *supuesto* |
| Costo de procesamiento de pago | 3,5% del monto procesado | Flow 2,89% + IVA ≈ 3,44% |
| Contracargos y reembolsos | 0,7% del monto procesado | Doc §1.4 — *supuesto* |
| Costo de soporte por reserva | $800 (≈8 min) | Doc §1.4 — *supuesto* |
| Estacionalidad | 70% del GMV entre 15-dic y 15-mar | Doc §3 |
| GMV por camping por temporada | $15–25 millones | Doc §2.4 — *supuesto, a validar* |

---

## 2. La estructura propuesta

Tres capas, con un principio que las gobierna:
**nunca le cobramos al anfitrión por un cliente que él trajo.**

```
CAPA 1 · SOFTWARE — gratis, para siempre, condicionado a estar publicado
   Calendario, alta manual de reservas, link de cobro, ficha pública,
   confirmaciones por WhatsApp.
   Precio al anfitrión: $0.
   Por qué: es el caballo de Troya. Su dolor diario no es la falta de clientes
   en enero, es el caos administrativo. Y a cambio nos da la única cosa que
   nadie más tiene: su disponibilidad real, actualizada.

CAPA 2 · RESERVAS QUE ÉL ORIGINA (su WhatsApp, su Instagram, su web)
   Comisión: 0%. Siempre. Está en el contrato desde el día uno.
   Ingreso para nosotros: $0 directo. El valor es el dato y la retención.

CAPA 3 · RESERVAS QUE NOSOTROS ORIGINAMOS (buscador del marketplace)
   El huésped paga online un CARGO DE RESERVA = 12% del total, imputable
   al precio. Ese cargo es nuestro ingreso. El saldo (88%) lo paga en el
   camping, directo al anfitrión.
   Ingreso neto: ~$9.500 por reserva.
```

**Fijo: $0. Variable: pagado por el huésped al momento de reservar. Solo sobre lo que
nosotros traemos.** Es exactamente lo que se acordó el viernes, con la mecánica de cobro
que hace que los números funcionen.

### Cómo se le explica al anfitrión (una frase)

> *"El sistema es gratis y es tuyo. Tus clientes de siempre reservan por tu link y no te
> cobramos nada, nunca. Y si además te mandamos gente en abril, esa persona paga online un
> 12% que se descuenta de lo que te paga a ti — tú no giras nada, no esperas nada, y llega
> con la reserva ya comprometida."*

---

## 3. Unit economics — comparación de mecánicas de cobro

Por reserva de $90.000:

| # | Mecánica | Ingreso bruto | Monto procesado | Costos | **Neto** | **% GMV** |
|---|---|---|---|---|---|---|
| **A** | **Cargo de reserva 12% al huésped, imputable (Pitchup)** | $10.800 | $10.800 | $1.254 | **$9.546** | **10,6%** |
| A- | Cargo de reserva 10% | $9.000 | $9.000 | $1.178 | $7.822 | 8,7% |
| A+ | Cargo de reserva 15% | $13.500 | $13.500 | $1.367 | $12.133 | 13,5% |
| B' | Recaudo del abono 40%, comisión 12% retenida | $10.800 | $36.000 | $2.312 | $8.488 | 9,4% |
| B | Recaudo total online, comisión 12% al anfitrión | $10.800 | $90.000 | $4.580 | $6.220 | 6,9% |
| V | Anfitrión 0%, fee **adicional** de 8% al huésped | $7.200 | $43.200 | $2.614 | $4.586 | 5,1% |
| M1 | Modelo del documento: comisión 10%, recaudo total | $9.000 | $90.000 | $4.580 | $4.420 | 4,9% |

**La opción A rinde más del doble que el modelo del documento y más del doble que la
lectura literal de lo acordado el viernes**, con menos trabajo operativo y menos riesgo
regulatorio. Esa es la recomendación.

### Por qué 12% y no 10% ni 15%

- Pitchup cobra 15% y Hipcamp 15%; Booking cobra 15% y hasta 23%. **12% se ve barato en el
  pitch de venta** y deja espacio para subir en el año 2.
- A 10% el neto por reserva ($7.822) es un 18% menor y no compra nada estratégicamente:
  el anfitrión no distingue entre 10% y 12% cuando la comisión es sobre inventario que
  hoy está vacío.
- **Los primeros 20 anfitriones entran con 0% las primeras 20 reservas** (recomendación del
  documento §1.6). Es un descuento de adquisición, no un precio.

---

## 4. Lo que NO monetizamos en el año 1 (y por qué)

| Fuente | Por qué no ahora |
|---|---|
| Suscripción SaaS | Cobrar por el software mata el "gratis" que es todo nuestro argumento de entrada. Se evalúa en la temporada 2 con la base instalada. |
| Fee de procesamiento sobre reservas directas | El margen es casi nulo (cobrar 3,9% cuando la pasarela cuesta 3,5%) y envenena la promesa de "0% en lo tuyo". |
| Destacados / publicidad | Requiere 200+ campings y tráfico medible. Año 2. |
| Seguros, fotografía, formalización asistida | Buenos productos, pero son distracción operativa en el año 1. La inscripción asistida en Sernatur sí se ofrece **gratis**, como herramienta de venta. |

---

## 5. Proyección de la temporada 1 (dic-2026 → mar-2027)

**Esta temporada no es de ingresos. Es de aprendizaje e inventario.** Hay que decirlo
explícitamente hoy para no medirnos contra la vara equivocada en marzo.

| Escenario | Campings activos | Reservas originadas | GMV originado | **Ingreso neto** |
|---|---|---|---|---|
| Conservador | 20 | 150 | $13.500.000 | **$1.432.000** |
| Base | 30 | 300 | $27.000.000 | **$2.864.000** |
| Agresivo | 40 | 600 | $54.000.000 | **$5.728.000** |

A esto se suma el **GMV directo procesado por el sistema** (las reservas propias del
anfitrión), que no genera ingreso pero es la métrica que de verdad importa: si 30 campings
procesan $15M cada uno, son **$450 millones de GMV corriendo por nuestra infraestructura**.
Ese número es el que abre la puerta a Corfo Semilla Expande, a una ronda ángel, y
eventualmente a los productos financieros de M6.

### La métrica que gobierna todo

No es el GMV ni las reservas. Es:

> **Campings con el calendario actualizado en los últimos 7 días.**

Si ese número es 30 al 1 de marzo, tenemos un activo que nadie más en Chile tiene.
Si es 5, no tenemos nada, da igual cuántas reservas hubo.

---

## 6. Presupuesto real de los primeros 12 meses

Escenario bootstrapped: Pablo desarrolla, Vicente vende, ninguno de los dos toma sueldo.

| Ítem | 12 meses | Nota |
|---|---|---|
| Constitución SpA + inicio de actividades | $150.000 | Empresa en un Día |
| Contabilidad externa | $1.440.000 | ~$120.000/mes |
| Legal (T&C, contrato anfitrión, privacidad) | $1.800.000 | No usar plantilla genérica |
| Marca en INAPI (clases 39 y 42) | $260.000 | |
| Dominio + infra (Vercel, Supabase, Cloudflare, Mapbox, Resend) | $900.000 | ~$75.000/mes |
| WhatsApp Business API (plantillas, temporada) | $700.000 | Meta Cloud API |
| Viajes de terreno y fotografía (3 viajes) | $2.500.000 | Bencina, alojamiento, comida |
| Contenido y SEO (redacción freelance) | $1.500.000 | ~30 guías |
| Meta Ads de prueba (medir CPL, no adquirir) | $600.000 | |
| Provisión de incidentes y reembolsos | $1.000.000 | |
| Buffer 20% | $2.170.000 | |
| **TOTAL** | **≈ $13.020.000** | **≈ $6.510.000 por socio** |

Comparar con los $164.000.000 que el documento estima para M3: la diferencia completa es
que nosotros ponemos el desarrollo. **No necesitamos levantar capital para empezar.**

### Ruta de financiamiento (opcional, no bloqueante)

1. **Mes 3** — Corfo Semilla Inicia (hasta $15M). Requiere SpA con menos de 18 meses de
   inicio de actividades → **razón adicional para constituir ya, pero no antes de haber
   definido el pacto de accionistas.**
2. **Mes 15 (marzo-2027)** — Corfo Semilla Expande (hasta $45M) con datos de temporada 1.
3. **Mes 18–22** — ronda ángel, si y solo si los números de la temporada 1 la justifican.

Regla del documento que hay que respetar: **levantar en marzo, con los datos frescos, nunca
en octubre.**

---

## 7. Decisiones tributarias y legales que condicionan el código

Estas hay que cerrarlas con un tributarista **antes de escribir el checkout**, no después:

| Decisión | Recomendación | Impacto en el producto |
|---|---|---|
| Modelo agencia vs. merchant | **Agencia.** El camping emite boleta al huésped; nosotros facturamos comisión (afecta a IVA 19%). | Solo necesitamos emitir DTE por nuestra comisión → **no necesitamos integración de boleta electrónica en el MVP**. Ahorra 2 semanas. |
| Quién recauda | Solo el cargo de reserva (12%). El saldo no pasa por nosotros. | No hay módulo de liquidaciones ni tesorería en el MVP. Ahorra 3 semanas. |
| Verificación tributaria de anfitriones | Obligatoria desde 1-ene-2026 para plataformas de intermediación. | Campo obligatorio de RUT + verificación de inicio de actividades en el onboarding. |
| RNPST de Sernatur | Exigirlo para publicar, con 90 días de gracia y ayuda para inscribirse (es gratis, 5 días hábiles). | Campo + badge "Sello R" en la ficha. |
| Derecho a retracto | Excluirlo para el cargo de reserva no reembolsable, con advertencia destacada **junto al precio**. | Componente de UI obligatorio en el checkout. |
| Precio total antes del pago | Obligatorio (Reglamento de Comercio Electrónico). | Nada de fees que aparecen al final. El desglose va desde el primer paso. |
| Exportador de servicios (exención IVA a turistas extranjeros) | Evaluar en V1, cuando entremos al receptivo. | Ventaja de 19% en el segmento internacional. No es del MVP. |

---

## 8. El foso: por qué esto no lo copia cualquiera

Honestamente, el software no es defendible: cualquiera hace un calendario. Lo defendible es:

1. **El calendario vivo de N campings.** Es un activo que se construye anfitrión por
   anfitrión, en terreno, y no se puede comprar ni scrapear. Es exactamente lo que Hipcamp
   reconoce al cobrar menos a quien está integrado vía PMS.
2. **La base de datos verificada de la oferta.** 800 campings con servicios, tarifas y
   fotos propias. Travana tiene 550 listings pero autogestionados, sin verificación en
   terreno.
3. **El contenido y el SEO.** Tarda 12–18 meses en madurar, y por eso hay que empezarlo el
   mes 1 aunque no sirva hasta el mes 12. Es la sinergia más importante del documento base.
4. **La relación.** El anfitrión que te dejó entrar a fotografiar su camping y a quien le
   arreglaste el calendario no te cambia por 2 puntos de comisión.

Ninguna de las cuatro se construye escribiendo código. Las cuatro se construyen en
noviembre, en terreno, o no se construyen.
