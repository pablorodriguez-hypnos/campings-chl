# 04 · MVP: alcance, esquema de datos y stack

> El MVP tiene que estar operativo con campings reales el **1 de noviembre de 2026**.
> Todo lo que no sirva para eso, no se construye.

---

## 1. Principio de corte

El MVP son **dos productos que comparten una base de datos**, y se construyen en este orden:

```
1. EL CALENDARIO DEL ANFITRIÓN   ← es el que consigue el inventario
2. LA FICHA PÚBLICA CON RESERVA  ← es el que le demuestra valor inmediato
3. EL BUSCADOR DEL MARKETPLACE   ← es el que monetiza, y solo funciona si 1 y 2 existen
```

Si en noviembre solo alcanzamos a tener 1 y 2, **igual ganamos la temporada**: tenemos 30
calendarios vivos y datos reales. Si construimos 3 primero y no tenemos inventario,
tenemos un sitio vacío. Por eso el orden es innegociable.

---

## 2. Alcance del MVP

### ✅ Entra

**Panel del anfitrión (móvil primero)**
- Onboarding en <15 minutos: nombre, comuna, ubicación en mapa, tipos de sitio, cantidad
  por tipo, tarifas por temporada, servicios, fotos, RUT.
- Calendario de ocupación por tipo de sitio. Vista mes y semana.
- **Alta manual de reserva** — crítico: es el 90% de su realidad (le escriben por WhatsApp
  y la anota). Si esto no es más rápido que su cuaderno, no lo usa.
- Bloqueo de fechas / cierre por temporada.
- Generar link de cobro para el abono (Flow) y marcar reservas como pagadas.
- Aceptar / rechazar solicitudes **desde WhatsApp**, sin entrar a la web.

**Ficha pública y reserva**
- URL propia por camping (`/camping/[slug]`) que el anfitrión comparte por WhatsApp e IG.
- Galería de fotos, descripción, mapa de ubicación, grilla de servicios, tarifas por
  temporada, reglas, política de cancelación, badge de Sello R si tiene RNPST.
- Selector de fechas + personas + tipo de sitio, con **precio total desglosado antes de
  pagar** (obligación legal) y la exclusión del derecho a retracto destacada junto al precio.
- **Solicitud de reserva (request-to-book) con SLA de 2 horas.** No confirmación instantánea.
- Checkout con Flow: cargo de reserva 12% (o abono, según el modo del camping).
- Reseñas verificadas: solo quien reservó y se alojó.

**Buscador del marketplace**
- Búsqueda por destino + fechas + personas + tipo de alojamiento.
- Resultados en **lista + mapa** (split view, tipo Hipcamp).
- Filtros por amenidades (§4).
- Landings por comuna y por tipo, generadas desde la base de datos (base del SEO programático).

**Transversal**
- WhatsApp y email transaccionales: solicitud recibida, confirmación, recordatorio 48h
  antes, post-estadía con pedido de reseña.
- Panel interno de operación (nosotros): campings, reservas, incidencias.
- T&C, política de privacidad, política de cancelación de 3 niveles.
- Analítica instrumentada desde el día 1 (PostHog).

### ❌ No entra (y por qué)

| No construimos | Razón |
|---|---|
| App nativa | El 100% del tráfico del año 1 va a llegar por navegador. PWA como mucho. |
| Channel manager real (API Booking/Airbnb) | Requiere certificación de partner y meses. **iCal import/export cubre el caso real** y va en V1. |
| Boleta electrónica / integración DTE | En modelo agencia, el camping emite la boleta. Nosotros solo facturamos comisión. |
| Módulo de liquidaciones y payouts | Con la mecánica de cargo de reserva no recaudamos el saldo. Ahorra ~3 semanas. |
| Precios dinámicos | Nadie los va a usar el año 1. |
| Mensajería interna | WhatsApp ya existe y funciona. |
| Multi-idioma | El receptivo entra en V1, con Stripe USD. |
| Plano del camping con sitios numerados | Caro y exige que el anfitrión lo mantenga. **V1** — pero el esquema de datos lo soporta desde hoy. |
| Confirmación instantánea | V1, solo para los campings con calendario sincronizado y responsividad probada. |
| Programa de puntos / lealtad | Año 2. |

---

## 3. Esquema de datos — las decisiones que no se pueden deshacer

Estas cuatro decisiones hay que tomarlas bien ahora porque migrarlas después cuesta meses:

**a) La categoría es *alojamiento outdoor*, no "camping".**
```
property (el establecimiento)
  └── unit_type (sitio de carpa · sitio motorhome · domo · cabaña · refugio)
        └── unit (el sitio individual: "Sitio 14, junto al río")
              └── availability / booking
```
Modelar `unit` desde el día 1 aunque en el MVP vendamos por `unit_type` (categoría). Eso
es lo que después habilita el plano del camping sin rehacer nada.

**b) Precio de camping ≠ precio de hotel.**
El precio no es "por unidad por noche". Es:
`base por sitio/noche + cargo por persona adicional sobre N incluidas + cargo por mascota +
cargo por vehículo extra + mínimo de noches`, todo variable por **temporada**
(baja / media / alta / fechas especiales). Si el motor de precios no soporta esto, no
sirve para ningún camping chileno real.

**c) Multi-país desde el esquema.**
`country_code`, `currency`, `timezone`, división administrativa genérica (región/comuna
como niveles, no como columnas fijas). Cuesta un día ahora e imposible después.

**d) Origen de la reserva es un campo de primera clase.**
`booking.source` ∈ {`host_direct`, `marketplace`, `host_link`, `manual`}. **De este campo
depende si cobramos comisión o no.** Es el corazón del modelo de negocio y tiene que ser
auditable, porque es la promesa que le hacemos al anfitrión.

---

## 4. Lista estandarizada de servicios (borrador para validar en las 40 llamadas)

Esta lista **es** el esquema de datos y **es** el filtro. Definirla mal cuesta
re-entrevistar a 100 anfitriones.

**Baños e higiene** — baño privado · baño compartido · ducha con agua caliente · agua
potable · lavadero · descarga de aguas grises (motorhome)

**Servicios del sitio** — electricidad en el sitio · conexión para motorhome · sombra ·
quincho o parrilla propia · mesa · acceso vehicular hasta el sitio · piso de pasto/tierra/ripio

**Del establecimiento** — wifi · señal de celular (sí/parcial/no) · minimarket · venta de
leña · piscina · quincho común · estacionamiento · guardería de equipaje · sala común

**Entorno** — río · lago · playa · bosque nativo · montaña · termas cercanas · sendero desde
el camping

**Reglas** — mascotas · fogatas permitidas · horario de silencio · check-in / check-out ·
apto para niños · apto para grupos grandes

**Accesibilidad** — camino pavimentado / ripio / requiere 4x4 · accesible en silla de ruedas

> Regla: cada servicio es `sí / no / no informado`. **"No informado" no es lo mismo que
> "no"** y nunca debe filtrarse como si lo fuera — es la causa #1 de que un directorio
> pierda credibilidad.

---

## 5. Stack propuesto

| Capa | Elección | Por qué |
|---|---|---|
| Framework | **Next.js 15 (App Router) + TypeScript** | SSR para SEO —que es todo nuestro canal de adquisición—, un solo repo, un solo deploy. |
| UI | **Tailwind + shadcn/ui** | Velocidad. No diseñamos un design system en el año 1. |
| Base de datos | **PostgreSQL en Supabase** | Postgres + auth + storage de fotos + RLS en un solo proveedor. Neon si preferimos separar auth. |
| ORM | **Drizzle** | Migraciones explícitas y tipadas. Prisma también sirve. |
| Hosting | **Vercel** + Cloudflare | |
| Pagos | **Flow.cl** | Un contrato activa Webpay Plus, MACH, Servipag y CajaVecina. 2,89% + IVA, abono 1–3 días. Stripe se agrega en V1 para el receptivo. |
| WhatsApp | **Meta Cloud API** (o 360dialog) | Es la interfaz del anfitrión. No es un extra, es el producto. |
| Email | Resend | |
| Mapas | MapLibre + tiles de Mapbox | |
| Analítica | PostHog | Embudo instrumentado desde el día 1. |
| Errores | Sentry | |

**Regla de oro del stack:** la capa de pagos se diseña como **reemplazable** (interfaz
`PaymentProvider`, no llamadas a Flow esparcidas por el código). El open finance chileno
entra en vigencia en julio-2027 y puede bajar el costo de cobro a ~1%.

---

## 6. UX: qué copiamos, pantalla por pantalla

| Pantalla | Referencia | Qué tomamos |
|---|---|---|
| Home | Hipcamp | Buscador grande sobre foto, destinos destacados, y "colecciones" (con perro, con niños, para motorhome) |
| Resultados | Hipcamp / Pitchup | Split lista + mapa, filtros en panel lateral, precio total visible en la tarjeta |
| Ficha | Hipcamp | Galería arriba, grilla de amenidades con iconos, caja de reserva sticky a la derecha en desktop y fija abajo en móvil |
| Checkout | Pitchup | Desglose explícito: precio total, cargo de reserva que pagas hoy, saldo que pagas en el camping |
| Panel del anfitrión | Campspot / Kampgo | Calendario tipo Gantt, drag & drop, alta de reserva en 3 toques |
| Plano del camping (V1) | Campspot | Imagen del plano con hotspots por sitio |

---

## 7. Criterios de "terminado" del MVP

El MVP está listo cuando un anfitrión que no conocemos puede, **solo desde su teléfono y sin
que lo ayudemos**:

1. Publicar su camping en menos de 15 minutos.
2. Anotar una reserva que le llegó por WhatsApp en menos de 30 segundos.
3. Mandarle a ese cliente un link de pago y ver la plata confirmada.
4. Recibir una solicitud de reserva del marketplace y aceptarla respondiendo un mensaje.

Y un viajero puede buscar en una comuna, filtrar por "con perro" y "ducha caliente", ver el
precio total, y reservar en menos de 90 segundos.

**Nada más que eso. Todo lo demás es V1.**
