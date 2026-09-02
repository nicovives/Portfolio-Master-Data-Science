# 🏢 Tokenización de Real World Assets (RWA): Mercado Inmobiliario

> ⚠️ **Nota:** Este repositorio aloja la memoria y documentación oficial del Trabajo de Fin de Máster (TFM). El código fuente completo (Smart Contracts, tests y dApp) se encuentra en el repositorio de desarrollo: **[nicovives/TFM-TokenizacionRWA](https://github.com/nicovives/TFM-TokenizacionRWA)**.

## 📖 Contexto del Proyecto
El mercado inmobiliario tradicional sufre de altas barreras de entrada, extrema iliquidez y una fuerte dependencia de procesos manuales y sistemas centralizados. Este proyecto desarrolla una solución tecnológica basada en la **tokenización de Real World Assets (RWA)** mediante tecnología Blockchain.

El objetivo es democratizar la inversión mediante el fraccionamiento de la propiedad. Al transformar activos físicos en estructuras de datos programables e inmutables, se eliminan intermediarios innecesarios y se crea un mercado mucho más accesible y líquido.

## ⚖️ Marco Regulatorio y Estándares
La emisión de activos del mundo real en la blockchain requiere una base legal sólida. Este proyecto alinea la arquitectura técnica con la regulación financiera actual:
* **Regulación y Compliance:** Análisis e integración de los requisitos exigidos por el Reglamento europeo **MiCA** (Markets in Crypto-Assets) y la Ley 6/2023 de los Mercados de Valores en España.
* **Estándares de Tokens:** Uso del estándar **ERC-20** para garantizar la liquidez y fungibilidad de las fracciones de propiedad, evaluando conjuntamente el estándar **ERC-3643** para la emisión autorizada y el cumplimiento normativo de *Security Tokens*.

## 🏗️ Arquitectura Descentralizada (dApp)
El desarrollo práctico se despliega sobre la Ethereum Virtual Machine (EVM), garantizando la ejecución imparcial de acuerdos mediante Smart Contracts. La plataforma utiliza un patrón de diseño **Factory**:

* **Contrato `Mercado`:** Actúa como el orquestador principal. Es la fábrica encargada de gestionar los activos globales y desplegar dinámicamente nuevas propiedades.
* **Contratos `Inmueble`:** Cada activo inmobiliario se instancia como un contrato independiente herederado de las librerías de seguridad de **OpenZeppelin**.
* **Role-Based Access Control (RBAC):** Sistema granular de permisos que protege funciones críticas, diferenciando entre administradores del mercado, oráculos de validación e inversores.

## 📊 Validación y Análisis de Eficiencia
Para asegurar la viabilidad de la plataforma en un entorno productivo, se ejecutó un pipeline de validación técnica y financiera:
* **Test Coverage (100%):** Batería de pruebas unitarias que superan con un éxito total la validación de los flujos de control de acceso (RBAC) y la precisión matemática en el fraccionamiento y transacciones de tokens.
* **Auditoría de Costes (Gas Optimization):** El análisis de despliegue e interacción demuestra empíricamente que los costes operativos en la red (Gas) derivados de una compraventa fraccionada son drásticamente inferiores a los gastos notariales y registrales del circuito tradicional.