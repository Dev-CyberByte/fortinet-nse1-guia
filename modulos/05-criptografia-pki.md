# Módulo 5 — Cryptography and the Public Key Infrastructure

Lecciones: Overview · Ciphers · Keys and Cryptographic Algorithms · Hashing and Digital Signatures · PKI · Introducing Quantum Security

## 1. Conceptos base
**Criptografía:** técnicas para proteger información. Proporciona:
| Propiedad | Se logra con |
|---|---|
| Confidentiality | Cifrado |
| Integrity | Hashing |
| Authentication | Certificados / firmas |
| Non-repudiation | Firmas digitales |

- **Plaintext:** texto original · **Ciphertext:** texto cifrado · **Key:** valor secreto usado para cifrar/descifrar.
- **Encryption** → plaintext a ciphertext. **Decryption** → el inverso.
- **Principio de Kerckhoffs:** la seguridad debe depender de la **clave**, no de ocultar el algoritmo.

## 2. Ciphers (cifrados)
| Tipo | Descripción |
|---|---|
| **Substitution** | Reemplaza caracteres por otros (ej. **Caesar**) |
| **Transposition** | Reordena los caracteres |
| **Stream cipher** | Cifra bit a bit/byte a byte (ej. ChaCha20, RC4) |
| **Block cipher** | Cifra bloques de tamaño fijo (ej. AES, DES) |
| **One-time pad** | Clave aleatoria, de igual longitud que el mensaje y de un solo uso |

## 3. Llaves y algoritmos

### Simétrico (symmetric)
- **Una sola clave** para cifrar y descifrar.
- **Rápido**, ideal para grandes volúmenes de datos.
- Problema: **¿cómo compartir la clave de forma segura?**
- Ejemplos: **AES** (128/192/256 bits, estándar actual), 3DES, DES (obsoleto), ChaCha20.

### Asimétrico (asymmetric)
- **Par de claves:** pública (se comparte) y privada (secreta).
- Más **lento**; se usa para intercambio de claves, firmas y autenticación.
- Lo cifrado con la **pública** solo lo descifra la **privada** (confidencialidad).
- Ejemplos: **RSA**, **ECC**, **Diffie-Hellman** (intercambio de claves), DSA.

| | Simétrico | Asimétrico |
|---|---|---|
| Claves | 1 compartida | 2 (pública/privada) |
| Velocidad | Rápido | Lento |
| Uso principal | Cifrar datos | Intercambio de claves, firmas |
| Ejemplos | AES | RSA, ECC |

> **En la práctica (TLS):** se usa asimétrico para acordar una **clave de sesión** y luego simétrico para cifrar los datos (cifrado híbrido).

**Longitud de clave:** más bits = más difícil de atacar por fuerza bruta.

## 4. Hashing y firmas digitales

### Hash
Función **unidireccional** que convierte datos en una cadena de longitud fija.
- Mismo input → mismo hash; un cambio mínimo → hash totalmente distinto (*avalanche effect*).
- **No se puede revertir** y debe evitar **colisiones**.
- Algoritmos: **SHA-256**, SHA-3 (seguros); MD5 y SHA-1 (considerados débiles).
- Usos: verificar integridad, almacenar contraseñas (con **salt**), firmas.
- **HMAC:** hash con clave (integridad + autenticidad).

### Firma digital
1. Se calcula el **hash** del mensaje.
2. Se cifra el hash con la **clave privada** del emisor → firma.
3. El receptor descifra con la **clave pública** y compara hashes.

Proporciona **integrity, authentication y non-repudiation** (no confidencialidad por sí sola).

## 5. PKI (Public Key Infrastructure)
Conjunto de **roles, políticas y tecnología** para crear, distribuir, gestionar y revocar certificados digitales.

| Componente | Función |
|---|---|
| **CA** (Certificate Authority) | Emite y firma certificados; entidad de confianza |
| **RA** (Registration Authority) | Verifica identidad del solicitante |
| **Digital certificate (X.509)** | Vincula una clave pública con una identidad |
| **CRL / OCSP** | Listas/consultas para saber si un certificado fue **revocado** |
| **Root CA / Intermediate CA** | Cadena de confianza (*chain of trust*) |
| **CSR** | Solicitud de firma de certificado |

Un certificado contiene: sujeto, clave pública, emisor, vigencia, número de serie y firma de la CA.
**Usos:** HTTPS/TLS, VPN, email seguro (S/MIME), firma de código, autenticación.

## 6. Seguridad cuántica
- Las computadoras cuánticas amenazan la criptografía actual:
  - **Algoritmo de Shor** → rompe **RSA, ECC y Diffie-Hellman**.
  - **Algoritmo de Grover** → debilita la simétrica (se mitiga **duplicando** la longitud de clave, ej. AES-256).
- **Harvest now, decrypt later:** capturar hoy datos cifrados para descifrarlos cuando exista la capacidad.
- Respuestas: **Post-Quantum Cryptography (PQC)** — algoritmos resistentes a ataques cuánticos (estandarización del NIST); **QKD** (distribución cuántica de claves); **crypto-agility** (poder cambiar de algoritmo con facilidad).

## Autoevaluación
1. ¿Qué cifrado usa una sola clave? → **Simétrico**.
2. ¿Qué protege la integridad? → **Hash**.
3. ¿Con qué clave se firma digitalmente? → **Privada del emisor**.
4. ¿Qué entidad emite certificados? → **CA**.
5. ¿Qué algoritmo cuántico rompe RSA? → **Shor**.
