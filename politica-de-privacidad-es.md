# Política de Privacidad y Tratamiento de Datos Personales — Pockit

**Última actualización:** 28 de octubre de 2026  
**Vigencia:** desde la fecha de publicación

Esta política describe cómo la aplicación móvil **Pockit** (la "App") maneja tu información, en cumplimiento de la Ley Estatutaria 1581 de 2012, el Decreto 1377 de 2013 y demás normas concordantes de la República de Colombia, así como de los lineamientos de privacidad del App Store de Apple.

## 1. Responsable

- **Nombre:** Juan Marulanda (persona natural, desarrollador independiente)
- **Domicilio:** Bogotá, Colombia
- **Correo electrónico de contacto:** feedbackpockit@gmail.com

## 2. Principio esencial: tus datos se quedan en tu dispositivo

Pockit funciona **en tu iPhone y, por defecto, sin conexión a servidores**. Salvo por las funciones opcionales de importación automática (sección 7), la App:

- **No recolecta, no transmite y no almacena** tus datos personales o financieros en servidores propios ni de terceros.
- **No requiere crear una cuenta** ni entregar datos de identificación.
- **No usa analítica, publicidad ni rastreo** de ningún tipo, y no incluye SDKs de terceros.
- El desarrollador **no tiene acceso** a la información que registras en la App.

Si no activas la importación automática (SMS o Apple Pay), ningún dato sale de tu dispositivo. La ficha de privacidad del App Store refleja únicamente el tratamiento descrito en la sección 7: información financiera, un identificador de instalación y el historial de compras de la suscripción, todos **no vinculados a tu identidad** y usados solo para la funcionalidad de la App y para prevenir abusos.

## 3. Información que la App guarda localmente en tu dispositivo

Aunque no se recolecta información, la App almacena localmente, solo para su funcionamiento:

- **Datos financieros que tú registras:** movimientos (gastos, ingresos, ahorros), montos, categorías, notas, fechas, metas de ahorro, presupuestos por categoría, reglas de movimientos recurrentes y búsquedas recientes. Se guardan en una base de datos local cifrada por iOS con protección de datos completa (`NSFileProtectionComplete`).
- **Preferencias no sensibles:** tema, paleta de colores, idioma y ajustes del ritmo de gasto, guardadas en las preferencias locales de la App. Ningún dato financiero se guarda allí.
- **Configuración de bloqueo:** la preferencia de bloqueo biométrico se guarda en el Llavero (Keychain) del sistema, con accesibilidad restringida a este dispositivo y solo con el equipo desbloqueado.

## 4. Face ID / Touch ID

Si activas el bloqueo de la App, la autenticación la realiza iOS mediante el marco `LocalAuthentication`. La App **solo recibe el resultado (éxito o fallo)**: nunca accede a tus datos biométricos, que permanecen bajo el control exclusivo de Apple y del Secure Enclave de tu dispositivo.

## 5. Copias de seguridad

Si tienes activadas las copias de seguridad de tu dispositivo (iCloud o computador), la base de datos local de Pockit puede incluirse en ellas. Esas copias las gestiona Apple conforme a tu configuración y a la política de privacidad de Apple. Las claves guardadas por Pockit en el Llavero **no migran** a copias de seguridad ni a otros dispositivos.

## 6. Exportación de datos (CSV)

La App permite exportar tus movimientos a un archivo CSV. Esta acción **solo ocurre cuando tú la inicias** y tú decides dónde compartir o guardar el archivo. Una vez exportado, la protección de ese archivo queda bajo tu responsabilidad.

## 7. Importación automática de movimientos (funciones opcionales)

Pockit puede registrar movimientos por ti de dos maneras, ambas **desactivadas por defecto** y ambas basadas en automatizaciones de Atajos de Apple que tú mismo creas y controlas. Puedes tener una, las dos o ninguna activas.

### 7.1 Desde los SMS de tu banco

Pockit puede registrar movimientos automáticamente a partir de los SMS de tu banco, mediante una automatización de Atajos de Apple que tú mismo creas y controlas. Esta función está **desactivada por defecto** y solo opera si la enciendes en Ajustes.

- La App **no lee tus mensajes**: solo recibe el texto de los SMS que tu propia automatización de Atajos le envía (por ejemplo, los de tu banco).
- Con la función activa, ese texto —junto con los **nombres de tus categorías** (para poder clasificar el gasto en una de ellas)— se envía **cifrado (HTTPS)** a un servidor operado por el desarrollador, que lo procesa con un proveedor de inteligencia artificial (**Anthropic**) únicamente para extraer el monto, el comercio y la categoría del movimiento.
- El texto del SMS **no se almacena** en el servidor ni por el proveedor de IA (Anthropic no usa los datos de su API para entrenar modelos), y **no se vincula con tu identidad**: la App no envía tu nombre, número ni cuentas; solo el identificador aleatorio descrito en el punto 7.3.
- En tu dispositivo solo se guardan el monto, el comercio y la categoría resultantes, como cualquier otro movimiento que registres a mano.
- Si corriges la categoría de un movimiento importado, esa corrección se guarda **solo en tu dispositivo** para clasificar igual los próximos SMS de ese comercio; nunca se envía al servidor. Puedes consultarla y borrarla en Ajustes → Automatización → «Correcciones de categoría».
- Si no hay conexión al momento de recibir el SMS, la App guarda el texto **temporalmente en tu dispositivo, cifrado** (protección de datos completa de iOS), para reintentar procesarlo cuando vuelva la conexión (al abrir la App o al llegar otro SMS). Ese texto **se borra en cuanto se procesa** o se descarta, y nunca se envía sin conexión. Si tras varios días no se logra procesar, se elimina automáticamente.
- Puedes desactivar la función cuando quieras en Ajustes y eliminar la automatización desde la app Atajos.

### 7.2 Desde tus pagos con Apple Pay

Pockit puede registrar los pagos sin contacto que haces con Apple Pay, mediante la automatización de «Transacción» de Atajos. Esta función está **desactivada por defecto** y solo opera si la enciendes en Ajustes.

- La App **no accede a Wallet** ni a tu historial de transacciones, ni a los datos de tus tarjetas. Solo recibe el monto y el nombre del comercio que tu propia automatización de Atajos le entrega, y únicamente de los pagos sin contacto hechos con tu iPhone o Apple Watch.
- El **monto nunca sale de tu dispositivo**: lo entrega tu iPhone y se guarda tal cual.
- Para elegir la categoría del gasto se envía **cifrado (HTTPS)** únicamente el **nombre del comercio**, junto con los **nombres de tus categorías**, al mismo servidor descrito en el punto 7.1. Ese nombre no se almacena ni se vincula con tu identidad.
- Si ya corregiste antes la categoría de ese comercio, la clasificación ocurre **solo en tu dispositivo** y no se envía nada al servidor.
- Si no hay conexión (o el teléfono está bloqueado y la App todavía no puede abrir tus datos), el movimiento **se registra igual** con su monto correcto y queda por ahora en la categoría «Varios». La próxima vez que abras la App con conexión se envía el nombre del comercio para elegir la categoría, como se describe arriba. Si eso no ocurre en 14 días, el movimiento se queda en «Varios».
- Si un mismo cargo llega por las dos vías (el pago con Apple Pay y el SMS del banco), la App lo detecta y conserva **un solo movimiento**.
- Puedes desactivar la función cuando quieras en Ajustes y eliminar la automatización desde la app Atajos.

### 7.3 Plan gratuito, Pockit Pro y verificación de la App

Las funciones de los puntos 7.1 y 7.2 usan inteligencia artificial, que tiene un costo por uso. El plan gratuito incluye un número limitado de **registros automáticos al mes** (cada SMS leído y cada pago de Apple Pay categorizado cuenta uno); **Pockit Pro** no tiene ese límite. Registrar un pago de Apple Pay no cuenta: solo elegir su categoría. Para llevar esa cuenta y evitar abusos:

- Al instalarse, la App genera un **identificador aleatorio** que no está relacionado con tu nombre, tu número, tu Apple ID ni tus cuentas, y lo envía con cada solicitud de los puntos 7.1 y 7.2. El servidor guarda **solo** ese identificador, el mes y la cantidad de usos; ese conteo **se borra solo a los 70 días**. Para que reinstalar no reinicie la cuenta, el identificador se conserva en el llavero (Keychain) de tu iPhone aunque borres la App.
- Para comprobar que las solicitudes vienen de la App original y no de otro programa, la App usa **App Attest** de Apple: tu iPhone genera una clave y el servidor guarda únicamente su **clave pública**, sin datos tuyos.
- Si tienes Pockit Pro, la App envía la **constancia de compra firmada por Apple** (producto, fechas y el número de transacción de Apple) para verificar la suscripción. El servidor guarda ese número de transacción junto con los identificadores de las instalaciones que la usan (máximo 10), para evitar que una suscripción se comparta. **No recibe** tu nombre, correo ni medio de pago: eso lo maneja Apple.
- Si estás en el plan gratuito y ya usaste los registros automáticos del mes, el texto de los SMS que lleguen se guarda **en tu dispositivo, cifrado, sin enviarse**, hasta por **60 días**: si te suscribes a Pockit Pro se procesa entonces (con la fecha en que llegó); si no, se elimina.
- Ninguno de estos datos se usa para publicidad ni se comparte con terceros.

## 8. Permisos del sistema

Pockit solo solicita, de forma opcional, el permiso de **Face ID** para proteger el acceso a la App. No solicita acceso a ubicación, contactos, cámara, micrófono, fotos ni ningún otro dato del dispositivo. La App no tiene acceso a tus mensajes ni a Wallet: los SMS y los datos de tus pagos solo llegan a Pockit si tu automatización de Atajos se los envía.

## 9. Conservación y supresión

Tus datos permanecen en tu dispositivo hasta que tú los elimines. Puedes:

- Borrar movimientos, metas o categorías individualmente dentro de la App.
- Usar la opción **"Eliminar cuenta"** en Ajustes, que borra permanentemente todos los movimientos, presupuestos y metas guardados en el dispositivo.
- Desinstalar la App, lo que elimina su base de datos local.

El servidor no guarda tus movimientos. Solo conserva los datos técnicos del punto 7.3: el identificador aleatorio con su conteo mensual (que se borra solo a los 70 días), la clave pública de App Attest y, si eres Pro, el número de transacción de Apple. Puedes pedir su eliminación al correo de contacto.

## 10. Derechos de los titulares (habeas data)

Conforme a los artículos 8, 14 y 15 de la Ley 1581 de 2012, tienes derecho a conocer, actualizar, rectificar y suprimir tu información, y a revocar cualquier autorización. Por el diseño local de la App, **ejerces estos derechos directamente y sin intermediarios**, editando o borrando tu información dentro de Pockit.

Para consultas o reclamos relacionados con esta política puedes escribir a **feedbackpockit@gmail.com**. Las consultas se atenderán en un término máximo de diez (10) días hábiles y los reclamos en un término máximo de quince (15) días hábiles, contados desde su recibo, conforme a la ley. Si consideras vulnerados tus derechos, puedes acudir a la **Superintendencia de Industria y Comercio (SIC)** — [www.sic.gov.co](https://www.sic.gov.co) — una vez agotado el trámite de consulta o reclamo ante el responsable.

## 11. Menores de edad

Pockit no está dirigida a menores de edad y no recolecta datos de ninguna persona, incluidos menores. El tratamiento de datos de niños, niñas y adolescentes se sujeta a lo previsto en el artículo 7 de la Ley 1581 de 2012.

## 12. Cambios a esta política

Cualquier cambio se publicará en esta misma página y se reflejará en la fecha de "última actualización". Si un cambio implicara nuevas finalidades de tratamiento, se informará antes de su entrada en vigencia a través de la App o de la ficha del App Store.

## 13. Contacto

Juan Marulanda — feedbackpockit@gmail.com
