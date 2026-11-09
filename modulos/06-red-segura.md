# Módulo 6 — Secure Network

Lecciones: Overview · Secure Perimeter · Zero Trust Principles · Centralized Security Network Management · Network Segmentation · Firewalls · Secure Switching and Ports · Security Protocols · Sandbox · Common Network Threats and Prevention · Operational Technology (OT) Security

## 1. Secure perimeter
Modelo tradicional "castillo y foso": se protege el **borde** de la red; lo de adentro se considera confiable.
- **Perímetro:** frontera entre la red interna y no confiable (Internet).
- **DMZ:** zona intermedia que aloja servicios expuestos (web, correo) aislados de la red interna.
- **Limitación:** hoy hay nube, remoto, BYOD e IoT; el perímetro ya no es claro → **zero trust**.

## 2. Zero Trust
Principio: **"never trust, always verify"** — no se confía en nadie por estar dentro de la red.
- Verificar **identidad, dispositivo y contexto** en cada acceso.
- **Least privilege** y acceso por sesión.
- **Microsegmentación** y asumir que ya hubo una brecha (*assume breach*).
- Monitoreo continuo.
- **ZTNA** (Zero Trust Network Access): acceso por aplicación, no a toda la red (reemplaza la VPN tradicional).

## 3. Administración centralizada
Gestionar políticas, logs y configuración desde **un solo punto** → consistencia, visibilidad y respuesta más rápida. Ejemplos de conceptos: consola de gestión, **SIEM**, análisis de logs, automatización.
Idea Fortinet: **Security Fabric** (integración de productos con visibilidad y control unificados).

## 4. Network segmentation
Dividir la red en **segmentos** para limitar movimiento lateral y reducir el alcance de un ataque.
| Técnica | Descripción |
|---|---|
| **VLAN** | Segmentación lógica en capa 2 |
| **Subnetting** | Subredes IP separadas |
| **Firewall interno** | Control entre segmentos |
| **Microsegmentation** | Segmentación granular por carga o aplicación |

## 5. Firewalls
Controlan el tráfico según **reglas/políticas**.
| Tipo | Qué hace |
|---|---|
| **Packet filtering** | Revisa IP, puerto, protocolo; sin contexto de sesión |
| **Stateful inspection** | Sigue el **estado de las conexiones** |
| **Proxy / Application gateway** | Intermediario que inspecciona a nivel de aplicación |
| **NGFW** (Next-Generation Firewall) | Stateful + **application control, IPS, inspección SSL/TLS, identidad de usuario, inteligencia de amenazas** |
| **UTM** | Varias funciones integradas en un solo equipo |
| **WAF** | Protege **aplicaciones web** (módulo 9) |

Políticas típicas: *default deny*, reglas ordenadas (se evalúan de arriba abajo), NAT, VPN.

## 6. Secure switching and ports
- **Port security:** limitar MACs permitidas por puerto.
- **802.1X:** autenticar dispositivos antes de dar acceso a la red.
- **Deshabilitar puertos sin uso**, cambiar VLAN nativa.
- **DHCP snooping**, **Dynamic ARP Inspection (DAI)**, **BPDU guard / STP protections**.
- **VLAN hopping** y ARP spoofing: ataques que estas medidas previenen.

## 7. Security protocols
| Protocolo | Función |
|---|---|
| **TLS/SSL** (HTTPS) | Cifra comunicación web |
| **IPsec** | Cifra a nivel IP (VPN) |
| **SSH** | Acceso remoto seguro (reemplaza Telnet) |
| **SFTP / FTPS** | Transferencia segura (reemplazan FTP) |
| **WPA2 / WPA3** | Seguridad Wi-Fi |
| **DNSSEC** | Autenticidad de respuestas DNS |
| **SNMPv3** | Gestión de red segura |
| **S/MIME, PGP** | Correo seguro |

Inseguros (evitar): **Telnet, FTP, HTTP, SNMPv1/2, WEP**.

## 8. Sandbox
Entorno **aislado** donde se ejecutan archivos sospechosos para **observar su comportamiento** sin riesgo.
- Detecta amenazas **desconocidas / zero-day** y malware evasivo.
- Puede ser local, en la nube o integrado en el firewall/email/endpoint (Fortinet: **FortiSandbox**).
- Resultado: veredicto (limpio / malicioso) que se comparte con otros dispositivos.

## 9. Amenazas de red comunes y prevención
| Amenaza | Prevención |
|---|---|
| **DoS / DDoS** | Protección DDoS, rate limiting, CDN |
| **MITM** | Cifrado (TLS), certificados, DAI |
| **ARP spoofing** | Dynamic ARP Inspection |
| **DNS poisoning** | DNSSEC, DNS filtering |
| **IP spoofing** | Filtrado de ingreso/egreso |
| **Port scanning / reconnaissance** | Firewall, IPS, cerrar puertos |
| **Packet sniffing** | Cifrado |
| **Rogue device / AP** | NAC, 802.1X |
| **Exploits de red** | **IPS**, parches |

**IDS vs IPS:** IDS **detecta y alerta**; IPS **detecta y bloquea**.

## 10. OT Security
**OT (Operational Technology):** sistemas que controlan procesos físicos — **ICS, SCADA, PLC, HMI** (industria, energía, agua, manufactura).
- Prioridades distintas a IT: en OT importa más la **seguridad física y la disponibilidad**; en IT, la confidencialidad.
- Equipos antiguos, difíciles de parchar y con protocolos sin seguridad (Modbus, DNP3).
- Riesgos crecientes por la convergencia **IT/OT**.
- **Modelo Purdue:** niveles jerárquicos para segmentar (nivel 0 procesos físicos → nivel 5 empresa).
- Controles: segmentación IT/OT, DMZ industrial, monitoreo pasivo, control de acceso, *virtual patching*.

## Autoevaluación
1. ¿Qué significa zero trust? → Nunca confiar, siempre verificar.
2. ¿Qué diferencia a un NGFW de un firewall tradicional? → Inspección de aplicaciones, IPS, identidad, SSL inspection.
3. IDS vs IPS → detecta vs detecta y bloquea.
4. ¿Para qué sirve una sandbox? → Analizar archivos sospechosos de forma aislada.
5. ¿Qué prioriza OT? → Disponibilidad y seguridad física.
