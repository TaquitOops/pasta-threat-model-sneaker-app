# Modelado de Amenazas: Aplicación Móvil de Sneakers (Framework PASTA)

[cite_start]Este repositorio documenta el análisis de seguridad realizado para una nueva aplicación móvil de compra y venta de calzado para entusiastas y coleccionistas[cite: 1]. [cite_start]Se ha utilizado el marco **PASTA** (Process for Attack Simulation and Threat Analysis) para identificar riesgos y definir controles de seguridad antes del lanzamiento[cite: 1].

## 1. Objetivos de Negocio (Etapa I)
[cite_start]De acuerdo con la descripción de la aplicación, se han identificado los siguientes objetivos principales[cite: 9, 10]:
* [cite_start]**Privacidad de Datos:** Garantizar que los usuarios se sientan seguros al registrarse y gestionar sus cuentas, tratando su información de manera responsable[cite: 9, 10].
* [cite_start]**Integridad en las Transacciones:** Asegurar que las ventas sean claras, rápidas de procesar y cuenten con una gestión de pagos legalmente sólida para evitar problemas jurídicos[cite: 9, 10].
* [cite_start]**Experiencia de Usuario Segura:** Facilitar la comunicación directa entre compradores y vendedores mediante mensajes y calificaciones, manteniendo la confianza en la plataforma[cite: 9, 10].

## 2. Alcance Tecnológico y Requisitos (Etapa II)
[cite_start]La aplicación utiliza una infraestructura moderna que requiere atención específica en los siguientes puntos[cite: 1, 10, 11]:
* [cite_start]**SQL (Prioridad Alta):** Es la tecnología crítica para almacenar el inventario y los datos de usuarios[cite: 11, 14]. [cite_start]Se prioriza su seguridad debido al riesgo de inyecciones SQL identificado en el modelado de ataques[cite: 13, 14, 15].
* [cite_start]**Infraestructura de Clave Pública (PKI):** Utiliza algoritmos como AES (para datos sensibles como tarjetas de crédito) y RSA (para el intercambio de claves entre la app y el dispositivo)[cite: 10].
* [cite_start]**Funciones Hash (SHA-256):** Implementadas para proteger contraseñas y números de tarjetas, convirtiendo datos sensibles en compendios de 256 bits no reversibles[cite: 10, 11].

## 3. Descomposición y Modelado (Etapas III y VI)
### Diagrama de Flujo de Datos (DFD)
[cite_start]Se analizó el proceso de búsqueda de productos[cite: 3, 6, 7]:
* [cite_start]**Usuario:** Inicia la búsqueda de zapatillas[cite: 4, 9].
* [cite_start]**Proceso:** El sistema consulta el inventario actual[cite: 7, 10].
* [cite_start]**Base de Datos:** Devuelve los listados disponibles al usuario[cite: 5, 10].

### Árbol de Ataque
[cite_start]El objetivo del atacante es comprometer los **Datos de Usuario**[cite: 13]. Los vectores identificados son:
1.  [cite_start]**Inyección SQL:** Explotando la falta de sentencias preparadas en el código[cite: 14, 15].
2.  [cite_start]**Secuestro de Sesión:** Aprovechando credenciales de inicio de sesión débiles[cite: 16, 17].

## 4. Análisis de Amenazas y Vulnerabilidades (Etapas IV y V)
[cite_start]Basado en el análisis, se definen los siguientes puntos críticos[cite: 1, 13, 14, 16, 17]:
* **Amenazas Potenciales:**
    * [cite_start]Inyección de código malicioso en la base de datos (Externa)[cite: 14].
    * [cite_start]Acceso no autorizado a cuentas de usuario mediante robo de sesión (Externa/Interna)[cite: 16].
* **Vulnerabilidades del Sistema:**
    * [cite_start]**Código:** Ausencia de sentencias preparadas (prepared statements) para validar entradas de usuario[cite: 15].
    * [cite_start]**Autenticación:** Políticas de contraseñas débiles que facilitan ataques de fuerza bruta o secuestro de cuenta[cite: 17].

## 5. Controles de Seguridad y Defensas (Etapa VII)
[cite_start]Para mitigar los riesgos identificados, se han seleccionado estos 4 controles esenciales[cite: 10, 11, 13, 15]:
1.  [cite_start]**Validación de Entradas (Sentencias Preparadas):** Implementación obligatoria de consultas SQL parametrizadas para prevenir ataques de inyección[cite: 15].
2.  [cite_start]**Cifrado Robusto (AES/RSA):** Asegurar que toda la información financiera y personal esté cifrada tanto en tránsito como en reposo[cite: 10].
3.  [cite_start]**Hashing de Credenciales (SHA-256):** Almacenamiento seguro de contraseñas para que, en caso de brecha, la información no sea legible[cite: 10, 11].
4.  [cite_start]**Autenticación Multifactor (MFA):** Reforzar el inicio de sesión para neutralizar la vulnerabilidad de credenciales débiles y prevenir el secuestro de sesiones[cite: 1, 17].

---
[cite_start]*Análisis realizado como parte del programa de Ciberseguridad utilizando las plantillas oficiales de PASTA[cite: 1].*
