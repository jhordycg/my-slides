---
layout: cover
mdc: true
background: https://images.unsplash.com/photo-1658486428378-ea8f6a76acc2?q=80&w=3264&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D
hideInToc: true
---

# Microservicios

Pequeños héroes, grandes soluciones

<footer class="absolute bottom-0px right-0px mx-6 my-4 text-md text-color-zinc-500 font-weigth-bold">

By: Jhordy Caceres ([@jhordycg](https://slides.jhordycg.dev))

</footer>

---
hideInToc: true
---

# Temario

<Toc/>


---
layout: two-cols-header
---

# ✨ **¿Qué son los microservicios?**
Los microservicios son un estilo de arquitectura donde una aplicación se divide en servicios pequeños e independientes que se comunican entre sí mediante APIs.

::left::

```mermaid {scale: 0.4}
graph TD;
    subgraph Monolito
        UI1[UI] -->|Llamada interna| APP1[Aplicación Monolítica]
        APP1 -->|Accede| DB1[(Base de Datos Única)]
    end

    subgraph Microservicios
        UI2[UI] -->|API Gateway| API[Gateway]
        API -->|Llamada REST| MS1[Microservicio 1]
        API -->|Llamada REST| MS2[Microservicio 2]
        API -->|Llamada REST| MS3[Microservicio 3]
        
        MS1 -->|Accede| DB2[(DB 1)]
        MS2 -->|Accede| DB3[(DB 2)]
        MS3 -->|Accede| DB4[(DB 3)]
    end

    style Monolito fill:#bfaa,stroke:#333,stroke-width:2px
    style Microservicios fill:#cb6,stroke:#333,stroke-width:2px
```

::right::

<v-click>

🌍 **Características principales:**

</v-click>

<br/>

<v-clicks>

- Independencia en desarrollo y despliegue.
- Escalabilidad flexible.
- Uso de tecnologías variadas.
- Diseño basado en dominios.

</v-clicks>
<br/>
<br/>
<br/>
<br/>
<br/>

---
layout: statement
---

# Evolución de la Arquitectura de Microservicios

```mermaid {scale: 0.5}
timeline
    1990 : Arquitectura Monolítica - Aplicaciones centralizadas con bases de datos únicas.
    2000 : Arquitectura de N-Tier - Separación en capas (Presentación, Lógica, Datos).
    2005 : SOA (Arquitectura Orientada a Servicios) - Servicios reutilizables con ESB (Enterprise Service Bus).
    2010 : Primeros Microservicios - Independencia de servicios, comunicación vía APIs REST.
    2014 : Popularización - Empresas como Netflix, Amazon y Google adoptan microservicios a gran escala.
    2017 : Kubernetes y Contenedores - Orquestación de servicios con Docker y Kubernetes.
    2020 : Serverless y FaaS - Microservicios sin servidor, ejecución basada en eventos.
    2023 : IA y Observabilidad - Integración con inteligencia artificial y herramientas avanzadas de monitoreo.
```

---
layout: two-cols-header
class: p-4
hideInToc: true
---

# 🛠 **Beneficios y Desafíos**

::left::

<v-click>

## ✅ **Beneficios**

</v-click>
<br/>
<v-clicks>

1. **Escalabilidad**: Se pueden escalar servicios específicos sin afectar a otros.
2. **Resiliencia**: Fallos en un servicio no impactan a toda la aplicación.
3. **Agilidad y Rápida Implementación**: Equipos trabajan en paralelo en diferentes servicios.
4. **Flexibilidad Tecnológica**: Cada servicio puede usar diferentes lenguajes y bases de datos.

</v-clicks>

::right::

<v-click>

## ❌ **Desafíos**

</v-click>
<br/>
<v-clicks>

1. **Complejidad Operativa**: Gestionar múltiples servicios requiere herramientas avanzadas.
2. **Consistencia de Datos**: No hay una base de datos centralizada.
3. **Seguridad**: Más puntos de acceso implican más riesgos.
4. **Monitoreo y Depuración**: Diagnosticar errores en entornos distribuidos es más complejo.

</v-clicks>

<br/>
<br/>

---
layout: default
---

# 🛡 **Arquitectura y Tecnologías Clave**

<br/>
<br/>
<br/>

```mermaid {scale: 0.37}
graph TD;
    
    subgraph Frontend
        React[React.js] -->|UI| API_Gateway
        Angular[Angular] -->|UI| API_Gateway
        Vue[Vue.js] -->|UI| API_Gateway
    end
    
    subgraph API Gateway
        API_Gateway[NGINX / Kong / Traefik] -->|Encaminamiento| Microservicios
    end
    
    subgraph Microservicios
        MS1[Spring Boot] -->|Lógica| DB1[PostgreSQL]
        MS2[Node.js] -->|Lógica| DB2[MongoDB]
        MS3[Go] -->|Lógica| DB3[MySQL]
        MS4[Python / FastAPI] -->|Lógica| DB4[Redis]
    end
    
    subgraph Mensajería
        Kafka[Apache Kafka] -->|Eventos| MS1
        RabbitMQ[RabbitMQ] -->|Mensajería| MS2
    end

    subgraph Autenticación
        Auth[Keycloak / Auth0] -->|JWT / OAuth| API_Gateway
    end

    subgraph Observabilidad
        Prometheus[Prometheus] -->|Métricas| Grafana[Grafana]
        ELK[Elastic Stack] -->|Logs| API_Gateway
    end
    
    subgraph Infraestructura
        K8s[Kubernetes] -->|Orquestación| Microservicios
        Docker[Docker] -->|Contenedores| K8s
    end
```

---
layout: two-cols
hideInToc: true
---


<v-click>

🏰 **Diseño de Microservicios**

</v-click>

<br/>

<v-clicks>

- **API Gateway**: Maneja peticiones, autenticación y balanceo de carga.
- **Service Discovery**: Localiza instancias de microservicios dinámicamente.
- **Base de datos por servicio**: Independencia en almacenamiento.

</v-clicks>

::right::

<v-click>

💻 **Tecnologías Comunes**

</v-click>

<br/>

<v-clicks>

- **Orquestación & Contenedores**: Docker, Kubernetes
- **Mensajería**: Kafka, RabbitMQ
- **API Gateway**: Kong, Nginx, AWS API Gateway
- **Monitoreo**: Prometheus, Grafana, ELK Stack

</v-clicks>

---
hideInToc: true
---

# 💡💻 **Caso de Uso: Plataforma de E-commerce**

```mermaid {scale: 0.7}
graph TD;
    Usuario[🧑‍💻 Usuario] -->|Inicia sesión| Autenticacion[🔑 Servicio de Autenticación];
    Usuario -->|Explora productos| Catalogo[📦 Servicio de Catálogo de Productos];
    Usuario -->|Realiza pago| Pagos[💳 Servicio de Pagos];
    Pagos -->|Confirma pago| Notificaciones[📩 Servicio de Envío de Notificaciones];
    Pagos -->|Notifica a catálogo| Catalogo;
    Catalogo -->|Muestra productos| Usuario;
    Notificaciones -->|Envía confirmaciones| Usuario;
```

<br/>

<v-clicks>

- Servicio de Autenticación
- Servicio de Catálogo de Productos
- Servicio de Pagos
- Servicio de Enío de Notificaciones

</v-clicks>

---
hideInToc: true
---

# ⚖️ **Comparación: Monolito vs Microservicios**

| Característica | Monolito | Microservicios |
|---------------|----------|---------------|
| Despliegue | Unido | Independiente |
| Escalabilidad | Limitada | Alta |
| Complejidad | Baja | Alta |
| Tecnología | Uniforme | Variada |

<v-click>

✅ **Conclusiones**

</v-click>

<v-clicks>

- Los microservicios ofrecen flexibilidad y escalabilidad, pero requieren buenas prácticas DevOps.
- Es clave contar con herramientas de monitoreo y gestión de despliegues.
- No siempre son la mejor opción: considerar según necesidades del negocio.

</v-clicks>

---
layout: quote
hideInToc: true
---

# *"En un sistema donde reina el silencio, se extinguiría la chispa de la vida; es a través de la comunicación que cada alma digital revela su verdadero significado."*


by: ChatGPT

---
layout: intro
---

# REST API: Una forma de comunicarse

En este mar de opciones, analizaremos una forma específica de comunicación que mantiene a los microservicios en sintonía.

---
hideInToc: true
---
# ¿Qué es?

Es una interfaz que usan 2 partes para intercambiar información sobre internet.

![alt text](/image-1.png){.mx-auto .mt-16.w-120}

---
layout: default
---

# ¿Qué es una API?

Es la definición de las reglas del servidor del recurso, la cual los clientes deben seguir para comunicarse con el.

- **Cliente:**
La parte que desea acceder a cierto recurso en la web.

- **Recurso:**
Es la información que un servidor ofrece a sus clientes en una variedad diversa de formatos.

- **Servidor:**
Es el propietario o custodio de uno o muchos recursos.

![alt text](https://images.ctfassets.net/8vofjvai1hpv/6fdaVO1azF8fIenqbXdYG8/22cc0d8c6141ef1a3fa56d69b7f9391e/api2.jpg?w=992&h=623&q=100&fm=webp&bg=transparent){.w-96 .m-auto .mt-6}

---
layout: two-cols-header
---

# ¿Qué es REST?

La transferencia de estado representacional es una arquitectura de software que establece las condiciones de como un API debe comportarse. Permitiendo tener una comunicación confiable y de alto rendimiento a escala.

::left::

Principios:

- **Interfáz uniforme** 
- **Sin estados**
- **Sistema en capas** 
- **Cacheabilidad** 
- **Código a demanda** 

::right::

Beneficios: 

- **Escalabilidad:** No maneja estados y es cacheable.
- **Flexibilidad:** Tiene un sistema de capas.
- **Independencia:** Es agnóstico a la tecnología

<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>

---
layout: two-cols-header
---

# Componentes de un RESTful API

::left:: 

<v-clicks>

- **URI:** Identificador ùnico del recurso.
- **Método:** GET, POST, PUT, PATCH y DELETE
- **Cabeceras:** Metadatos de un request.
- **Data:** Aplica para los metodos POST, PUT y PATCH.
- **Parámetros:** Cookie, Query y Path. 

</v-clicks>

::right::

```mermaid {scale: 0.5}
sequenceDiagram
    participant Client as Cliente
    participant API as Servidor REST
    participant DB as Base de Datos

    Client->>API: Solicitud HTTP (GET/POST/PUT/DELETE)
    API->>DB: Consulta o actualización de datos
    DB-->>API: Devuelve los datos
    API-->>Client: Respuesta en formato JSON o XML
```

<br/>
<br/>
<br/>
<br/>

---
hideInToc: true
---

# 📌 Métodos HTTP y sus Características

| Método  | Descripción | Idempotente | Seguro | Cuerpo en la solicitud | Cuerpo en la respuesta |
|---------|------------|-------------|--------|------------------------|------------------------|
| **GET**    | Obtiene un recurso. | ✅ Sí  | ✅ Sí  | ❌ No | ✅ Sí |
| **POST**   | Crea un nuevo recurso. | ❌ No | ❌ No | ✅ Sí | ✅ Sí |
| **PUT**    | Reemplaza un recurso existente. | ✅ Sí | ❌ No | ✅ Sí | ✅ Sí |
| **PATCH**  | Modifica parcialmente un recurso. | ❌ No | ❌ No | ✅ Sí | ✅ Sí |
| **DELETE** | Elimina un recurso. | ✅ Sí | ❌ No | ❌ No | ❌ No o ✅ Sí |

---
hideInToc: true
---

# 📌 Explicación de Conceptos  

- **Idempotente:** Si se ejecuta varias veces, el resultado es el mismo.  
- **Seguro:** No modifica el recurso en el servidor.  
- **Cuerpo en la solicitud:** Indica si permite enviar datos en la petición.  
- **Cuerpo en la respuesta:** Indica si devuelve datos en la respuesta.  

🚀 **Siguiendo estas características, puedes diseñar APIs RESTful más eficientes.**

---
layout: two-cols-header
---

# Métodos de Autenticación

Un servidor deberia autenticar la solicitud antes de ser procesada. La *authenticación* es el proceso de verificar una identidad.

Hay 4 métodos comunes:

::left::

- Basic authentication
  ```http
  GET /api/resource HTTP/1.1
  Host: example.com
  Authorization: Basic dXNlcm5hbWU6cGFzc3dvcmQ=
  ```
- Bearer authentication
  ```http
  GET /api/protected-resource HTTP/1.1
  Host: example.com
  Authorization: Bearer your-access-token
  ```

::right::

- API keys
  ```http
  GET /api/resource HTTP/1.1
  Host: example.com
  x-api-key: your-api-key

  GET /api/resource?api_key=your-api-key HTTP/1.1
  Host: example.com
  ```
- OAuth
  ```http
  POST /oauth/token HTTP/1.1
  Host: auth.example.com
  Content-Type: application/x-www-form-urlencoded

  grant_type=client_credentials&client_id=client-id&
  client_secret=client-secret
  ```

<br/>
<br/>
<br/>

---
layout: two-cols-header
---

# 📌 Estados HTTP

Los códigos de estado HTTP indican el resultado de una solicitud al servidor. Se dividen en cinco categorías principales:

::left::

## ✅ 2xx - Respuestas Exitosas  
- **200 OK**  
- **201 Created**  
- **204 No Content**  

## 🔄 3xx - Redirecciones  
- **301 Moved Permanently**
- **302 Found**  
- **304 Not Modified**  

::right::

## ⚠️ 4xx - Errores del Cliente  
- **400 Bad Request**  
- **401 Unauthorized**  
- **403 Forbidden**  
- **404 Not Found**  

## 🚨 5xx - Errores del Servidor
- **500 Internal Server Error**
- **502 Bad Gateway**
- **503 Service Unavailable**
- **504 Gateway Timeout**

---
layout: two-cols-header
hideInToc: true
---

# 🌱 Modelo de Madurez de Richardson para APIs RESTful

El modelo de madurez de Richardson clasifica las APIs RESTful en **cuatro niveles** según su grado de adopción de principios REST.

::left::

## 🌑 Nivel 0

- Se utiliza HTTP solo como un **túnel de transporte**.  
- Todas las solicitudes van a una única URL (`/api`).  
- Se usa **POST** para todas las operaciones.  
- Ejemplo: Un servicio SOAP sobre HTTP.

::right::

## 🌒 Nivel 1

- La API define **recursos** en la URL (`/usuarios`, `/productos`).  
- Sigue utilizando **un único verbo HTTP** (por lo general, **POST**).  
- Ejemplo: Una API que usa `/usuarios/crear`, `/usuarios/eliminar` en lugar de métodos HTTP.

---
layout: two-cols
hideInToc: true
---


## 🌓 Nivel 2

- Uso de los verbos HTTP estándar:  
  - **GET** → Obtener datos.  
  - **POST** → Crear un recurso.  
  - **PUT/PATCH** → Actualizar un recurso.  
  - **DELETE** → Eliminar un recurso.  
- Ejemplo:
  ```http
  GET /usuarios/1  → Obtener usuario con ID 1
  DELETE /usuarios/1  → Eliminar usuario con ID 1
  ```

::right::

## 🌕 Nivel 3

- Respuestas incluyen hipervínculos para guiar el uso de la API.
- Facilita la exploración de recursos sin conocer todas las URLs de antemano.
- Ejemplo:
  ```json
  {
    "id": 1,
    "nombre": "Juan",
    "email": "juan@example.com",
    "_links": {
      "self": { "href": "/usuarios/1" },
      "amigos": { "href": "/usuarios/1/amigos" }
    }
  }
  ```

---
layout: section
hideInToc: true
---

# Aplicando lo aprendido

---
layout: two-cols-header
---

# 🏆 Ejercicio 1: Aplicando Métodos HTTP

Estás diseñando una API RESTful para gestionar una tienda en línea. La API debe manejar productos y clientes, permitiendo su creación, modificación, consulta y eliminación.  

Tu tarea es **asignar el método HTTP correcto** para cada operación y escribir la URI adecuada.

::left::

**Ejemplo para el primer caso:**  
- Obtener la lista de productos
  ```http
  GET /productos
  ```

**Ejercicios:**

- Obtener la lista de productos
- Agregar un nuevo producto

<br/>
<br/>
<br/>

::right::

- Consultar los detalles del producto con ID 10
- Actualizar completamente el producto con ID 10
- Modificar solo el precio del producto con ID 10
- Eliminar el producto con ID 10
- Obtener la lista de clientes
- Registrar un nuevo cliente
- Obtener los pedidos de un cliente con ID 5
- Restablecer la contraseña del cliente con ID 5

---
layout: two-cols-header
---

# 🏆 Ejercicio2: Aplicando Correctamente los Códigos de Estado HTTP

Estás desarrollando una API RESTful para un sistema de reservas de hoteles.  
Los clientes pueden crear, consultar, modificar y cancelar sus reservas a través de la API.  

Tu tarea es **asignar el código de estado HTTP correcto** para cada situación descrita.

::left::

- Un cliente solicita la lista de hoteles disponibles con éxito.
  ejemplo: `200 OK`
- Se intenta reservar una habitación, pero no hay disponibilidad.
- Se crea correctamente una nueva reserva.
- Se intenta acceder a una reserva inexistente.
- El cliente intenta modificar una reserva, pero no está autenticado.

::right::

- Se actualiza correctamente la reserva con nuevos datos.
- Se elimina una reserva exitosamente.
- Se intenta eliminar una reserva que ya fue cancelada.
- Un cliente envía datos inválidos al hacer una reserva (ej. fecha incorrecta).
- Ocurre un error inesperado en el servidor al procesar una reserva.


---
layout: center
hideInToc: true
---

# **¡Gracias! 🚀**