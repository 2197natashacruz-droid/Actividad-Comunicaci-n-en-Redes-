# Actividad: Comunicación en Redes 

### 1. 🌐 Conceptos base

| Concepto | Definición simple | Nivel técnico breve | Ejemplo real |
| --- | --- | --- | --- |
| **TCP** | Protocolo que envía datos de forma segura y ordenada | Orientado a conexión, usa confirmaciones (ACK) y retransmisión para asegurar entrega correcta | Descargar un archivo o cargar una página web |
| **UDP** | Protocolo que envía datos rápido sin asegurar entrega | No orientado a conexión, no verifica ni retransmite paquetes | Videollamadas o juegos online |
| **Puerto** | Número que identifica un servicio dentro de un dispositivo | Permite que múltiples aplicaciones usen la red en una misma IP (ej: 80, 443) | Navegar en web usa el puerto 80 o 443 |
| **HTTP** | Protocolo para transferir páginas web | Funciona sobre TCP, permite la comunicación entre navegador y servidor | Abrir una página como Google en el navegador |

### 2. ⚖️ TCP vs UDP (diferencia clave)

- **¿Cuál es la principal diferencia entre TCP y UDP?**  
TCP es orientado a conexión y asegura que los datos lleguen correctamente.  
UDP es sin conexión y envía datos sin verificar si llegaron bien.

- **¿Cuál es más confiable? ¿por qué?**  
TCP es más confiable porque confirma la entrega de datos, corrige errores y reenvía información perdida.

- **¿Cuál es más rápido? ¿por qué?**  
UDP es más rápido porque no verifica la entrega ni establece conexión, por lo que tiene menos procesos.

---

### 3. 🔌 Puertos (clave en desarrollo)

- **¿Qué es un puerto en una red?**  
Es un número que identifica a una aplicación o servicio dentro de un dispositivo conectado a la red.

- **¿Por qué una aplicación necesita un puerto?**  
Permite que varias aplicaciones usen la misma IP sin conflictos, diferenciando cada conexión.

- **¿Qué significan estos puertos?**
  - **80** → HTTP (web normal, sin cifrado)
  - **443** → HTTPS (web segura, con cifrado)
  - **3000** → Desarrollo (apps locales como React o Node.js)
  - **5432** → PostgreSQL (base de datos)


### 👉 Ejemplo developer

- **¿Qué pasa cuando ejecutas:**

npm run dev


Se inicia un servidor local en tu computador (localhost), normalmente en un puerto como `3000`.

Tu aplicación queda "escuchando" en ese puerto, y puedes verla en el navegador con:  
`http://localhost:3000`

---

### 4. 🌍 HTTP (HyperText Transfer Protocol)

- **¿Qué es HTTP?**  
Es un protocolo que permite la comunicación entre un cliente (navegador) y un servidor para transferir información en la web.

- **¿Cómo funciona una petición HTTP?**  
El cliente envía una solicitud (request) al servidor, el servidor la procesa y devuelve una respuesta (response) con datos o resultados.

- **¿Qué significan:**
  - **GET** → Obtener información (leer datos)
  - **POST** → Enviar información para crear algo nuevo
  - **PUT** → Actualizar información existente
  - **DELETE** → Eliminar información

### 👉 🔄 Flujo de comunicación

Frontend → Request → Backend → Response → Frontend


- **Frontend**: El usuario hace una acción (clic, formulario, etc.)
- **Request**: Se envía una petición HTTP al servidor
- **Backend**: Procesa la solicitud (lógica, base de datos)
- **Response**: Devuelve datos o resultado
- **Frontend**: Muestra la información al usuario

---

### 5. 🔗 Conexión directa con desarrollo (CRÍTICO)

- **¿Qué pasa cuando haces:**
fetch("http://localhost:3000/api
")


El frontend envía una petición HTTP al servidor local que está corriendo en tu computador (localhost) en el puerto 3000, solicitando el recurso `/api`.

- **¿Qué protocolo se usa?**  
HTTP (porque la URL comienza con `http://`)

- **¿Qué puerto?**  
3000 (indicado explícitamente en la URL)

- **¿Qué tipo de comunicación?**  
Cliente-servidor mediante HTTP request/response (el frontend pide y el backend responde)

---

### 6. 🛠️ Problemas reales (debugging)

- **¿Qué significa:**
  - **“Port already in use”?**  
  El puerto ya está siendo utilizado por otra aplicación, por lo que no puede iniciarse otro servicio en ese mismo puerto.

  - **“Connection refused”?**  
  El servidor rechazó la conexión, normalmente porque no está corriendo o no está escuchando en ese puerto.

  - **“Timeout”?**  
  La conexión tardó demasiado y se canceló, generalmente porque el servidor no respondió a tiempo.


- **¿Qué revisarías como developer?**

  - Ver si el servidor está corriendo (`npm run dev`)
  - Confirmar que el puerto es correcto (ej: 3000)
  - Revisar si otro proceso está usando el puerto
  - Validar la URL (`http://localhost:3000`)
  - Revisar errores en consola (frontend/backend)
  - Verificar firewall o bloqueos de red
  - Reiniciar el servidor o la app si es necesario

---

### 7. 🧪 Caso práctico real

**Escenario:**
> “Tu frontend no se conecta al backend”

- **¿Puede ser problema de puerto?**  
Sí. Si el frontend apunta a un puerto incorrecto (ej: 3000 vs 5000) o el backend no está escuchando en ese puerto, la conexión fallará.

- **¿Puede ser problema de protocolo?**  
Sí. Si el frontend usa `http://` y el backend requiere `https://` (o viceversa), el navegador puede bloquear la conexión.

- **¿Puede ser problema de red?**  
Sí. Puede haber bloqueos por firewall, CORS, mala configuración de red o el servidor no está accesible desde esa red.

---

**Resumen rápido:**  
Puerto incorrecto + protocolo incorrecto + problemas de red = frontend no conecta 🚫

### 8. 🧠 Analogía obligatoria

| Concepto | Analogía |
| --- | --- |
| TCP | Llamada telefónica: hay conexión, confirmas que la otra persona escucha y la información llega completa |
| UDP | Mensaje de voz o carta: se envía sin saber si llegó o si fue leído |
| Puerto | Número de departamento en un edificio: indica exactamente a quién va dirigido |
| HTTP | Idioma de comunicación: reglas que ambos usan para entenderse (como hablar español o inglés) |

## 🎁 BONUS

- **¿Qué es HTTPS?**  
Es la versión segura de HTTP que cifra la información para que no pueda ser leída por terceros.

- **¿Qué es REST?**  
Es un estilo de arquitectura para crear APIs donde se usan métodos HTTP (GET, POST, etc.) para interactuar con recursos.

- **¿Qué es un endpoint?**  
Es una URL específica dentro de una API donde puedes hacer una petición para obtener o enviar datos.

# 📚 Glosario básico: Comunicación en Redes

## 🌐 Conceptos clave

| Concepto | Definición simple |
|----------|------------------|
| TCP | Protocolo que envía datos de forma segura y ordenada |
| UDP | Protocolo rápido que envía datos sin asegurar entrega |
| Puerto | Número que identifica una aplicación en un dispositivo |
| HTTP | Protocolo que permite cargar páginas web |

---

## ⚖️ TCP vs UDP

- **TCP**: Más seguro y confiable  
- **UDP**: Más rápido pero menos seguro  

---

## 🔌 Puertos importantes

- **80** → HTTP  
- **443** → HTTPS  
- **3000** → Desarrollo local  
- **5432** → Base de datos (PostgreSQL)  

---

## 🌍 HTTP

- **Request**: Petición del cliente  
- **Response**: Respuesta del servidor  

### Métodos básicos

- **GET** → Obtener datos  
- **POST** → Crear datos  
- **PUT** → Actualizar  
- **DELETE** → Eliminar  

---

## 🔗 Conceptos clave en desarrollo

- **localhost**: Tu propio computador como servidor  
- **fetch()**: Forma de pedir datos a un servidor  

---

## 🛠️ Errores comunes

- **Port in use** → Puerto ocupado  
- **Connection refused** → Servidor apagado  
- **Timeout** → Servidor no responde  

---

## 🎁 BONUS

| Concepto | Definición |
|----------|-----------|
| HTTPS | HTTP seguro (con cifrado) |
| REST | Forma de crear APIs usando HTTP |
| Endpoint | URL donde haces una petición |
