# Módulo 2 — The Threat Landscape

Lecciones: Overview · Threat Actors · Cybersecurity Threats · Threat Intelligence · Attack Frameworks · Outbreak Alerts and Advisories

## 1. Panorama de amenazas
Conjunto de amenazas, actores y vectores que pueden afectar a una organización. Incluye el mundo **físico y digital**.
- **Attack surface:** suma de todos los puntos donde un atacante puede intentar entrar (puertos, apps, usuarios, dispositivos, nube).
- **Attack vector:** el *camino* usado para entrar (email, USB, vulnerabilidad web, credenciales robadas, Wi-Fi inseguro).

## 2. Threat actors

| Actor | Motivación típica | Característica |
|---|---|---|
| **Script kiddie** | Curiosidad, fama | Usa herramientas ajenas, poca habilidad |
| **Hacktivist** | Ideología/política | DDoS, defacement, filtraciones |
| **Cybercriminal** | Dinero | Ransomware, fraude, robo de datos |
| **Organized crime** | Dinero a gran escala | Estructurados, venden servicios (RaaS, MaaS) |
| **Nation-state / APT** | Espionaje, sabotaje, geopolítica | Recursos altos, ataques largos y sigilosos |
| **Insider** | Venganza, dinero o error | Ya tiene acceso legítimo |
| **Competitor** | Ventaja de negocio | Espionaje industrial |
| **Terrorist** | Daño/ideología | Infraestructura crítica |

> **APT (Advanced Persistent Threat):** atacante sofisticado que permanece mucho tiempo sin ser detectado.

## 3. Amenazas comunes

| Amenaza | Descripción breve |
|---|---|
| **Malware** | Software malicioso (módulo 4) |
| **Phishing / Social engineering** | Engañar personas (módulo 3) |
| **DoS / DDoS** | Saturar un servicio para dejarlo no disponible |
| **MITM** | Interceptar/alterar comunicación entre dos partes |
| **SQL Injection** | Insertar SQL malicioso en una entrada |
| **XSS** | Inyectar scripts en páginas vistas por otros usuarios |
| **Brute force** | Probar muchas contraseñas |
| **Credential stuffing** | Usar credenciales filtradas en otros sitios |
| **Password spraying** | Probar pocas contraseñas comunes en muchas cuentas |
| **Zero-day** | Vulnerabilidad desconocida y sin parche |
| **DNS poisoning/spoofing** | Falsificar respuestas DNS para redirigir tráfico |
| **Supply chain attack** | Comprometer a un proveedor/software de confianza |
| **Ransomware** | Cifra datos y exige rescate |

## 4. Threat intelligence
Información **analizada y contextualizada** sobre amenazas para tomar mejores decisiones de defensa.
- **IoC (Indicator of Compromise):** evidencia de que algo malicioso ocurrió o está ocurriendo (hash, IP, dominio, URL, nombre de archivo).
- **TTPs:** *Tactics, Techniques and Procedures* — cómo actúa el adversario.
- **Fuentes:** feeds, honeypots, análisis de malware, dark web, comunidad, vendors. En Fortinet: **FortiGuard Labs**.
- **Niveles:** *strategic* (directivos), *operational* (campañas), *tactical* (TTPs), *technical* (IoCs).
- **Intercambio estándar:** STIX / TAXII.
- **Ciclo:** planeación → recolección → procesamiento → análisis → difusión → retroalimentación.

## 5. Attack frameworks

### Cyber Kill Chain (Lockheed Martin) — 7 fases
1. **Reconnaissance** — recopilar información del objetivo
2. **Weaponization** — crear el payload/exploit
3. **Delivery** — entregarlo (email, USB, web)
4. **Exploitation** — se aprovecha la vulnerabilidad
5. **Installation** — se instala malware/backdoor
6. **Command & Control (C2)** — canal remoto con el atacante
7. **Actions on Objectives** — exfiltración, cifrado, destrucción

> Idea clave: **romper la cadena en cualquier fase detiene el ataque.**

### MITRE ATT&CK
Base de conocimiento de **tácticas, técnicas y procedimientos** reales de adversarios.
- **Tactic** = el *objetivo* (ej. Initial Access, Persistence, Privilege Escalation, Defense Evasion, Credential Access, Lateral Movement, Exfiltration, Impact).
- **Technique** = el *cómo* (ID tipo `T1059`). **Sub-technique** = `T1059.001`.
- Usos: mapear detecciones, evaluar cobertura, threat hunting, red/blue/purple team.

### Diamond Model
Cuatro vértices de un evento: **Adversary · Capability · Infrastructure · Victim**.

| Marco | Enfoque |
|---|---|
| Kill Chain | Fases lineales del ataque |
| ATT&CK | Catálogo detallado de tácticas/técnicas |
| Diamond | Relación entre los elementos de un incidente |

## 6. Outbreak alerts y advisories
- **Outbreak alert:** aviso rápido sobre una amenaza de rápida propagación o una vulnerabilidad explotada activamente (en Fortinet: **FortiGuard Outbreak Alerts**).
- **Advisory:** boletín con detalle de vulnerabilidades y mitigación (en Fortinet: **PSIRT advisories**).
- **CVE:** identificador único de vulnerabilidades (`CVE-AAAA-NNNN`). **CVSS:** puntaje de severidad 0–10.
- Acción típica: identificar sistemas afectados → parchar o mitigar → monitorear IoCs.

## Autoevaluación
1. ¿Quién busca dinero? → **Cybercriminal**. ¿Y espionaje con recursos estatales? → **Nation-state/APT**.
2. Fase de la Kill Chain donde se instala el backdoor → **Installation** (fase 5).
3. Diferencia entre táctica y técnica en ATT&CK → táctica = objetivo; técnica = método.
4. ¿Qué es un IoC? → Evidencia de compromiso (hash, IP, dominio...).
5. ¿Qué mide CVSS? → La severidad de una vulnerabilidad.
