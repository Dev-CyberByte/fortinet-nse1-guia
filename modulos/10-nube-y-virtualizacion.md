# Módulo 10 — Cloud Security and Virtualization

Lecciones: Overview · Virtualization Overview · Cloud Overview · Cloud Security · Virtual Machine Risks · Common Cloud Threats · Cloud Hosted Security Services · Securing the Cloud

## 1. Virtualización
Crear **versiones virtuales** de recursos (servidores, redes, almacenamiento) sobre hardware físico.
- **Hypervisor:** software que crea y administra VMs.
  - **Tipo 1 (bare-metal):** se instala directo en el hardware (VMware ESXi, Hyper-V, KVM). Más eficiente y seguro.
  - **Tipo 2 (hosted):** corre sobre un SO (VirtualBox, VMware Workstation).
- **VM** (máquina virtual): SO completo aislado. **Contenedor:** empaqueta app y dependencias, **comparte el kernel** del host (más ligero).
- **Beneficios:** mejor uso de recursos, flexibilidad, recuperación rápida, ahorro de costos.

## 2. Cloud computing
Acceso **bajo demanda** a recursos de cómputo por Internet.

**Características esenciales (NIST):** on-demand self-service · broad network access · resource pooling · rapid elasticity · measured service.

| Modelo de servicio | Qué ofrece | Ejemplo |
|---|---|---|
| **IaaS** | Infraestructura (VMs, redes, almacenamiento) | AWS EC2, Azure VMs |
| **PaaS** | Plataforma para desarrollar/desplegar | Azure App Service, Google App Engine |
| **SaaS** | Aplicación lista para usar | Microsoft 365, Salesforce |

| Modelo de despliegue | Descripción |
|---|---|
| **Public** | Proveedor compartido entre clientes |
| **Private** | Dedicada a una organización |
| **Hybrid** | Combina pública y privada |
| **Multi-cloud** | Uso de varios proveedores |
| **Community** | Compartida por organizaciones con intereses comunes |

## 3. Cloud security: modelo de responsabilidad compartida
El **proveedor** y el **cliente** comparten la seguridad.

| Responsabilidad | IaaS | PaaS | SaaS |
|---|---|---|---|
| Datos, identidades y accesos | **Cliente** | **Cliente** | **Cliente** |
| Aplicaciones | Cliente | Compartida | Proveedor |
| SO / runtime | Cliente | Proveedor | Proveedor |
| Red virtual / hipervisor | Proveedor | Proveedor | Proveedor |
| Infraestructura física | Proveedor | Proveedor | Proveedor |

> Regla de oro: **"el proveedor protege *la nube*; el cliente protege lo que pone *en* la nube"**. Los **datos y el acceso siempre son del cliente**.

## 4. Riesgos en máquinas virtuales
| Riesgo | Descripción |
|---|---|
| **VM escape** | Atacante sale de la VM y accede al host/hipervisor |
| **Hypervisor attacks** | Comprometer el hipervisor afecta todas las VMs |
| **VM sprawl** | Proliferación de VMs sin control, sin parches |
| **Snapshots / imágenes inseguras** | Contienen datos o credenciales antiguas |
| **Falta de visibilidad del tráfico east-west** | El tráfico entre VMs no pasa por firewalls físicos |
| **Recursos compartidos** | Ataques *side-channel* / "noisy neighbor" |
| **Configuración débil / sin parches** | Igual que servidores físicos |

**Mitigación:** parchar hipervisor, segmentación y microsegmentación, firewalls virtuales, control de acceso, gestión del ciclo de vida de VMs, cifrado de discos.

## 5. Amenazas comunes en la nube
| Amenaza | Descripción |
|---|---|
| **Misconfiguration** | La causa más común de brechas (buckets públicos, permisos excesivos) |
| **Data breach / data loss** | Exposición o pérdida de datos |
| **Insecure APIs / interfaces** | APIs sin autenticación o con fallas |
| **Account hijacking** | Robo de credenciales |
| **Insider threat** | Acceso interno malicioso o negligente |
| **DDoS** | Saturación de servicios |
| **Shadow IT** | Uso de servicios no autorizados |
| **Lack of visibility** | Poca claridad sobre qué hay en la nube |
| **Malware / ransomware** | Ataques a cargas de trabajo y almacenamiento |
| **Compliance issues** | Incumplimiento regulatorio |

## 6. Servicios de seguridad hospedados en la nube
| Servicio | Función |
|---|---|
| **FWaaS** | Firewall como servicio |
| **SWG** (Secure Web Gateway) | Filtrado y protección de navegación web |
| **CASB** | Visibilidad y control del uso de aplicaciones SaaS |
| **ZTNA** | Acceso por aplicación con verificación continua |
| **SD-WAN** | Conectividad WAN optimizada y segura |
| **SASE** | Integra red (SD-WAN) y seguridad (SWG, CASB, ZTNA, FWaaS) entregados desde la nube |
| **Cloud email security** | SEG en la nube |
| **Cloud sandbox / WAF** | Análisis de amenazas y protección web en la nube |
| **SIEM/CNAPP/CSPM/CWPP** | Monitoreo de postura y cargas de trabajo en la nube |

Las **APIs** conectan servicios de la nube con otros componentes y aplicaciones de terceros; deben protegerse con autenticación, cifrado, límites de uso y monitoreo.

## 7. Cómo asegurar la nube
- **IAM** fuerte: MFA, least privilege, roles.
- **Cifrado** de datos en reposo y en tránsito; gestión de claves.
- **Segmentación** (VPC/VNET, grupos de seguridad).
- Revisión de **configuración y postura** (CSPM).
- **Logging y monitoreo** continuo; integración con SIEM.
- **Seguridad de APIs**.
- **Backups** y plan de recuperación.
- Cumplimiento y auditoría.
- Seguridad integrada y visibilidad unificada (Fortinet **Security Fabric**).

## Autoevaluación
1. Hipervisor tipo 1 vs 2 → bare-metal vs sobre un SO.
2. ¿De quién es responsabilidad proteger los datos en cualquier modelo? → Del **cliente**.
3. ¿Qué modelo da una aplicación lista para usar? → **SaaS**.
4. ¿Causa #1 de brechas en la nube? → **Misconfiguration**.
5. ¿Qué es SASE? → Convergencia de red y seguridad entregadas desde la nube.
