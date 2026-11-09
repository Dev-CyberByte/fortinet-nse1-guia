# Módulo 8 — Endpoint Security

Lecciones: Overview · Internet of Things · Endpoint Hardening Techniques · Endpoint Monitoring

## 1. ¿Qué es un endpoint?
Cualquier dispositivo que se conecta a la red: laptops, PCs, servidores, celulares, tablets, impresoras, cámaras, dispositivos **IoT** y **OT**.
Cada endpoint es un **posible punto de entrada**, por eso se busca protegerlo y monitorearlo.

## 2. BYOD
**Bring Your Own Device:** empleados usan dispositivos personales para trabajar.
- **Riesgos:** dispositivos sin parches, apps no controladas, pérdida o robo, mezcla de datos personales y corporativos, *shadow IT*.
- **Controles:** **MDM/MAM** (gestión de dispositivos móviles/aplicaciones), NAC, cifrado, MFA, contenedores de datos corporativos, política BYOD, borrado remoto.

## 3. Internet of Things (IoT)
Dispositivos conectados con capacidad limitada: cámaras, sensores, termostatos, impresoras, dispositivos médicos, etc.
**Riesgos:**
- Credenciales por defecto o débiles.
- Firmware sin actualizaciones; poca o ninguna capacidad de parchar.
- Recursos limitados (no se les instala antivirus).
- Falta de visibilidad; protocolos inseguros.
- Pueden formar **botnets** (ej. Mirai).

**Controles:** cambiar credenciales por defecto, **segmentar** IoT en VLAN propias, **NAC** con perfilamiento, actualizar firmware, deshabilitar servicios innecesarios, monitoreo de tráfico.

## 4. Endpoint hardening
Reducir la **superficie de ataque** configurando el endpoint de forma segura.

| Técnica | Descripción |
|---|---|
| **Patch management** | Mantener SO y aplicaciones actualizados |
| **Eliminar/deshabilitar** software, servicios y puertos innecesarios | Menos superficie de ataque |
| **Cambiar credenciales por defecto** | Evita accesos triviales |
| **Least privilege** | Usuarios sin permisos de administrador permanentes |
| **Host firewall** | Firewall local |
| **Antimalware / EPP** | Protección contra malware |
| **Disk encryption** | BitLocker, FileVault, LUKS |
| **Application allowlisting** | Solo se ejecutan apps aprobadas |
| **Secure baseline / configuration** | Configuración estándar (ej. CIS Benchmarks) |
| **Desactivar autorun / USB** | Evita infecciones por medios removibles |
| **Políticas de contraseña y MFA** | Control de acceso |
| **Backups** | Recuperación |
| **Logging habilitado** | Visibilidad |

## 5. Endpoint monitoring

| Tecnología | Qué hace |
|---|---|
| **EPP** (Endpoint Protection Platform) | **Prevención**: antivirus de nueva generación, firewall, control de dispositivos |
| **EDR** (Endpoint Detection and Response) | **Detección, investigación y respuesta** con telemetría continua; permite aislar el equipo, matar procesos, hacer forense |
| **XDR** (Extended Detection and Response) | Correlaciona datos de **endpoint, red, correo, nube** |
| **MDR** (Managed Detection and Response) | Servicio gestionado por terceros de monitoreo 24/7 |
| **SIEM** | Centraliza y correlaciona logs |

| EPP | EDR |
|---|---|
| Prevenir | Detectar y responder |
| Basado en firmas/ML | Basado en comportamiento y telemetría |
| Bloquea amenazas conocidas | Investiga actividad sospechosa |

Productos Fortinet relacionados: **FortiClient** (agente de endpoint), **FortiEDR**.

## Autoevaluación
1. ¿Qué técnica reduce la superficie de ataque? → **Hardening**.
2. EPP vs EDR → prevención vs detección/respuesta.
3. ¿Cómo proteger dispositivos IoT sin antivirus? → Segmentar, NAC, cambiar credenciales, actualizar firmware.
4. ¿Qué significa BYOD? → Bring Your Own Device.
5. ¿Qué correlaciona endpoint, red y nube? → **XDR**.
