# 01 · Análisis y diagnóstico

> Lectura crítica del documento de trabajo (`plan-campings-chile.pdf`, ago-2026) y de los
> next steps acordados en la reunión del 29-ago-2026, más investigación propia de referencias.
> Fecha: 4 de septiembre de 2026.

---

## 1. Qué es realmente este negocio

Despojado de la envoltura, el negocio es este:

**En Chile hay ~2.000 campings que operan con cuaderno, WhatsApp y transferencia.
Nadie tiene la disponibilidad real de ninguno de ellos. El que la tenga, manda.**

Todo lo demás —el marketplace, el mapa, los filtros, la app— son consecuencias de haber
resuelto eso. No al revés. Este es el punto que más se subestima y el que define el orden
de construcción.

El documento base llega a la misma conclusión por otro camino (recomienda M3, híbrido
SaaS→Marketplace) y **estoy de acuerdo con esa recomendación**. Mi aporte no es
contradecirla sino: (a) corregir tres cosas donde el documento se queda corto,
(b) resolver la tensión entre esa recomendación y el modelo que acordaron el viernes
pasado, y (c) bajar todo a un MVP y un calendario que calcen con la temporada que
empieza en 102 días.

---

## 2. Evaluación del documento base

### Lo que está bien y hay que tomar tal cual

| Punto | Por qué es correcto |
|---|---|
| El CAC pagado no cierra | La aritmética es irrefutable: contribución de ~$4.400–$9.500 por reserva contra un CAC de Google de $20.000–$50.000. **No hay versión de este negocio que se financie con Google Ads.** |
| Estacionalidad brutal (~70% en 4 meses) | Define el calendario completo del proyecto. Se vende ago–nov o se pierde un año. |
| El anfitrión real no es el que imaginamos | 45–70 años, cuaderno, cuenta RUT, WhatsApp. Todo el diseño de producto sale de acá. |
| Empezar con *request-to-book*, no confirmación instantánea | Es la única forma de partir sin integraciones. Correcto. |
| Resolver el abono parcial (30–50%) | Es la conducta instalada. Obligar a pagar 100% online mata la venta. |
| Rutero ya lo intentó y murió | El dato más valioso del documento. Repetir M1 puro es apostar con las mismas cartas. |
| Definir la categoría como *alojamiento outdoor*, no "camping" | Multiplica el mercado 5–8x y desestacionaliza. Afecta el nombre de marca y el esquema de datos. |
| No usar split payments | Correcto. La infraestructura chilena para eso es mala y complica lo tributario. |

### Dónde el documento se queda corto

**a) El presupuesto asume que hay que pagar desarrolladores. En nuestro caso no.**
El documento estima M3 en ~$164.000.000 a 24 meses, de los cuales $79M son dos
desarrolladores. Pablo es el desarrollador. El presupuesto real de los primeros 12 meses
está más cerca de **$13.000.000** (detalle en `02-modelo-de-negocio.md` §6). Esto cambia
por completo la conversación: no necesitamos levantar capital para empezar, y eso a su vez
nos permite tomarnos una temporada de aprendizaje sin presión de inversionistas.

**b) Subestima que el reloj ya está corriendo.**
El documento propone un protocolo de validación de 3 semanas y luego un MVP de 10–12
semanas. Sumado, eso nos deja lanzando en **diciembre**, es decir, tarde: en diciembre el
anfitrión ya está en temporada y no contesta el teléfono. La ventana de venta se cierra el
**30 de noviembre (87 días)** y la temporada parte el **15 de diciembre (102 días)**.
El plan tiene que ejecutar validación y construcción **en paralelo**, no en secuencia.

**c) Falta el análisis del competidor local que ya está operando.**
El documento menciona el "cementerio" (Rutero, Klimber, directorios vacíos) pero es de
agosto y no cubre a **Travana** —que Vicente mismo puso como referencia— ni a **Kampgo**.
Travana no es una referencia: es un competidor vivo con 550+ listings. Detalle en
`03-benchmark-referencias.md`.

---

## 3. Los next steps del viernes pasado: evaluación honesta

### Next step 1 — "Sistema de reservas gratis, condicionado a entrar al marketplace. Comisión fija 0; solo comisión variable pagada por el cliente."

**El instinto es correcto y es la mejor idea que salió de esa reunión.** Coincide con la
recomendación del documento (M3) y con el caso de éxito internacional más relevante que
encontré: **Campspot** (EE.UU.) —partió en 2015 como software B2B para campings, lanzó su
marketplace al consumidor en 2020 y llegó a **USD 17,4M de ingresos sin levantar un peso
de capital de riesgo**. Es literalmente la jugada que están proponiendo, ya ejecutada y
validada.

Pero la formulación tiene **dos problemas que hay que resolver hoy**, antes de escribir código:

**Problema 1 — "comisión variable pagada por el cliente" no cierra los números si el fee va *encima* del precio.**

Corrí las cuentas con los supuestos del documento (ticket $90.000, procesamiento 3,5%,
contracargos 0,7%, soporte $800/reserva):

| Modelo | Ingreso bruto | Monto procesado | **Neto por reserva** | % del GMV |
|---|---|---|---|---|
| Anfitrión 0%, huésped paga fee **adicional** 5% | $4.500 | $40.500 | **$1.999** | 2,2% |
| Anfitrión 0%, huésped paga fee **adicional** 8% | $7.200 | $43.200 | **$4.586** | 5,1% |
| Anfitrión 0%, huésped paga fee **adicional** 10% | $9.000 | $45.000 | **$6.310** | 7,0% |

Con un fee de 5% no hay negocio. Con 10% sí lo hay, pero abre el **problema de arbitraje**:
en Chile el teléfono del camping está a un click de distancia en Google Maps, y el
anfitrión —que paga 0%— no tiene ningún incentivo para rechazar la reserva directa.
El huésped compara, ve que reservando por WhatsApp se ahorra $9.000, y llama. La fuga no
es del 50% que estima el documento: es casi total.

**Problema 2 — ninguna de las referencias que queremos copiar cobra 0% al anfitrión.**

| Plataforma | Anfitrión paga | Huésped paga |
|---|---|---|
| Hipcamp | 15% (12,5% si está integrado vía PMS) | 10–15% de service fee |
| Campspot | 10% de comisión de marketplace + USD 3 + 2,5% de procesamiento | booking fee variable |
| Airbnb | 15,5% host-only | 0% desde oct-2025 |
| Pitchup | 15% (incluido en el precio que ve el visitante) | 0% adicional |
| Booking.com | 15% estándar, hasta 23%+ | 0% |

El "0% al anfitrión" es un **argumento de adquisición excelente y una política de
monetización imposible**. Hay que ser precisos sobre cuál de las dos cosas es, porque el
documento advierte —con razón— que el error #5 que hunde este tipo de proyecto es que el
anfitrión se sienta traicionado cuando la comisión aparece después.

### La solución: el mecanismo de Pitchup

Hay una forma de tener las tres cosas a la vez —comisión fija 0, el huésped pagando, y
márgenes que funcionan— y es la que usa Pitchup en Reino Unido:

> **El huésped paga online solo un "cargo de reserva" equivalente al 10–12% del total.
> Ese pago ES nuestro ingreso. El saldo lo paga en el camping, directo al anfitrión.**

Lo que esto resuelve, todo junto:

1. **El margen.** Solo procesamos nuestra propia comisión, no el GMV completo. El costo de
   pasarela pasa de 3,5% del GMV a 0,4% del GMV.

   | Mecanismo | Neto por reserva | % del GMV |
   |---|---|---|
   | **A · Cargo de reserva 12% (Pitchup)** | **$9.546** | **10,6%** |
   | B · Recaudo total, comisión 12% al anfitrión | $6.220 | 6,9% |
   | B' · Recaudo del abono 40%, comisión 12% retenida | $8.488 | 9,4% |
   | Fee adicional al huésped de 8% | $4.586 | 5,1% |

2. **El arbitraje.** El cargo de reserva es **imputable al precio total**: el huésped paga
   exactamente lo mismo que si llamara por WhatsApp. No hay nada que arbitrar. Quien
   absorbe económicamente la comisión es el anfitrión (recibe el total menos el cargo),
   pero nunca gira plata ni espera una liquidación. Psicológicamente es gratis.

3. **La operación.** No hay liquidaciones, no hay float, no hay tesorería, no hay
   "¿cuándo me pagas?". Esto elimina probablemente el 40% del trabajo operativo del año 1
   y una fuente enorme de fricción con el anfitrión.

4. **Lo tributario.** Es el *modelo agencia* que el documento recomienda en §7.2: el camping
   emite boleta al huésped por el alojamiento; nosotros emitimos factura por nuestra
   comisión. Solo facturamos comisión. Muchísimo más simple y menos riesgoso.

5. **El abono.** El cargo de reserva *es* el abono/garantía que el anfitrión quiere.
   Le llega un huésped que ya puso plata. Ese es exactamente su dolor con los no-shows.

**Trade-off que hay que aceptar:** perdemos el "pago protegido" como argumento de confianza
al viajero, y perdemos el control del dinero como palanca sobre el anfitrión. Mi propuesta
es partir así de todas formas (velocidad y simplicidad ganan en el año 1) y agregar el
recaudo completo como **opción** en V1, para los anfitriones y viajeros que lo quieran.

### Next step 2 — "Copiaremos la página a partir de una exitosa en EE. UU. y Europa. Mapa del camping y filtros por amenidades."

De acuerdo con el enfoque. Dos precisiones importantes:

- **"Mapa" son dos cosas distintas y solo una va en el MVP.**
  El *mapa de descubrimiento* (geográfico, tipo Hipcamp: resultados en lista + mapa) es
  barato y va en el MVP. El *plano del camping* (los sitios numerados, elegir el sitio 14
  junto al río, tipo Campspot) es caro: exige modelar inventario sitio por sitio y que el
  anfitrión mantenga ese plano. **Va en V1, no en el MVP** — pero el esquema de datos se
  diseña desde hoy para soportarlo, porque migrarlo después es carísimo.
- **Los filtros por amenidades son en realidad el esquema de datos.** La lista
  estandarizada de servicios (ducha caliente, electricidad, sombra, mascotas, acceso
  vehicular al sitio, quincho, río/playa, señal celular, leña) hay que definirla **antes**
  de cargar el primer camping. Si se define mal, hay que re-entrevistar a 100 anfitriones.
  Propuesta concreta en `04-mvp-producto.md`.

### Next step 3 — "Pablo: MVP web. Vicente: sociedad, channel managers, propuesta de valor."

**El reparto de Pablo está bien. El de Vicente está mal priorizado**, y esto es lo más
importante que quiero plantear hoy.

- **Los channel managers son prematuros y no son el cuello de botella.** Un channel manager
  real (API de Booking Connectivity, API de Airbnb) exige certificación de partner y meses
  de trabajo, y **solo sirve para las cabañas y domos** — Booking y Airbnb ni siquiera
  saben modelar un "sitio de carpa" como unidad. Para el MVP la respuesta correcta es
  **iCal (import/export)**, que se implementa en dos días y cubre el 90% del caso real.
  Esto no requiere investigación: requiere media hora de decisión y está decidido.
- **Lo que sí solo puede hacer Vicente, y es lo que decide si el negocio existe, es el
  trabajo de calle:** el catastro, las 40 llamadas del Anexo B y las 5 cartas de intención.
  Si Pablo construye durante 10 semanas mientras nadie habla con anfitriones, estamos
  cometiendo el error #1 de la lista de errores que hunden estos proyectos.

La sociedad sí es de Vicente y es urgente —pero con una condición que planteo en §5.

---

## 4. Los tres riesgos que de verdad me preocupan

Más allá de los siete problemas estructurales del documento (que comparto), estos son los
que veo específicos de **nuestra** situación:

**R1 · El reloj.** 87 días hasta que se cierre la ventana de venta. Si tratamos esto como
un proyecto de fin de semana entre dos personas con trabajo, no llegamos a la temporada
26/27 y perdemos 12 meses. La decisión más importante de hoy no es el modelo de negocio:
es **cuántas horas semanales pone cada uno y en qué**.

**R2 · Construir para el anfitrión equivocado.** Es el error más caro y el más fácil de
cometer, porque el anfitrión que imaginamos (con web, Instagram, tarifario) es el 15% del
mercado. Mitigación: las 40 llamadas antes de que Pablo escriba la primera pantalla del
panel del anfitrión. El buscador y las fichas se pueden construir en paralelo sin riesgo,
porque esos no dependen del anfitrión.

**R3 · Que Travana llegue primero al mismo lugar.** Ya tienen 550 listings, mapa, filtros,
y están en constitución. Van por camper + camping; nosotros iríamos por camping +
alojamiento outdoor con software. Nuestro foso posible es el que ellos no tienen:
**el calendario vivo del anfitrión**. Si nos limitamos a ser un directorio con formulario,
llegamos segundos a una carrera que ya está corriendo.

---

## 5. Un punto incómodo que hay que poner sobre la mesa hoy

Vicente aporta la idea, la red comercial y va a hacer el trabajo de calle.
Pablo aporta el producto completo — que en los primeros 12 meses es, en dinero de mercado,
**entre $40.000.000 y $50.000.000 de trabajo** (el propio documento presupuesta un
desarrollador semi-senior a $2,4M/mes).

No estoy diciendo que el reparto deba ser desigual. Estoy diciendo que **hay que
conversarlo hoy, escribirlo, y ponerle vesting de 4 años con cliff de 1 año**, como
recomienda el documento en su checklist legal. Es la conversación que nadie quiere tener
entre primos y es exactamente por eso que hay que tenerla ahora, cuando todavía no hay
nada que repartir y es fácil ser generoso. Si se posterga, aparece en el peor momento.

Lo mismo con: quién pone el capital ($13M el primer año), qué pasa si uno se baja, y qué
dedicación semanal se compromete cada uno.

---

## 6. Veredicto

**El negocio existe, la tesis es correcta, y el modelo que propusieron el viernes es el
correcto con un ajuste de mecánica de cobro.**

Pero el margen de error es chico y viene de tres fuentes: el reloj de la temporada, la
tentación de construir antes de hablar con anfitriones, y un competidor local que ya está
en la cancha.

Mi recomendación es ejecutar el plan de 90 días de `05-plan-90-dias.md`, que corre
validación y construcción en paralelo, apunta a **25–40 campings con calendario vivo el
30 de noviembre**, y trata la temporada 26/27 como una **temporada de aprendizaje con
ingresos simbólicos** (~$1,5–3M) cuyo producto real son los datos, el inventario y las
relaciones que hacen posible la temporada 27/28.

Si en 3 semanas las 40 llamadas dicen que los anfitriones están llenos todo el año y
nadie paga por nada, paramos y nos ahorramos un año. Ese es el punto del plan.
