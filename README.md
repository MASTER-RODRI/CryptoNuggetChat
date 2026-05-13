🛑 CryptoNugget

Un micro-protocolo de comunicación efímero, seguro y con mutación de claves (Ratcheting).
Nada se guarda, todo se transforma.

👁️ ¿Qué es CryptoNugget?

CryptoNugget no es solo un chat; es una demostración en vivo de criptografía avanzada empaquetada para la comunidad. Utiliza un concepto conocido como Ratcheting (Trinquete Criptográfico).

A diferencia de los cifrados tradicionales donde una contraseña protege todo, en CryptoNugget las claves se devoran a sí mismas. Cada vez que envías o recibes un mensaje, la clave de cifrado se utiliza para generar una nueva y luego se destruye. Si alguien roba tu dispositivo hoy, le será matemáticamente imposible descifrar los mensajes de ayer.

✨ Características Excéntricas

🧬 Mutación de ADN (Ratcheting): Implementado con AES-256-GCM y HMAC-SHA256. Máxima entropía y seguridad de grado militar.

🚫 Cero Servidores, Cero Rastros: Todo el cifrado ocurre en la memoria local de tu navegador usando la API nativa WebCrypto. No hay bases de datos, no hay logs. Si recargas la página, la sesión deja de existir en este universo.

🔳 Sincronización Visual: Generación de Códigos QR excéntricos (circulares y personalizados con el logo del proyecto) para establecer conexiones seguras en persona sin enviar claves por internet.

💻 Motor Desacoplado: El motor criptográfico es un objeto de JavaScript puro sin dependencias. Listo para que la comunidad lo integre en sus propios proyectos.

🚀 Guía de Inicio Rápido (Para Usuarios)

No necesitas instalar Node.js ni bases de datos. Todo funciona en el cliente.

Asegúrate de tener los archivos index.html y tu logo avatar1.png en la misma carpeta.

Abre index.html en cualquier navegador web moderno (Chrome, Firefox, Brave, Safari).

Para iniciar un canal: Haz clic en "Crear Conexión". El sistema generará una semilla cuántica y mostrará un Código QR.

Para unirte: La otra persona debe escanear el QR o pegar el enlace de invitación en la sección "Unirse a Sesión".

¡Comiencen a chatear! Observa el panel izquierdo para ver cómo el "ADN" de sus claves muta en tiempo real con cada mensaje.

🛠️ Guía de Integración (Para Desarrolladores)

¿Quieres usar CryptoNugget para cifrar JSONs, guardar archivos seguros en la nube de forma local, o crear tu propio protocolo? Es extremadamente fácil.

El motor criptográfico está contenido completamente en la constante NuggetEngine. Solo cópiala a tu proyecto.

Ejemplo de Uso en tu propio código JS:

// 1. Instanciar el motor (puedes importarlo si lo separas en un módulo)
const MiNugget = Object.create(NuggetEngine);

// 2. Obtener una semilla (puedes usar la que te genera la App Web)
const semillaMaestra = "TU_SEMILLA_EN_BASE64_AQUI";

// 3. Inicializar (Debes decidir quién es el iniciador y quién el receptor)
// Nodo A (Iniciador)
await MiNugget.inicializar(semillaMaestra, true);

// 4. Cifrar cualquier texto o JSON stringificado
const datosSecretos = JSON.stringify({ usuario: "Comunidad", nivel: "Paranoico" });
const payloadCifrado = await MiNugget.cifrar(datosSecretos);

console.log("Criptograma mutante:", payloadCifrado);

// 5. Descifrar (El Nodo B, inicializado con 'false', haría esto)
// const datosDescifrados = await NodoB.descifrar(payloadCifrado);


Notas sobre Seguridad:

Aislamiento: El NuggetEngine utiliza window.crypto.subtle, lo que significa que las operaciones son ejecutadas por el motor C/C++ del navegador. Es rápido y resistente a ataques de tiempo (Timing Attacks).

Sincronización Estricta: El protocolo espera que los mensajes se procesen en orden. Si pierdes un paquete en la red, el ADN se desincronizará por diseño (protección contra ataques de repetición/replay attacks).

🎨 Personalización

Logo del QR: Reemplaza el archivo avatar1.png por cualquier imagen de tu preferencia para cambiar el logo que aparece en el centro del código de sincronización.

Colores: La interfaz utiliza TailwindCSS a través de CDN. Puedes modificar la paleta de colores en el bloque <script> de configuración en el <head> del archivo index.html.

Construido para la comunidad. Nada se guarda, todo se transforma.