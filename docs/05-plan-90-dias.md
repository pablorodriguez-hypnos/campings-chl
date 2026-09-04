# 05 · Plan de 90 días

> Hoy es **4 de septiembre de 2026**.
> Faltan **87 días** para que se cierre la ventana de venta (30 de noviembre).
> Faltan **102 días** para que parta la temporada (15 de diciembre).
>
> El principio que ordena todo el plan: **validación y construcción corren en paralelo,
> no en secuencia.** Hacerlo en secuencia nos deja lanzando en enero, y en enero nadie
> contesta el teléfono.

---

## Vista general

```
        SEMANA   1  2  3  4 │ 5  6  7  8 │ 9 10 11 12 13 │ 14 →
                 SEPTIEMBRE │  OCTUBRE   │   NOVIEMBRE   │ DIC
VICENTE (calle)  ███████████│████████████│███████████████│ operar
  catastro ──────███████    │            │               │
  40 llamadas ───    ███████│            │               │
  5 cartas ──────────    ███│███         │               │
  viaje terreno ─────────   │  ██████    │               │
  onboarding ────────────   │      ██████│███████████    │
PABLO (producto) ███████████│████████████│███████████████│ soportar
  esquema+auth ──███████    │            │               │
  calendario ────    ███████│███         │               │
  ficha+checkout ─────      │   █████████│               │
  buscador+mapa ──────      │            │███████        │
  SEO+contenido ──────      │            │    ███████    │
AMBOS
  legal/sociedad ██████     │            │               │
  contenido ──────    ██████│████████████│███████████████│
```

---

## Fase 0 · Esta semana (4 – 10 de septiembre)

**Decisiones (hoy, en la reunión)** — ver `06-agenda-reunion.md`.

| # | Tarea | Quién |
|---|---|---|
| 1 | Cerrar: modelo de monetización, cabeza de playa, nombre y reparto societario | Ambos |
| 2 | Registrar dominio y handles de redes sociales | Pablo |
| 3 | Abrir la planilla del catastro con los campos del Anexo A y cargar los primeros 20 | Vicente |
| 4 | Hacer una reserva real en Travana, de principio a fin, como cliente | Vicente |
| 5 | Escribir a César Olivos (Rutero) y a los fundadores de Glampi por LinkedIn | Vicente |
| 6 | Publicar la landing de captura con lista de espera (1 día de trabajo) | Pablo |
| 7 | Cotizar abogado para T&C + contrato de anfitrión + pacto de accionistas | Vicente |

---

## Fase 1 · Semanas 1–4 (septiembre) — validar y cimentar

### Vicente — el trabajo que decide si el negocio existe

- **Catastro de 300 campings** de la zona objetivo. Fuentes: registro.sernatur.cl, Google
  Maps por comuna, Instagram por ubicación, directorios existentes, grupos de Facebook,
  cámaras de turismo comunales. Campos según Anexo A del documento base.
- **40 llamadas de descubrimiento** con el guion del Anexo B. **No vender nada.** Medir
  las tres cosas que importan:
  1. Ocupación en abril–junio *(si dicen "vacío", hay negocio; si dicen "lleno", no)*
  2. Dolor administrativo *(reservas dobles, no-shows, cuánto perdió)*
  3. Disposición a pagar *(anotar el número textual)* y comisión que le parece justa
- **5 cartas de intención** de campings pioneros que se comprometen a usar el sistema esta
  temporada y a participar del diseño. No hace falta que paguen (el software es gratis):
  lo que firman es **exclusividad de atención y compromiso de uso**, y nos dan sus datos
  reales para cargar.

### Pablo — construir lo que no depende de las llamadas

- Repositorio, CI, entorno de staging.
- **Esquema de datos completo** (§3 de `04-mvp-producto.md`). Esta es la pieza crítica.
- Auth y multi-tenant.
- Landing de captura publicada (semana 1).
- Primeras 20 fichas de camping cargadas desde el catastro, ya renderizando como páginas
  públicas. **Sirven de argumento de venta: "ya te tenemos publicado, gratis".**

### Ambos

- Constituir la SpA (después de acordar el pacto de accionistas, no antes).
- Encargar T&C, contrato de anfitrión y política de privacidad al abogado.
- Marca en INAPI (clases 39 y 42).

### 🚦 Semáforo de fin de septiembre

| Resultado de las 40 llamadas | Acción |
|---|---|
| ≥5 cartas + ocupación baja confirmada en abril–junio | **Adelante con todo el plan.** |
| Interés pero nadie confirma nada | Seguir, pero recortar el marketplace del alcance de esta temporada. Solo software. |
| Dicen que están llenos todo el año | **Cambiar la cabeza de playa**, no el modelo. |
| Nadie contesta ni le interesa | **Parar.** Nos ahorramos $13M y un año. |

---

## Fase 2 · Semanas 5–8 (octubre) — construir y salir a terreno

### Pablo
- Calendario del anfitrión funcionando end-to-end.
- Alta manual de reservas (el flujo que tiene que ser más rápido que su cuaderno).
- Ficha pública + solicitud de reserva + checkout con Flow.
- Bot de WhatsApp para aceptar/rechazar.
- **Onboarding manual de los 5 pioneros: cargamos nosotros sus datos, en videollamada.**
  La activación lo es todo.

### Vicente
- **Viaje de terreno: 5 días, 25 campings visitados y fotografiados.** Ofrecer las fotos
  gratis y sin compromiso — eso compra la relación (es lo que hace Hipcamp).
- Cerrar 20 campings con el acuerdo de una página.
- **El encuadre de venta es el que resuelve el problema del huevo y la gallina:**
  > *"No te pido tu enero. Te pido tus fines de semana de mayo, que hoy están vacíos."*
- Contacto con cámaras de turismo comunales y Sernatur regional. Un convenio con una cámara
  puede dar 40 campings de una vez.

---

## Fase 3 · Semanas 9–13 (noviembre) — llenar y publicar

### Pablo
- Buscador + mapa + filtros por amenidades.
- Landings por comuna y por tipo (SEO programático) — apuntar a 150 URLs publicadas.
- Reseñas verificadas.
- Emails y WhatsApp transaccionales completos.
- Hardening: qué pasa si el anfitrión no responde, si el pago falla, si hay sobreventa.

### Vicente
- Onboarding de campings hasta llegar a **25–40 con calendario vivo**.
- Campaña de reactivación de los que dijeron "hablemos en octubre".
- Alianzas: tiendas outdoor, clubes de motorhome, cajas de compensación.

### Ambos
- **Lanzamiento privado: 1 de noviembre.** Público: 15 de noviembre.
- Campaña de contenido antes de la temporada: "los 12 campings con piscina cerca de
  Santiago", "camping con perro en Los Ríos". Formato listicle con fotos propias.

---

## Fase 4 · Diciembre – marzo — operar la temporada

Nadie construye funcionalidades nuevas en temporada. Se opera, se soporta y se mide.

- Soporte por WhatsApp, 9–21h, humano.
- Iterar el flujo de confirmación (ahí va a estar el 80% de los problemas).
- Protocolo escrito de crisis: "el camping no existe / está cerrado / cobró de más".
  Relocalización + reembolso. Provisionar 1% del GMV.
- **Marzo: entrevistar a los 100% de los anfitriones activos.** Esa conversación decide
  el año 2.

---

## Metas duras al 1 de marzo de 2027

| Métrica | Meta | Alarma |
|---|---|---|
| **Campings con calendario actualizado en los últimos 7 días** | **30** | <12 |
| Campings publicados en el marketplace | 60 | <30 |
| GMV total procesado por el sistema (directo + originado) | $400.000.000 | <$120.000.000 |
| Reservas originadas por nosotros | 300 | <100 |
| Tasa de aceptación de solicitudes | >80% | <65% |
| Tiempo mediano de respuesta del anfitrión | <90 min | >4h |
| Retención de anfitriones a la temporada siguiente | >70% | <50% |
| Tráfico orgánico como % del total | >55% | <30% |
| Fichas publicadas / URLs indexadas | 400 | <150 |

---

## Reglas de operación del equipo

1. **Reunión semanal fija de 45 minutos.** Mismo día, misma hora. Tres preguntas: qué
   avanzó, qué está trabado, qué decidimos.
2. **Un tablero público entre los dos** con el estado de cada camping del pipeline.
3. **Ningún desarrollo nuevo sin un anfitrión que lo haya pedido**, después de la semana 4.
4. **Nada se lanza en enero.** Si no está el 1 de diciembre, va para la temporada siguiente.
5. **Todo lo que se aprende en una llamada se escribe** en el mismo repositorio. El catastro
   y las notas de entrevistas son el activo más valioso de los primeros 90 días.
