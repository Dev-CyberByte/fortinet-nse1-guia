# Módulo 1 — Introduction to Cybersecurity

Lecciones: Overview · What is Cybersecurity · Principles of Information Security

## 1. ¿Qué es la ciberseguridad?
Práctica de **proteger sistemas, redes, dispositivos y datos** contra accesos no autorizados, daños o interrupciones, y de **reducir el riesgo** de ciberataques. Abarca personas, procesos y tecnología.

**Por qué importa:** casi todo depende de sistemas conectados (negocios, salud, gobierno, infraestructura crítica). Una brecha puede causar pérdidas económicas, daño reputacional, sanciones legales e interrupción operativa.

## 2. Términos base

| Término | Significado |
|---|---|
| **Asset** (activo) | Cualquier cosa de valor: datos, equipos, aplicaciones, personas, reputación |
| **Vulnerability** | Debilidad que puede ser aprovechada |
| **Threat** (amenaza) | Cualquier cosa que puede explotar una vulnerabilidad y causar daño |
| **Exploit** | Técnica o código que aprovecha una vulnerabilidad |
| **Risk** (riesgo) | Probabilidad de que una amenaza explote una vulnerabilidad × impacto |
| **Attack** | Intento deliberado de dañar, robar o acceder sin autorización |
| **Breach** | Incidente en el que se accede a datos sin autorización |

## 3. Principios de seguridad de la información

### Tríada CIA
| Principio | Qué garantiza | Ejemplo de control |
|---|---|---|
| **Confidentiality** | Solo los autorizados acceden a la información | Cifrado, control de acceso, MFA |
| **Integrity** | Los datos no se alteran sin autorización | Hashing, firmas digitales, control de cambios |
| **Availability** | Los sistemas y datos están disponibles cuando se necesitan | Redundancia, backups, protección DDoS |

### Otros conceptos
- **AAA:** *Authentication* (quién eres), *Authorization* (qué puedes hacer), *Accounting* (qué hiciste).
- **Non-repudiation:** no se puede negar haber realizado una acción (firmas digitales, logs).
- **Least privilege:** solo los permisos mínimos necesarios.
- **Defense in depth:** varias capas de seguridad; si una falla, otra protege.
- **Separation of duties:** ninguna persona controla todo un proceso crítico.
- **Need to know:** acceso solo a la información necesaria para el trabajo.

### Estados de los datos
*At rest* (almacenados) · *In transit* (en movimiento por la red) · *In use* (en procesamiento).

### Tipos de controles
| Por función | Ejemplo |
|---|---|
| **Preventive** | Firewall, MFA, cifrado |
| **Detective** | IDS, logs, cámaras |
| **Corrective** | Restaurar backup, parchar |
| **Deterrent** | Avisos, políticas |

| Por naturaleza | Ejemplo |
|---|---|
| **Administrative** | Políticas, capacitación |
| **Technical** | Firewall, antivirus |
| **Physical** | Cerraduras, guardias |

## Autoevaluación
1. ¿Qué principio de CIA protege un hash? → **Integrity**.
2. ¿Qué ataque afecta principalmente *Availability*? → **DoS/DDoS**.
3. Diferencia entre vulnerabilidad y amenaza → la vulnerabilidad es la **debilidad**; la amenaza es lo que **la aprovecha**.
4. ¿Qué significa AAA? → Authentication, Authorization, Accounting.
5. ¿Qué es defense in depth? → Seguridad en **múltiples capas**.
