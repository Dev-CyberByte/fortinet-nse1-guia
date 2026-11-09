# Módulo 3 — Social Engineering

Lecciones: Overview · Techniques A · Techniques B · Insider Threat · Fraud, Scams and Influence Campaigns

## 1. ¿Qué es la ingeniería social?
Manipular **personas** (no sistemas) para que revelen información, den acceso o realicen acciones que comprometan la seguridad. Es efectiva porque **el factor humano suele ser el eslabón más débil**.

### Por qué funciona (principios psicológicos)
| Principio | Cómo lo explotan |
|---|---|
| **Authority** | Se hacen pasar por jefe, TI o autoridad |
| **Urgency** | "¡Hazlo ya o pierdes la cuenta!" |
| **Scarcity** | "Oferta limitada" |
| **Fear** | Amenazas de multas o bloqueos |
| **Trust / Liking** | Simpatía o familiaridad |
| **Reciprocity** | Dan algo para pedir algo |
| **Social proof** | "Todos ya lo hicieron" |
| **Curiosity / Greed** | Premios, archivos "interesantes" |

## 2. Técnicas

### Digitales
| Técnica | Descripción |
|---|---|
| **Phishing** | Correos masivos falsos para robar datos/credenciales |
| **Spear phishing** | Phishing dirigido a una persona concreta con datos personalizados |
| **Whaling** | Dirigido a ejecutivos (C-level) |
| **Vishing** | Por llamada de voz |
| **Smishing** | Por SMS/mensajería |
| **Pharming** | Redirigir a un sitio falso (DNS/hosts) |
| **Watering hole** | Infectar un sitio que la víctima visita habitualmente |
| **Typosquatting** | Dominios con errores tipográficos (`gooogle.com`) |
| **BEC** (Business Email Compromise) | Suplantar a directivos/proveedores para pedir transferencias |
| **Clone phishing** | Copia de un correo legítimo con enlace/adjunto malicioso |
| **Angler phishing** | Suplantar soporte en redes sociales |

### Físicas / presenciales
| Técnica | Descripción |
|---|---|
| **Pretexting** | Inventar un escenario creíble para obtener información |
| **Baiting** | Dejar un cebo (USB infectado) |
| **Quid pro quo** | Ofrecer un "servicio" a cambio de información |
| **Tailgating / Piggybacking** | Entrar siguiendo a alguien autorizado |
| **Shoulder surfing** | Mirar lo que alguien escribe |
| **Dumpster diving** | Buscar información en la basura |
| **Impersonation** | Hacerse pasar por otra persona |

### Señales de phishing
Remitente extraño o dominio parecido · urgencia · errores de redacción · enlaces que no coinciden al pasar el cursor · adjuntos inesperados · solicitudes de credenciales o dinero.

## 3. Insider threat
Riesgo que proviene de **personas con acceso legítimo**.

| Tipo | Descripción |
|---|---|
| **Malicious insider** | Actúa con intención (venganza, dinero) |
| **Negligent insider** | Comete errores o ignora políticas |
| **Compromised insider** | Sus credenciales/equipo fueron tomados por un atacante |

**Indicadores:** accesos fuera de horario, descargas masivas, acceso a datos que no necesita, uso de dispositivos no autorizados, descontento.
**Mitigación:** least privilege, monitoreo/UEBA, DLP, capacitación, offboarding rápido, separación de funciones.

## 4. Fraude, estafas y campañas de influencia
- **Fraude:** engaño para obtener beneficio ilegal (fraude de tarjetas, de facturas, de soporte técnico).
- **Scams:** estafas de lotería, romance, inversión, falso soporte técnico.
- **Influence campaigns:** manipular la opinión pública mediante información falsa o sesgada.
  - **Misinformation:** falsa, sin intención de dañar.
  - **Disinformation:** falsa, **con intención** de engañar.
  - **Malinformation:** información real usada para causar daño.
  - Herramientas: bots, cuentas falsas, **deepfakes**.

## 5. Cómo defenderse
Capacitación y simulacros de phishing · MFA · filtros de correo (SEG) · verificar por otro canal · políticas claras de reporte · control de acceso físico.

## ✅ Autoevaluación
1. Phishing dirigido a un ejecutivo → **Whaling**.
2. Phishing por SMS → **Smishing**; por llamada → **Vishing**.
3. Entrar a un edificio pegado a un empleado → **Tailgating**.
4. USB abandonado con malware → **Baiting**.
5. Información falsa difundida con intención → **Disinformation**.
