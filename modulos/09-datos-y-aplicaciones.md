# Módulo 9 — Secure Data and Applications

Lecciones: Overview · Data Protection · Data Privacy · Secure Email Gateway · WAF · Content Filters · Application Hardening Techniques

## 1. Data protection
Proteger los datos durante todo su **ciclo de vida** (creación, uso, almacenamiento, transferencia, destrucción).

| Medida | Descripción |
|---|---|
| **Data classification** | Etiquetar según sensibilidad (pública, interna, confidencial, restringida) |
| **Encryption** | At rest, in transit, in use |
| **DLP** (Data Loss Prevention) | Detecta y bloquea fuga de datos sensibles (correo, USB, nube) |
| **Backup & recovery** | Copias y pruebas de restauración |
| **Access control** | Mínimo privilegio |
| **Data masking / tokenization** | Ocultar o sustituir datos sensibles |
| **Retention & disposal** | Conservar lo necesario y destruir de forma segura |

## 2. Data privacy
Se enfoca en **cómo se recopilan, usan y comparten los datos personales**, y los derechos de las personas.
- **PII** (Personally Identifiable Information): nombre, CURP/SSN, correo, dirección, teléfono, datos biométricos.
- **Privacy ≠ Security:** la seguridad *protege* los datos; la privacidad define *cómo se usan*.

| Regulación | Alcance |
|---|---|
| **GDPR** | Datos de residentes de la UE |
| **HIPAA** | Información de salud (EE. UU.) |
| **PCI DSS** | Datos de tarjetas de pago |
| **CCPA/CPRA** | Privacidad en California |
| **SOX** | Reportes financieros |
| **LFPDPPP** | Protección de datos personales en México |

Principios habituales: **minimización**, limitación de propósito, consentimiento, transparencia, derecho de acceso y eliminación, notificación de brechas.

## 3. Secure Email Gateway (SEG)
Filtra el correo **entrante y saliente** antes de llegar al usuario. El correo es el vector #1 de phishing y malware.
| Función | Descripción |
|---|---|
| Anti-spam y anti-phishing | Detecta correos fraudulentos |
| Antimalware | Escanea adjuntos |
| **Sandbox de adjuntos** | Analiza archivos desconocidos |
| **URL rewriting / protección de enlaces** | Revisa el enlace al hacer clic |
| **DLP** | Evita fuga de datos por correo |
| Cifrado de correo | Mensajes seguros |
| **SPF / DKIM / DMARC** | Autenticación del dominio remitente |

- **SPF:** qué servidores pueden enviar por un dominio.
- **DKIM:** firma criptográfica del mensaje.
- **DMARC:** política sobre qué hacer si SPF/DKIM fallan, más reportes.
Producto Fortinet: **FortiMail**.

## 4. WAF (Web Application Firewall)
Protege **aplicaciones web** inspeccionando tráfico HTTP/HTTPS (capa 7).
- Previene: **SQL injection, XSS, CSRF, path traversal, command injection**, ataques del **OWASP Top 10**, bots y abuso de APIs.
- **Modelos:** *negative security* (bloquea lo conocido como malo) y *positive security* (permite solo lo conocido como bueno).
- Despliegue: appliance, virtual, nube, reverse proxy.

| NGFW | WAF |
|---|---|
| Protege la **red** en general | Protege **aplicaciones web** |
| Capas 3–7 | Capa 7 (HTTP/S) |

Producto Fortinet: **FortiWeb**.

## 5. Content filters
Controlan **qué contenido pueden acceder** los usuarios.
| Filtro | Función |
|---|---|
| **Web/URL filtering** | Bloquea categorías o sitios (malware, phishing, adultos) |
| **DNS filtering** | Bloquea dominios maliciosos al resolver |
| **Application control** | Permite/bloquea aplicaciones |
| **File/Content filtering** | Por tipo de archivo o contenido |
| **Video/Email filters** | Controla ciertos tipos de contenido |

Beneficios: reduce exposición a malware, mejora cumplimiento y productividad.

## 6. Application hardening
Reducir vulnerabilidades en aplicaciones.
- **Secure coding** y validación de entradas (*input validation*), sanitización.
- **Patching** de aplicaciones y librerías (control de dependencias).
- Eliminar funciones, cuentas y credenciales por defecto.
- **Least privilege** para la app y sus cuentas de servicio.
- Gestión segura de secretos (no dejar claves en el código).
- Manejo seguro de errores (no revelar información interna).
- **SAST / DAST / pentesting** y revisión de código.
- Cifrado (TLS) y sesiones seguras.
- Implementar **WAF**.
- Principios *Secure SDLC / DevSecOps*.

## Autoevaluación
1. ¿Qué previene la fuga de datos sensibles? → **DLP**.
2. ¿Qué protege contra SQLi y XSS? → **WAF**.
3. SPF/DKIM/DMARC protegen → el **correo** (autenticidad del remitente).
4. ¿Qué regulación protege datos de tarjetas? → **PCI DSS**.
5. Privacidad vs seguridad → cómo se usan los datos vs cómo se protegen.
