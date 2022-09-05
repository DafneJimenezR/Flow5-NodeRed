> # Flow5-NodeRed
Este repositorio contiene el Flow5 en Node-RED en el cual se muestran gráficos que obtienen información de OpenWeatherMap.

## Introducción
En este Flujo podrá apreciarse un conjunto de datos a través de gráficos en Dashboard, las cuales tienen como propósito reportar información climática recibida manualmente por MQTT, la información recibida automáticamente por API y la información de varios usuarios compartida por MQTT mediante un broker público.
## Material Necesario
Para realizar este flow necesitas lo siguiente:

-   [Ubuntu 20.04](https://releases.ubuntu.com/20.04/)
-   [NodeJS](https://nodejs.org/es/)
    -   [NPM](https://www.npmjs.com/)
    -   [NodeRed](https://nodered.org/docs/getting-started/local)
    -   [Nodos Dashboard](https://flows.nodered.org/node/node-red-dashboard)
-   [Mosquitto](https://mosquitto.org/)
## Material de Referencia
En los siguientes enlaces puedes encontrar cursos en la plataforma de edu.codigoiot.com que te permitirán realiar las configuraciones necesarias

-   [Instalación de Virutal Box y Ubuntu 20.04](https://edu.codigoiot.com/course/view.php?id=812)
-   [Instalación de NodeRed](https://edu.codigoiot.com/course/view.php?id=817)
-   [Introducción a NodeRed](https://edu.codigoiot.com/course/view.php?id=278)
-   [Introducción a Mosquitto](https://edu.codigoiot.com/course/view.php?id=851)
### Servicios
Para que el ejercicio sea ejecutado con éxito es necesario el uso de los siguientes servicios:

-   [HiveMQ](http://www.mqtt-dashboard.com/). Es un broker MQTT. Es una plataforma de mensajería para el movimiento de datos rápido, eficiente y confiable hacia y desde dispositivos IoT conectados y sistemas empresariales. (No se necesita crear una cuenta).
-   [OpenWeatherMap](https://openweathermap.org/). Es una de las opciones más populares para acceder a grandes volúmenes de datos meteorológicos gratuitos. El generoso plan gratuito de la API permite a los usuarios hasta 60 llamadas por minuto, incluido el acceso a datos meteorológicos actuales, pronósticos y mapas meteorológicos. (Se requiere una cuenta de usuario).

## Instrucciones

### Requisitos previos
Para que este flow funcione, debes cumplir con los siguientes requisitos previos.

1.  Instalación de NodeJS. Se recomienda tener instalado NodeJS en alguna versión LTS. Al momento de creación de este documento, se usó la versión 16.17.0LTS. Esta instalación debe incluir las Build-Tools para hacer uso de NPM
2.  Instalación de NodeRed. La instalación se realiza por NPM. Al momento de la creación de este contenido, se usó la versión 3.0.2
3.  Instalar los nodos node-red-dashboard. Para ello, dirígete a la opción "Manage Palet" de NodeRed y en la pestaña Install busca node-red-dashboard. Finalmente haz clic en instalar.
4.  Instalación de Broker local Mosquitto MQTT.
5.  Cuenta en OpenWeatherMap.org. Este es el servidor del cual se obtendrán los datos del clima por API
6.  API Key valida. Deberás generar una API Key con tu cuenta de openweathermaps.org


### Instrucciones de preparación del entorno

Para ejecutar este flow, es necesario lo siguiente:

1.  Arrancar NodeRed con el comando  `node-red`.
2.  Importar el flow del repositorio.
3.  Coloca tu API Key personal en la API Call del nodo HTTP Request.
4.  Actualiza la IP del broker público.
5.  Hacer clic en el botón Deploy.


### Instrucciones de operación

-   Para observar el resultado de este flow, abre un navegador y dirígete a localhost:1880/ui.
-   Para activar las gráficas de clima manual, debes enviar por MQTT un mensaje que contenga un JSON con las variables ID, temp y hum.
- 
### Notas

-   La sección manual de este flow se suscribe al tema codigoIoT/fow5/mqtt en un broker local.
-   El mensaje mqtt usado para probar este flow es  `mosquitto_pub -h localhost -t ccodigoIoT/fow5/mqtt -m '{"ID":"Dafne","temp":22,"hum":80}'`
-   Para que la gráfica histórica muestre información, deben enviarse al menos 2 puntos.
-   Para actualizar la IP del broker publico, se recomienda el siguiente comando  `nslookup broker.hivemq.com`. Puedes usar el broker publico de tu elección.
-   Para que múltiples graficas sean mostradas en la sección de Histórico Público, es necesario que múltiples usuarios se encuentren publicando a la vez.

- Comando para visualizar la información enviada por otros usuarios 
`mosquitto_sub -h 35.156.177.225 -t codigoIoT/flow5/mqtt/clima`

## Resultados

A continuación puedes ver los nodos del flow.
![enter image description here](https://github.com/DafneJimenezR/Flow5-NodeRed/blob/main/Flow5.png)

A continuación puede ver el tablero resultante.

![enter image description here](https://github.com/DafneJimenezR/Flow5-NodeRed/blob/main/Mqtt_api.png)

![enter image description here](https://github.com/DafneJimenezR/Flow5-NodeRed/blob/main/dashboard1.png)

![enter image description here](https://github.com/DafneJimenezR/Flow5-NodeRed/blob/main/HistoricoPublico.png)

![Gráfica que muestra el envio de datos simultaneo](https://github.com/DafneJimenezR/Flow5-NodeRed/blob/main/DatosUsuarios.png)

## Evidencias

-   [Repositorio](https://github.com/DafneJimenezR/Flow2-NodeRed)
- [Hugo Escalpelo](https://github.com/hugoescalpelo/)

## Créditos
- [Hugo Escalpelo](https://github.com/hugoescalpelo/)

