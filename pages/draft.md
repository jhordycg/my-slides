---
src: ./pages/sesson-zero.md
---
---
layout: cover
hideInToc: true
background: https://images.unsplash.com/photo-1520022911530-fea50671df2e?q=80&w=1738&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D
mdc: true
---

# Sping Boot

## Tu Primer Paso para Crear Aplicaciones Java Sin Estrés

By: Jhordy Caceres ([@jhordycg]())

---
layout: default
hideInToc: true
---

# Table of content

<Toc/>


---
layout: features
image: https://spring.io/img/extra/microservices-6-dark.svg
---

# ¿Qué es Spring Boot?

Es una framework construido sobre el ecosistema de Spring, diseñado para simplificar el desarrollo, despliegue y gestion de aplicaciones basadas en Spring.

::features::

<v-clicks>

- ### <cib-github/>Open Source
    Código accesible y modificable, respaldado por una red global de desarrolladores que colaboran, reportan errores y proponen mejoras.

- ### <cib-read-the-docs/>Documentación detallada + tutoriales prácticos
    Guías paso a paso, ejemplos reales y referencias técnicas para acelerar el aprendizaje y la implementación de soluciones.

- ### <cib-stackoverflow/>Soporte robusto
    Acceso rápido a respuestas expertas, discusiones técnicas y soluciones validadas por la comunidad y los mantenedores del proyecto.

- ### <bi-boxes/>Enfoque en microservicios
    Diseñado para crear servicios independientes y escalables, facilitando el mantenimiento, la actualización y la escalabilidad selectiva.

- ### <cib-spring/>Ecosistema integrado
    Herramientas especializadas (seguridad, gestión de datos, procesos batch) que se integran sin esfuerzo, reduciendo la necesidad de librerías externas.

</v-clicks>

---
layout: iframe-right
url: https://start.spring.io/#!type=maven-project&language=java&platformVersion=3.4.2&packaging=jar&jvmVersion=17&groupId=dev.jhordycg.spring&artifactId=mi-first-app&name=My%20First%20App&description=My%20First%20Application%20for%20Spring%20Boot&packageName=dev.jhordycg.spring.demo&dependencies=web,lombok
---

# ¡Tu Primera App en Minutos! 👩💻

Para esto contamos con 2 enlaces, el primero es una manera facil de crear nuestro primer proyecto, y el segundo es una guía que nos proporciona Spring Boot para conocer y aprender sobre sus ecosistema.

> Requisitos necesitaremos tener instalado `Java 17` (con `Maven`) y un *IDE* o *Editor*  

<div class="flex">

<div class="w-full flex-1 text-center">

![Spring Initializr](/qr-initializr.png){.mx-auto .mb-2 .w-28}
[Spring Initializr](https://start.spring.io/#!type=maven-project&language=java&platformVersion=3.4.2&packaging=jar&jvmVersion=17&groupId=dev.jhordycg.spring&artifactId=mi-first-app&name=My%20First%20App&description=My%20First%20Application%20for%20Spring%20Boot&packageName=dev.jhordycg.spring.demo&dependencies=web,lombok){.font-size-3}

</div>

<br/>

<div class="w-full flex-1 text-center">

![Building an Application with Spring Boot](/qr-sbg-rest-app.png){.mx-auto .mb-2 .w-28}
[Building an Application with Spring Boot](https://spring.io/guides/gs/rest-service){.font-size-3}

</div>

</div>

---
layout: two-cols-header
---

# <cib-spring/> Spring Boot Starters: Gestión Simplificada de Dependencias

::left::

## 🔍 **Problema Tradicional**
- **Dependencias en cascada**:  
  Cada funcionalidad principal (ej: API REST) requiere múltiples dependencias secundarias (JSON, HTTP, serialización, etc.).  
  → Ejemplo: `A → B → C → D` (versiones específicas requeridas).

- **"Whack-a-Mole" de Versiones**:  
  Conflictos entre versiones de librerías interdependientes.  
  ⚠️ Ejemplo: `Librería X v1.5` solo funciona con `Librería Y v2.3`.

::right::

## 🚀 **Solución con Spring Boot Starters**

```xml
<!-- Ejemplo: spring-boot-starter-web -->
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-web</artifactId>
</dependency>
```

<br/>

```xml
<!-- Ejemplo: spring-boot-starter-data-jpa -->
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-data-jpa</artifactId>
</dependency>
```

---
layout: two-cols
hideInToc: true
---

## ✅ Beneficios Clave

**Paquetes Pre-testeados:**

- Todas las dependencias necesarias para una capacidad (ej: desarrollo web) en un solo starter.
- Versiones sincronizadas y compatibles.

**Reducción de Configuración:**

- De 10-15 dependencias manuales → 1 starter.

**Flexibilidad Controlada:**

- Posibilidad de override de versiones (con precaución ⚠️).
- Exclusión de dependencias no requeridas.

::right::

## ⚠️ Advertencias Importantes

- **Al Modificar Versiones**:  
  \> *"Aumente el nivel de pruebas para mitigar riesgos"*

- **Al Excluir Dependencias**:  
  \> Verificar impactos en funcionalidades relacionadas.

---
hideInToc: true
---

# 📊 Impacto General

| Aspecto|	Antes|	Con Starters|
|----------|------|---------|
| Archivo de Build	|Largo y complejo|	Compacto y declarativo|
| Mantenimiento|	Alto esfuerzo de sincronización	|Automatizado|
| Testing|	Requerido para cada combinación|	Reducido (pre-validado)|

<br/>

✨ **Conclusión**: Los starters eliminan el "caza-conflictos" y aceleran el desarrollo con dependencias probadas y unificadas.

---
layout: two-cols-header
---
# ⚙️ Autoconfiguración en Spring Boot: La "Magia" de la Productividad

::left::

## 🚀 **¿Qué es la Autoconfiguración?**

- **Superpoder del desarrollador**: Elimina código repetitivo mediante convenciones probadas\.  
- **Filosofía**: *"Convención sobre configuración"* → Menos código, más funcionalidad\.  
- **Ejemplo clave**:  
  ```java
  // Spring Data JPA genera consultas automáticamente:
  List<User> findByEmail\(String email\); // ¡Sin implementación\!  
  ```

::right::

## 🎯 **Beneficios Clave**

### 1. **Configuración Inteligente por Defecto**

- **Base de datos**:  
  - Conexiones automáticas (abrir/cerrar).  
  - Consultas generadas desde nombres de métodos.  
- **Mensajería (Ej: RabbitMQ/Kafka)**:  
  - Valores predeterminados para desarrollo: `localhost:5672`, sin credenciales\.  

---
layout: two-cols
hideInToc: true
---

### 2. **Enfoque "Developer-First"**
- **Entornos de desarrollo**:  
  ```properties
  # application.properties (opcional para desarrollo)
  spring.datasource.url=jdbc:h2:mem:testdb  
  spring.rabbitmq.host=localhost  
  ```
- **Equipos**: Configuraciones compartidas que funcionan "out-of-the-box".  

### 3. **Flexibilidad Controlada**
- **Personalización**:  
  ```properties
  # Override para producción  
  spring.datasource.url=jdbc:postgresql://prod-db:5432/mydb  
  ```
- **Deshabilitar autoconfiguración**:  
  `@SpringBootApplication(exclude = {DataSourceAutoConfiguration.class})`

::right::

## ⚠️ **Casos de Uso Atípicos (10-20\%)**

| Escenario                | Solución                          |  
|--------------------------|-----------------------------------|  
| Configuración muy específica | Definir propiedades o beans manualmente |  
| Librería no estándar      | Excluir autoconfiguraciones       |  

> **⚠️ Advertencia**: Al overridear configuraciones\, aumenta el testing para mitigar riesgos\.

---
hideInToc: true
---

## 📊 **Impacto en Productividad**

| **Sin Spring Boot**      | **Con Spring Boot**               |  
|--------------------------|-----------------------------------|  
| 100+ líneas de configuración | 0-10 líneas (convenciones)      |  
| Debugging de conexiones   | Conexiones gestionadas automáticamente |  
| Setup manual por entorno  | Defaults listos para desarrollo   |  

<br/>

✨ **Conclusión**: La autoconfiguración elimina el "código boilerplate", permitiéndote enfocarte en **lógica de negocio**, no en configuraciones repetitivas. ¡Tu superpoder para ser 10x más productivo! 🦸♂️

---

# Despliegué Simple

---

# Resume