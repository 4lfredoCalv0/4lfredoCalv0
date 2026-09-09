<p align="center">
  <a href="https://github.com/4lfredoCalv0/4lfredoCalv0/blob/main/README.md">🇺🇸 English</a>
  &nbsp;&nbsp;•&nbsp;&nbsp;
  <a href="https://github.com/4lfredoCalv0/4lfredoCalv0/blob/main/README.es.md">🇨🇴 Español</a>
</p>

# Alfredo Calvo

**Ingeniero de IA y Automatización**

Construyo sistemas de automatización con IA para empresas — desde la
infraestructura backend orientada a eventos hasta las interfaces que la gente
termina usando.

La parte interesante no es conectar Shopify con Airtable. Es que el sistema siga
funcionando cuando un webhook se dispara dos veces, una API se cae, un mensaje
llega tarde, o no pasa nada en absoluto.

Trabajo en la intersección entre ingeniería de automatización, desarrollo backend
y aplicaciones con IA, sobre todo con n8n, Google Cloud, Next.js y TypeScript.

---

## Trabajo seleccionado

### Emerald

`Next.js 14` `TypeScript` `Tailwind` `Vercel AI SDK` `Streaming` `Groq` `MDX`

[Repositorio →](https://github.com/4lfredoCalv0/emerald) ·
[Sitio en vivo →](https://emerald-co.vercel.app/)

Una agencia de automatización AI-first que estoy construyendo desde cero,
incluyendo el sitio, la infraestructura, las interfaces conversacionales y la
capa de automatización que hay detrás.

El sitio corre dos asistentes conversacionales separados: uno de servicios, que
responde preguntas sobre lo que hace Emerald, y uno de agenda, que convierte una
conversación en una reserva completada — escribe el lead en Notion y dispara la
notificación sin salir del chat. Ambos responden en streaming a través del Vercel
AI SDK, con Llama 3.3 70B por Groq donde la latencia importa.

El blog usa MDX en vez de un CMS, y los formularios escriben directo en Notion.
Menos sistemas que mantener, menos cosas que se pueden romper.

### personal-ai-os

`Claude Code` `Obsidian` `n8n` `MCP`

[Repositorio →](https://github.com/4lfredoCalv0/personal-ai-os)

Un asistente personal construido como sistema operativo y no como chatbot.
Claude Code es el agente, un vault de Obsidian es la fuente de verdad, y n8n
corre lo que tiene que pasar sin nadie delante. Nada llega a la memoria
permanente sin revisión humana.

### Infraestructura de automatización

`n8n` `Shopify` `Airtable` `Gmail API` `Pub/Sub` `Google Cloud Functions`

Workflows en producción para una operación de e-commerce y manufactura. Airtable
es la fuente de verdad operativa, n8n orquesta, y Google Cloud se encarga de las
piezas que necesitan código propio o infraestructura orientada a eventos.

**Gmail → Pub/Sub → Cloud Functions.** Reemplacé un SaaS de pago de automatización
de Gmail con dos Cloud Functions. Las notificaciones push disparan el
procesamiento al instante en vez de consultar cada cinco minutos. Las
suscripciones se renuevan solas antes de expirar, y el etiquetado idempotente
evita procesar dos veces el mismo mensaje.

**Automatización de afiliados.**
`Solicitud → Aprobación → Código de descuento en Shopify → Comisiones → Reconciliación → Pago`
Un trabajo diario de reconciliación compara las órdenes de Shopify contra las
comisiones registradas y recrea las que un webhook perdido habría dejado caer.

**Inventario → Plazos de entrega.** Los datos de llegada de contenedores se
convierten en la ventana de entrega que el cliente ve en la página de producto.
Sin actualizaciones a mano, sin copiar y pegar de una hoja de cálculo a la web.

---

## Cómo construyo

Me importa menos que una automatización funcione una vez, y más que sea segura
de dejar corriendo indefinidamente. Los patrones a los que recurro:

* **Idempotencia** — ejecutar algo dos veces no debería crear dos registros. En
  la práctica significa verificar antes de crear, para que un reintento no
  duplique sus propios efectos.
* **Arquitectura orientada a eventos** — reaccionar a eventos en vez de consultar
  constantemente.
* **Reconciliación** — chequeos programados que detecten lo que los sistemas por
  eventos se perdieron.
* **Reintentos con backoff** — los fallos transitorios deberían recuperarse solos.
* **Ruta de error** — un fallo tiene que llegarle a una persona, no desaparecer
  en un log.
* **Observabilidad** — el sistema debería hacer evidentes sus fallos.

**La mayor parte de lo que construyo es la maquinaria que se da cuenta cuando
algo no pasó.**

## Stack

**Construcción** `Next.js` `React` `TypeScript` `Tailwind CSS` `Framer Motion` `Node.js`

**IA** `Vercel AI SDK` `Groq` `Llama` `Ollama` `MCP`

**Automatización** `n8n` `Airtable` `Shopify REST API` `Shopify GraphQL API` `Notion API`

**Cloud** `Google Cloud Functions` `Pub/Sub` `Gmail API`

**Ingeniería** `Python` `REST APIs` `GraphQL` `Webhooks` `OAuth` `Sistemas orientados a eventos`

## Ahora mismo

Construyendo Emerald, y experimentando con formas de combinar agentes de IA,
automatización de negocio y software convencional en sistemas que una empresa
pequeña pueda operar de verdad.

## Sobre este perfil

Buena parte del trabajo que hay detrás corre dentro de infraestructura privada de
empresas, así que no todo se puede abrir. Los repositorios que ves aquí son las
partes que sí puedo mostrar.

[calvo.alfredo2003@gmail.com](mailto:calvo.alfredo2003@gmail.com)
