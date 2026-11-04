# Digital Dev Tech — Rediseño de landing page

**Archivo maestro de contenido y sistema de diseño**
Proyecto: `digital-dev-linear` · Astro 5 + Tailwind CSS 3 · Tema oscuro por defecto
Referencia visual: [linear.app](https://linear.app) (tokens reales extraídos de su CSS: `data-theme="dark"`)

---

## 1. Objetivo

Transformar la landing actual de Digital Dev Tech (diseño "Obsidian Cybernetic": obsidiana + cian + esmeralda)
en una landing con el lenguaje visual de **Linear**: negro casi puro, grises de superficie, índigo de marca,
tipografía Inter, densidad baja, mucho aire, bordes de 1 px y movimiento sobrio.

**Lo que no cambia:** el contenido, el tono de venta, el producto, los datos de contacto, el asistente Miga
y su funcional (saludo + chat). **Lo que cambia:** todo el sistema visual y el orden/ritmo de las secciones.

**Datos de contacto (invariables)**

| Canal | Valor |
| --- | --- |
| WhatsApp | `+591 71961698` → `https://wa.me/59171961698` |
| Correo | `jorgejano97@gmail.com` |
| Nombre propio en la landing | Ninguno (solo la marca "Digital Dev Tech") |

---

## 2. Sistema de diseño "Linear Studio"

### 2.1 Color (valores reales de linear.app)

| Token | Valor | Uso |
| --- | --- | --- |
| Fondo base | `#08090a` | Fondo de página |
| Superficie baja | `#0f1011` | Tarjetas, paneles |
| Superficie media | `#141516` | Superficies elevadas |
| Superficie alta | `#191a1b` | Chips, campos de formulario |
| Superficie máxima | `#23252a` | Chips sobre superficie, hover |
| Borde | `#23252a` | Bordes de 1 px (`outline-variant`) |
| Borde fuerte | `#34343a` | Estados hover |
| Texto principal | `#f7f8f8` | Títulos y texto fuerte |
| Texto secundario | `#d0d6e0` | Texto de apoyo |
| Texto terciario | `#8a8f98` | Párrafos |
| Texto cuaternario | `#62666d` | Etiquetas monoespaciadas |
| Marca | `#5e6ad2` | Fondos de marca,Depths |
| Acento | `#7170ff` | Gradientes, acentos, foco |
| Enlace | `#828fff` | Acento claro |
| Verde | `#68cc58` / `#27a644` | Confirmación, estados OK |
| Cian | `#00b8cc` | Acento terciario |
| Rojo | `#eb5757` | Errores y "antes" |
| Invert (CTA) | `#e5e5e6` | Botón principal, texto `#08090a` |

### 2.2 Tipografía

- **Inter** (variable 300–800): display, títulos, etiquetas y cuerpo.
- **JetBrains Mono** (sustituto de *Berkeley Mono*): datos, metadatos, etiquetas en mayúsculas.

| Escala | Tamaño / interlineado | Peso |
| --- | --- | --- |
| `display-hero` | 64 / 70, tracking `-0.035em` | 600 |
| `display-hero-mobile` | 38 / 44, tracking `-0.03em` | 600 |
| `headline-lg` | 48 / 54, tracking `-0.03em` | 600 |
| `headline-md` | 36 / 42 | 600 |
| `headline-sm` | 24 / 32 | 600 |
| `body-lg` | 17 / 28 | 400 |
| `body-md` | 15 / 24 | 400 |
| `body-sm` | 13 / 20 | 400 |
| `label-md` | 12 / 16 | 500 |
| `label-sm` | 11 / 14, tracking `0.04em` | 500 |

### 2.3 Layout y componentes

- Contenedor: `1200px` máximo, gutter de `24px` (móvil `20px`).
- Radios: `4px` (sm) · `6px` (base) · `8px` (botones y chips) · `12px` (tarjetas) · `9999px` (píldoras).
- Altura de botón: `36–40px`. Bordes de `1px` `#23252a`, hover `#34343a`.
- Sombras: `low 0 2px 4px #0000001a` · `medium 0 4px 24px #0003` · `high 0 7px 32px #00000059`.
- Etiqueta superior (eyebrow) monoespaciada, `11px`, `uppercase`, tracking `0.14em`, color `#62666d`.
- Botón principal estilo *invert* de Linear: fondo `#e5e5e6`, texto `#08090a`.
- Degradado de marca para palabras clave del titular: `#828fff → #7170ff → #b4bcd0`.
- Fondos: rejilla técnica de 64 px con máscara radial y dos halos índigo muy difusos.

### 2.4 Movimiento

Movimiento **sobrio** (no gamificado): entradas de 0.7 s con `cubic-bezier(0.22, 1, 0.36, 1)`, Micro-interacciones
de 0.15–0.2 s. `prefers-reduced-motion` desactiva todo.

- `fadeUp` / `ddtReveal` — entrada al hacer scroll (solo `translateY`, nunca `opacity: 0` en el estado final).
- `floatSlow` / `floatDelayed` — flotación suave de tarjetas y anotaciones.
- `pulseGlow` — punto en vivo del header.
- `laserScan` — línea de escaneo sobre el marco del producto.
- `circuitTravel` — recorrido del conector en el proceso.
- `auraBreathe` — halo del botón de Miga.
- `gradientShift` — degradado del titular.
- `marquee` — ticker de módulos de software.
- Propias de Miga: `bounceSoft`, `tailSway`, `earTwitch`, `blink`, `pawWave`, `spinSlow`.

---

## 3. Contenido completo de la landing

### 3.1 Navegación (header)

- Marca: logo DDT + "Digital Dev" (blanco) + "Tech" (gris) + subtítulo monoespaciado "Software & Mobile Studio".
- Enlaces: El Problema · Soluciones · Cómo Trabajamos · Comparativa · Precios & ROI · Contacto.
- Botón de Miga (avatar con punto verde) + CTA invert "Cotizar Ahora" + menú móvil.
- **Comportamiento responsive del header:**
  - `< 768 px`: solo marca + Miga + "Cotizar Ahora" + botón hamburguesa; la navegación vive en el panel desplegable.
  - `768–1023 px`: barra horizontal con 4 enlaces (El Problema · Soluciones · Cómo Trabajamos · Contacto), sin subtítulo de marca y sin hamburguesa.
  - `≥ 1024 px`: barra horizontal completa con los 6 enlaces.
  - `≥ 1280 px`: aparece además el subtítulo "Software & Mobile Studio".
  - Los enlaces nunca se parten de línea (`whitespace-nowrap`) y el nav no se comprime (`shrink-0`).

### 3.2 Hero

- **Eyebrow:** `● SOFTWARE A LA MEDIDA · RESPUESTA EN MENOS DE 24 HORAS`
- **Titular:** "Transforma el Caos Manual en **Software Inteligente**"
- **Bajada:** "Dejamos de perder tiempo en tareas repetitivas. Diseñamos apps móviles y sistemas a la medida que
  hacen que tu empresa y tu equipo trabajen mejor, con alcances claros y tiempos bien definidos."
- **CTA primario:** "Cotizar mi proyecto →" · **CTA secundario:** "▶ Ver cómo trabajamos"
- **Confianza:** Cero papeleo · Procesos 10x más rápidos · ROI en < 90 días
- **Marco del producto:** barra tipo terminal (`DDT_OPERATING_SYSTEM // v1.0`, estado "Respuesta: 24h",
  "Asistente: Miga"), imagen de showcase y dos tarjetas flotantes: "Pedidos en vivo" y "Panel en vivo"
  (esta última: "Ventas, inventario y facturación conectados en un solo panel, con la información siempre al día").
- **Métricas comparadas:** 42 hrs/sem (caos manual) · 18% fallos · < 1,2 s (Digital Dev Tech) · +340% eficiencia.

### 3.3 Proceso — "de la idea al software en 4 pasos"

| # | Fase | Título | Texto | Nota |
| --- | --- | --- | --- | --- |
| 01 | Fase inicial | Diagnóstico sin costo | Respondemos el mismo día por WhatsApp: entendemos tu operación, qué se hace a mano, qué se pierde y qué se repite. Salimos con un diagnóstico claro y accionable. | Respuesta el mismo día |
| 02 | Planificación | Diseño a tu medida | Convertimos tu operación en un plan: pantallas, flujos y datos. Ves el resultado esperado antes de que escribamos la primera línea de código. | Propuesta en 48 horas |
| 03 | Construcción | Desarrollo por entregas | Avanzamos en ciclos cortos y recibes avances funcionales para probarlos en tu operación real. El plazo depende del tamaño del software o la aplicación, y siempre te lo decimos antes de empezar. | Plazos según el tamaño |
| 04 | Despliegue | Entrega y soporte | Publicamos tu sistema, te damos acceso a todas tus credenciales y te acompañamos con soporte y garantía después de la entrega. | Acceso total a tus cuentas |

### 3.4 El problema — "¿Te suena familiar?"

1. **Carga de trabajo sin control** — Pedidos por WhatsApp, ventas en cuadernos, fichas de stock que no cuadran.
   *Etiqueta: Lo que pasa hoy.*
2. **Pasos tediosos que consumen el día** — Copiar datos, reportes a mano, escribir lo mismo cien veces.
   *Etiqueta: Lo que más cansa.*
3. **Errores humanos en cada proceso** — Un dato mal cargado, un inventario desactualizado y la pérdida se nota
   tarde; cada error cuesta dinero y procesos o clientes que se detienen. *Etiqueta: Lo que más cuesta.*

> Nota de estilo: el copy habla de **empresa / operación / equipo**, nunca de un tipo de cliente concreto, para
> que el mensaje funcione igual para un negocio, una empresa o una fábrica.

### 3.5 Comparativa — "Procesos manuales vs. software inteligente"

| Procesos manuales | Con Digital Dev Tech |
| --- | --- |
| Pedidos que se anotan a mano en cuadernos | Pedidos que entran solos por WhatsApp con QR |
| Reportes que se arman a mano cada semana | Reportes que se actualizan en tiempo real |
| Stock que se actualiza "cuando se acuerdan" | Stock sincronizado entre todos los puntos de venta |
| Precios que cambian según quién pregunte | Precios y reglas siempre iguales |
| Cero trazabilidad de lo que se vendió | Historial completo de cada venta y cada cliente |
| La operación se frena cuando falta un turno | La operación sigue funcionando aunque falte alguien |

### 3.6 Soluciones (4 tarjetas)

1. **Apps Móviles a Medida** *(iOS & Android)* — con QR, notificaciones y uso sin conexión; publicación garantizada
   en las tiendas; cobro con QR y tarjeta; funciona sin internet.
2. **Catálogos & WhatsApp Business** *(WhatsApp QR)* — chats que venden solos, catálogo interactivo con carrito,
   stock actualizado, sin comisiones de pasarelas.
3. **Sistemas ERP & Software de Gestión** *(Panel Web)* — inventario, finanzas y facturación en un panel; copias
   de seguridad automáticas; módulos personalizados; cada usuario ve solo lo suyo.
4. **Landing Pages Ultra Rápidas** *(Alta Conversión)* — cargan en menos de 1 segundo, Lighthouse 95+, mobile-first.

### 3.7 El software que hacemos (nueva sección)

> "No revendemos software genérico: diseñamos cada módulo con tus procesos, tus roles y tus números.
> Cada sistema funciona solo, pero juntos se convierten en una sola empresa."

Panel tipo tablero (`DDT_MODULES // v1.0`) con 8 módulos:

| Código | Módulo | Qué resuelve | Etiqueta |
| --- | --- | --- | --- |
| ERP | ERP a medida | Inventario, compras, ventas, producción y finanzas en un solo panel | Núcleo |
| SCM | Gestión de cadena de suministro | Proveedores, órdenes de compra, recepción y trazabilidad de cada lote | Logística |
| CRM | CRM y postventa | Pipeline comercial, historial de clientes, recordatorios y fidelización | Ventas |
| WMS | WMS para bodega | Stock por bodega, picking, mermas, transferencias y conteos cíclicos | Bodega |
| ACC | Contabilidad y facturación | Libro de ventas, IVA, balances, cuentas por cobrar y cierre mensual | Finanzas |
| POS | Punto de venta | Cobro con QR o tarjeta, tickets y corte de caja por turno | Mostrador |
| AI | Automatización con IA | Clasificación de pedidos, respuestas rápidas y reportes que se redactan solos | Inteligente |
| BI | Dashboards y reportes | Indicadores en vivo, alertas por umbral y reportes listos para decidir | Control |

Frases de apoyo: "Un solo proveedor" · "Acceso a tus cuentas" · "Integrable con lo que ya usas".
Debajo, un ticker animado con los códigos de cada módulo.

### 3.8 Spotlight de Miga

- Eyebrow: "Tu asistente de confianza".
- Titular: "Conoce a Miga 🐾 — tu guardián contra el caos manual".
- Cita: *«¡Hola! ¿Cómo estás? Soy **Miga**, la asistente de Digital Dev Tech. **Listo para dejar los procesos
  manuales y tediosos**: me escribes aquí, describes tu tarea y yo te digo en minutos cómo automatizarla. Y si
  prefieres hablar con el equipo, puedes escribirle directo a **Digital Dev Tech por WhatsApp**.»*
- Beneficios: Responde al instante · Habla tu idioma · Cero fricción.
- CTA principal: "Conversar con Miga ahora" → abre el chat.
- CTA secundario: "Hablar directo con Digital Dev Tech por WhatsApp" → `wa.me/59171961698`.

### 3.9 Precios y ROI

**Modelo anticuado (consultora tradicional)**
- Costos inflados: presupuestos de seis cifras con costos ocultos de gestión.
- Tiempos eternos: entre 6 y 12 meses antes del primer prototipo.
- Tarifas de mantenimiento cautivas: cobros recurrentes por cambios mínimos.
- Código propietario: te vuelves dependiente de licencias cerradas.
- Retorno estimado: **> 18 – 24 meses**

**El enfoque ágil (Digital Dev Tech)**
- Inversión predecible y honesta: paquetes estructurados sin sorpresas.
- Sprints de 3 a 6 semanas: entregas visibles para validar valor desde el día 15.
- Acceso total a tus credenciales: te entregamos el control de cuentas, paneles y accesos desde el primer día.
- Ahorro medible: recuperas horas-hombre y agilidad operativa.
- Retorno de inversión: **< 90 días**

> En esta sección **no se mencionan cuotas mensuales ni suscripciones**: el argumento es alcance, plazo y
> control, no la forma de pago.

**Calculadora de recuperación** (ids `team-slider`, `team-size-display`, `hours-saved-display`, `money-saved-display`)
- Control: "Miembros del equipo operativo" de 1 a 50 (marcas en 3 · 10 · 25 · 50+).
- Salida 1: tiempo liberado (`~80 hrs` al mes recuperadas).
- Salida 2: ahorro mensual estimado (`Bs 3.200` que vuelven a la empresa).
- Fórmula: `horas = equipo × 8`; `ahorro = horas × 40` (bolivianos/mes, formato `Bs 11.200`).

### 3.10 Contacto

- Eyebrow "Hablemos"; titular "¿Listo para construir el software que transforma tu empresa?".
- Bajada: diagnóstico y propuesta clara en menos de 24 horas, sin compromiso.
- Canales: `jorgejano97@gmail.com` y `+591 71961698`.
- Formulario (`main-contact-form`): `client-name`, `client-service` (App móvil · Catálogo WhatsApp · ERP/Panel web ·
  Landing page · Automatización con IA · Consultoría), `client-notes` y envío directo a WhatsApp.
- Nota de pie: "Respuesta personalizada en menos de 24 horas · Confidencialidad bajo acuerdo NDA".

### 3.11 Footer

Cuatro columnas: marca y datos de contacto · Servicios · Compromiso · Estado.
Compromisos: acceso total a tus cuentas · costos claros · soporte y garantía · confidencialidad.

---

## 4. Asistente Miga

- **Qué es:** una gatita (no un robot) dibujada en SVG propio, con pelaje lila-griz, collar índigo y aura orbital.
- **Animaciones:** respiración del cuerpo, cola que se mece, orejas que hacen tic, parpadeo, pata que saluda,
  órbita punteada girando, halo que respira.
- **Saludo automático** (2,2 s tras cargar): "¡Hola! ¿Cómo estás? Soy Miga, tu asistente en Digital Dev Tech.
  Listo para dejar los procesos manuales y tediosos: cuéntame y te digo cómo automatizarlos."
- **Chat** (esquina inferior derecha + botón del header + spotlight): burbujas de usuario invertidas (`#e5e5e6`),
  burbujas de Miga sobre superficie alta, indicador "escribiendo", chips rápidos:
  `¿Cuánto cuesta?` · `Quiero una App` · `Automatizar procesos` · `Cotizar en 24 h`.
- **Respuestas por palabras clave:** precio · app · automatizar · cotizar · ERP · catálogo.

---

## 5. Estructura de archivos

```
digital-dev-linear/
├── CONTENIDO-Y-DISENO.md      ← este archivo
├── astro.config.mjs
├── tailwind.config.mjs        ← tokens "Linear Studio"
├── public/
│   ├── logo-ddt.svg            ← logo DDT (vectorial, sin <text>)
│   ├── miga-avatar.svg
│   └── shots/*.webp            ← imágenes del estilo Linear
└── src/
    ├── layouts/BaseLayout.astro
    ├── pages/index.astro       ← ensamblaje + script (menú, ROI, chat, reveal)
    ├── styles/global.css       ← base + sistema de animaciones
    └── components/
        ├── Header.astro · Hero.astro
        ├── Process.astro · ProblemSolution.astro · Compare.astro
        ├── Services.astro
        ├── SoftwareModules.astro   ← ERP · SCM · CRM · WMS · Contabilidad · POS · AI · BI
        ├── MigaSpotlight.astro · Miga.astro · AssistantWidget.astro
        └── Pricing.astro · Contact.astro · Footer.astro
```

---

## 6. Comandos

```bash
npm install
npm run dev -- --host 127.0.0.1 --port 4330   # desarrollo
npm run build                                 # build estático en dist/
python -m http.server 8945 --directory dist    # previsualización del build
```
