# Etapa VI y VII: Modelado de Ataques y Análisis de Riesgo

## Etapa VI: Modelado de Ataques (Attack Tree)
[cite_start]El objetivo principal del ataque modelado es comprometer los **Datos de Usuario** (User data)[cite: 13].

### Vectores de Ataque Identificados
1. **Inyección SQL (SQL Injection):**
   * [cite_start]El atacante aprovecha la **falta de sentencias preparadas** (Lack of prepared statements) para manipular consultas[cite: 14, 15].
2. **Secuestro de Sesión (Session Hijacking):**
   * [cite_start]El atacante explota el uso de **credenciales de inicio de sesión débiles** (Weak login credentials) para ganar acceso[cite: 16, 17].

## Etapa VII: Análisis de Riesgo e Impacto
Para reducir el riesgo y mitigar los impactos negativos en el negocio, se deben implementar los siguientes controles de seguridad:
1. [cite_start]**Sentencias Preparadas:** Implementar parametrización en todas las consultas SQL para evitar inyecciones[cite: 2].
2. [cite_start]**Cifrado AES:** Asegurar que los datos sensibles almacenados utilicen cifrado simétrico robusto[cite: 2].
3. [cite_start]**Hashing SHA-256:** Utilizar funciones hash para proteger la integridad y confidencialidad de las contraseñas[cite: 2].
4. [cite_start]**Infraestructura PKI:** Implementar certificados digitales para asegurar las comunicaciones y la identidad entre clientes y servidor[cite: 2].
