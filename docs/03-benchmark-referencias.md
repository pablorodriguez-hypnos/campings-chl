# 03 · Benchmark de referencias

> Investigación propia, septiembre 2026. Complementa el §9 del documento de trabajo con
> lo que falta ahí: el caso que valida exactamente nuestro modelo (Campspot), el
> competidor local que ya está operando (Travana) y el SaaS chileno que ya existe (Kampgo).

---

## 1. La referencia principal: **Campspot** (EE. UU.)

Es el caso que hay que estudiar en detalle, porque es **nuestro modelo ya ejecutado y
validado**:

- Fundada en **2015** como software B2B de gestión para campings, resolviendo que casi la
  mitad de los campings de EE. UU. no tomaba reservas online.
- Lanzó su **marketplace al consumidor en 2020**, sobre el inventario que ya tenía
  digitalizado. Hoy son ~130.000 sitios reservables.
- **USD 17,4 millones de ingresos (2025), ~97 empleados, sin haber levantado capital de
  riesgo.** Valorización estimada USD 52M.

**Su pricing (lo más relevante para nosotros):**
- Sin costo de setup, sin contratos de permanencia, **sin cobro por sitio** — los sitios
  que no se usan no generan cargo.
- El paquete de crecimiento incluye precios dinámicos, POS, integraciones de marketing,
  sitio web propio, analítica y usuarios ilimitados.
- **El fee lo paga el huésped** ("guest-paid booking fee for online reservations").
- Para reservas del marketplace, el operador paga ~10% de comisión + USD 3 por reserva +
  2,5% de procesamiento (≈15,5% total).
- El camping **no puede descontar ni eximir el service fee** al huésped.

**Qué copiar:** la secuencia completa (SaaS → marketplace), el "sin cobro por sitio", el
fee al huésped, y el hecho de que el sitio web del camping *es* la plataforma —lo que
convierte cada reserva "directa" en una reserva del sistema.

**Qué NO copiar:** su soporte (5–7 días de espera es una queja recurrente de operadores) y
la percepción de que el precio sube mientras el valor baja. En Chile el soporte humano por
WhatsApp es nuestro diferenciador.

---

## 2. **Hipcamp** (EE. UU.) — la referencia de producto para el consumidor

- Marketplace de terrenos privados. Serie C, USD 94M levantados. 300.000+ sitios.
- **15% al anfitrión privado, 12,5% si está integrado vía PMS** + 10–15% de service fee al
  huésped. El descuento por integración es el reconocimiento explícito de que **el software
  es más defendible que el marketplace**.
- Todo en un mapa: parques nacionales, granjas, terrenos privados.
- Filtros: ubicación, precio, fechas, y amenidades — ducha solar, fogata, pet-friendly,
  off-grid, baños, wifi, estilo de camping.
- Tres categorías de inventario: sitios de carpa / sitios de RV y van / glamping y cabañas.
- **Ofrecen fotografía gratis al anfitrión** y seguro de hasta USD 1M.

**Qué copiar:** la taxonomía de inventario (las tres categorías son exactamente las que
necesitamos), la lógica de filtros por amenidad, y la fotografía gratis como herramienta de
adquisición. **Qué evitar:** su soporte es solo chatbot y tiene rating F en BBB.

---

## 3. **Pitchup.com** (Reino Unido) — la mecánica de cobro

- OTA de camping europea, fundada 2009. 3.800+ campings en 59 países.
- **15% de comisión, incluida en el precio que ve el visitante** (2,5% recuperable para
  hosts con IVA en UK).
- **La mecánica clave:** Stripe cobra la tarjeta del cliente, **envía el 15% de depósito a
  Pitchup y el saldo directo al anfitrión** en la fecha de vencimiento.
- Presente en Chile, pero con inventario mínimo (1 camping reservable). Es nuestro
  competidor natural si deciden entrar en serio: **ya tienen el producto correcto.**

**Qué copiar:** exactamente esa mecánica de cobro. Es la base de la Opción A de
`02-modelo-de-negocio.md` y calza perfecto con la conducta chilena del abono.

---

## 4. **The Dyrt** (EE. UU.) — el modelo alternativo

- Directorio + membresía al consumidor. USD 22,3M levantados, 30M de visitas anuales.
- **0% al lado de la oferta.** Monetiza con membresía PRO (mapas offline, descuentos).

**Por qué importa:** demuestra que se puede monetizar el lado de la demanda sin tocar al
anfitrión — la mejor respuesta posible al problema de desintermediación. Es nuestro plan B
si las 40 llamadas revelan que los anfitriones no aceptan comisión de ningún tipo.

---

## 5. Europa: **PiNCAMP**, **ACSI Eurocampings**, **camping.info**

- **ACSI Eurocampings**: desde 1998, 9.000+ campings europeos en 12 idiomas, 17M de
  visitantes al año, reservable desde 2016. ACSI y camping.info se aliaron y comparten
  software.
- **PiNCAMP**: desde enero-2024 pertenece conjuntamente a ADAC, ANWB y TCS —los clubes
  automovilísticos alemán, holandés y suizo, que juntos reúnen 27 millones de socios.

**La lección estratégica:** en Europa el camping se distribuye a través de instituciones con
membresía masiva, no a través de performance marketing. **El equivalente chileno son las
cajas de compensación (Los Andes, La Araucana), los clubes de motorhome y 4x4, las tiendas
outdoor y las cámaras de turismo comunales.** Una alianza de ese tipo resuelve el problema
del CAC de una manera que Google Ads jamás va a resolver. Vale más que tres meses de SEO.

---

## 6. Chile: el mapa competitivo actualizado

### Travana (travana.cl) — **competidor activo, no referencia**

Vicente lo trajo como referencia. Hay que mirarlo de nuevo, porque está vivo y corriendo:

- Marketplace peer-to-peer de **campers/vans + campings y glamping**, Atacama a Patagonia.
- **550+ listings.** Mapa con filtros por zona (Patagonia, Los Lagos, Valle de Elqui).
- Publicar es **gratis** para dueños de camper y de camping. "Pago protegido" que se libera
  al retirar el vehículo → cobran fee de transacción, sin tarifa publicada.
- Flujo: explorar → seleccionar fechas y **enviar solicitud al anfitrión** (request-to-book,
  igual que lo que propone el documento) → viajar.
- Rango de precios publicado: campers $8.000–$300.000/noche; campings $8.000–$85.000.
- Interfaz en español e inglés. El footer dice **"sociedad en constitución"** → son
  recientes y están en la misma etapa que nosotros.

**Lectura:** su centro de gravedad es el arriendo de campers (ticket alto, poca oferta,
ellos capturan buen margen); los campings parecen ser inventario complementario y
autogestionado. **Nuestro ángulo diferenciador sigue disponible: el calendario vivo y la
verificación en terreno.** Pero hay que asumir que estamos en una carrera, no en un mercado
vacío.

**Acción:** reservar algo en Travana esta semana. Hacer el flujo completo como cliente.
Aprender más en una reserva que en un mes de análisis.

### Kampgo (kampgo.cl) — el SaaS chileno que ya existe

- Plataforma chilena de gestión para **"campings, cabañas y hoteles boutique"**.
- Calendario tipo Gantt con drag & drop, caja diaria con arqueo por turno, tarifas por
  temporada, promociones, cotizaciones, **sitio de reservas propio + widget embebible**.
- **No tiene marketplace ni directorio público.** No publica precios, ni clientes, ni
  testimonios, ni fecha de lanzamiento → se ve muy temprano o con poca tracción.

**Lectura:** alguien más ya vio la mitad del negocio (el SaaS) pero no la otra mitad (el
marketplace sobre el inventario). Es exactamente la razón por la que el modelo híbrido es
el correcto: **el SaaS solo tiene techo, y el marketplace solo no tiene inventario.**

### El resto (del documento base, confirmado)

| Actor | Estado | Lectura |
|---|---|---|
| Rutero | Muerto, dominio abandonado | Habría que hablar con César Olivos. Vale más que tres meses de análisis. |
| Glampi | Activo, modelo operador (M5) | Validó que hay demanda de glamping. No compite con nosotros. |
| Klimber Camp | Sin actividad | Un directorio sin transacción no retiene. |
| campingsenchile.cl y similares | Cascarones de SEO | **Oportunidad, no barrera.** El SEO del nicho está ocupado por sitios muertos. |
| Booking.com | 69 glampings en Chile, 15%–23% de comisión | Fuerte en cabañas formalizadas, no sabe modelar "sitio de carpa". |
| Airbnb | Domina domos y tiny houses | No tiene producto de sitio de camping. |
| Pasesparques.cl (CONAF) | 61 parques | **Infraestructura, no competencia.** Una alianza acá sería enorme. |

---

## 7. Síntesis: qué copiamos de cada uno

| De | Copiamos |
|---|---|
| **Campspot** | La secuencia SaaS→marketplace. Software gratis sin cobro por sitio. Fee al huésped. |
| **Pitchup** | La mecánica de cobro: el huésped paga online solo nuestra comisión, el saldo va al anfitrión. |
| **Hipcamp** | La taxonomía de inventario, los filtros de amenidades, la fotografía gratis, el mapa. |
| **The Dyrt** | El plan B: monetizar la demanda sin tocar al anfitrión. Y el contenido como activo. |
| **PiNCAMP / ACSI** | La distribución vía instituciones con membresía masiva en vez de ads. |
| **Travana** | Qué NO hacer: quedarse en listings autogestionados sin verificación ni calendario. |

---

### Fuentes

- [Campspot — service fee](https://www.campspot.com/about/service-fee) · [pricing](https://software.campspot.com/pricing/) · [historia y revenue](https://getlatka.com/companies/campspot.com)
- [Comparación de costos reales Campspot vs Hipcamp vs Airbnb](https://northernstay.com/campground-booking-platform-comparison)
- [Hipcamp](https://www.hipcamp.com/en-US)
- [Pitchup — join](https://www.pitchup.com/join/) · [FAQ proveedores](https://www.pitchup.com/en-us/supplier2/faq/)
- [ACSI Eurocampings](https://www.eurocampings.co.uk/) · [ACSI + camping.info](https://www.acsi.eu/en/news/acsi-and-campinginfo-join-forces/) · [PiNCAMP for business](https://business.pincamp.com/es/)
- [Travana (Chile)](https://www.travana.cl/) · [Kampgo (Chile)](https://kampgo.cl/)
