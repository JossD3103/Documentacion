# Manual de Usuario: Documentación Web Service UBL 2.1 Facturatech - Anexo Técnico 1.9


## Menú

1. **[Introducción](#1)**
    - [1.1 Código de Respuesta del Servicio Web](#1-1)

2. **[Autenticación](#2)**

3. **[Estructura WSDL](#3)**

4. **[Método de Consumo: FTECHACTION.UPLOADINVOICEFILE](#4)**
    - [4.1 Estructura de Respuesta](#4-1)
    - [4.2 Catálogo de Respuesta](#4-2)

5. **[Método de Consumo: FTECHACTION.DOCUMENTSTATUSFILE](#5)**
    - [5.1 Catálogo de Respuesta](#5-1)

6. **[Método de Consumo: FTECHACTION.DOWNLOADXMLFILE]()**
    - [6.1 Estructura de Respuesta](#6-1)
    - [6.2 Catálogo de Respuesta](#6-2)

7. **[Método de Consumo: FTECHACTION.DOWNLOADPDFFILE](#7)**
    - [7.1 Estructura de Respuesta](#7-1)
    - [7.2 Catálogo de Respuesta](#7-2)

8. **[Método de Consumo: FTECHACTION.DOWNLOADGETCUFEFILE](#8)**
    - [8.1 Estructura de Respuesta](#8-1)
    - [8.2 Catálogo de Respuesta](#8-2)

9. **[Método de Consumo: FTECHACTION.DOWNLOADGETQRFILE](#9)**
    - [9.1 Catálogo de Respuesta](#9-1)

10. **[Conclusiones](#10)**

## <a id="1"></a>1. INTRODUCCIÓN
El presente manual tiene como objetivo detallar el funcionamiento del WSDL que brinda Facturatech como parte de la solución web service, para la integración de soluciones de facturación hacia softwares de terceros.
### **<a id="1-1"></a>1.1 Código de respuesta del servicio web service**

  ![imagen manual de usuario 1](/public/images/manual_de_usuario/manualU_1.png)

## <a id="2"></a>2. AUTENTICACIÓN
El proceso de autenticación utiliza las credenciales que constan del NIT y su contraseña Web Service, con estos dos elementos podemos acceder a la funcionalidad de los métodos, es importante señalar que esta información, no es la misma contraseña con la que ingresan al portal FACTURATECH, y es proporcionada por el departamento de Web Service a través de solicitud vía correo electrónico. En caso de no tener estos datos favor de contactar al equipo de soporte en la siguiente dirección de correo: soportews@facturatech.co

## <a id="3"></a>3. ESTRUCTURA WSDL
Los WSDL de ambiente de habilitación de pruebas para los diferentes servicios, se encuentra disponible en los siguientes vínculos:

**Factura Electrónica** [https://ws.facturatech.co/v2/demo/index.php?wsdl](https://ws.facturatech.co/v2/demo/index.php?wsdl)

  ![imagen manual de usuario 2](/public/images/manual_de_usuario/manualU_2.png)

**Nomina Electrónica** [https://ws-nomina.facturatech.co/v1/demo/index.php?wsdl](https://ws-nomina.facturatech.co/v1/demo/index.php?wsdl)

  ![imagen manual de usuario 3](/public/images/manual_de_usuario/manualU_3.png)

**Documento Soporte Electrónico** [https://ws-dse.facturatech.co/v1/demo/?wsdl](https://ws-dse.facturatech.co/v1/demo/?wsdl)

  ![imagen manual de usuario 4](/public/images/manual_de_usuario/manualU_4.png)

**Factura Electrónica POS** [https://ws-pos.facturatech.co/v1/demo/index.php?wsdl](https://ws-pos.facturatech.co/v1/demo/index.php?wsdl)

  ![imagen manual de usuario 5](/public/images/manual_de_usuario/manualU_5.png)

Una vez finalizado el proceso de pruebas, los ambientes productivos están en los siguientes enlaces.

**Factura Electrónica** [https://ws.facturatech.co/v2/pro/index.php?wsdl](https://ws.facturatech.co/v2/pro/index.php?wsdl)  
**Nomina Electrónica** [https://ws-nomina.facturatech.co/v1/pro/index.php?wsdl](https://ws-nomina.facturatech.co/v1/pro/index.php?wsdl)  
**Documento Soporte Electrónico** [https://ws-dse.facturatech.co/v1/pro/?wsdl](https://ws-dse.facturatech.co/v1/pro/?wsdl)  
**Factura Electrónica POS** [https://ws-pos.facturatech.co/v1/pro/index.php?wsdl](https://ws-pos.facturatech.co/v1/pro/index.php?wsdl)

Se encuentran los siguientes códigos de respuesta en el servicio web service.

**Códigos 409, 405 y 404**  
Recurso no encontrado en servidor Conflicto de datos en servidor Creación de recurso satisfactorio en servidor Método no permitido en servidor

**Códigos 200 y 201**  
Solicitud transmitida con éxito.  
Al dar clic en el nombre de cada método, podemos obtener de manera detallada su estructura. En el detalle se visualiza el nombre de la acción, protocolo de comunicación, parámetros de entrada, parámetros de salida, y una breve descripción de la funcionalidad del método.

  ![imagen manual de usuario 6](/public/images/manual_de_usuario/manualU_6.png)

Adicional a esto existe una sección llamada WSDL donde se presenta la información detallada en formato XML, siguiendo el estándar WSDL, para publicar la información de cada uno de los métodos

  ![imagen manual de usuario 7](/public/images/manual_de_usuario/manualU_7.png)


## <a id="4"></a>4. METODO FTECHACTION.UPLOADINVOICEFILE

Este método define la funcionalidad para poder cargar su archivo XML y devolver un número de transacción, con este número de transacción podrá posteriormente consultar el estatus de este comprobante con la ayuda del método documentStatusFile, que se detallará más adelante.

Los parámetros que recibe este método son los siguientes: 

    a) Usuario de plataforma.
    b) Contraseña Web Service encriptada con SHA256.
    c) XML del comprobante convertido a base64.

  ![imagen manual de usuario 8](/public/images/manual_de_usuario/manualU_8.png)

La respuesta de este método depende de varias validaciones que se realizan de acuerdo con los parámetros enviados, un ejemplo de respuesta exitoso

  ![imagen manual de usuario 9](/public/images/manual_de_usuario/manualU_9.png)

### <a id="4-1"></a>4.1 RESPUESTA FTECHACTION.UPLOADINVOICEFILE

Tal como se presenta en el WSDL, el elemento uploadInvoiceFile, este metodo consta de la estructura que se presenta a continuación. De acuerdo con el procesamiento de la información, este metodo esta programado para devolver siempre dicha estructura. Por tanto, de manera puntual podemos determinar que una respuesta positiva siempre será devuelta en el índice de SUCCES con el código 200 o 201, según sea el caso. Adicional a estos parámetros el transaccionID que, es un código indispensable para poder buscar la trazabilidad del documento a ser firmado. Para una mayor comprensión y detalle en el capítulo 4.2 se presentan los códigos de respuesta que devuelve el web service.

  ![imagen manual de usuario 10](/public/images/manual_de_usuario/manualU_10.png)

### <a id="4-2"></a>4.2 CATÁLOGO DE RESPUESTA FTECHACTION.UPLOADINVOICEFILE

  ![imagen manual de usuario 11](/public/images/manual_de_usuario/manualU_11.png)

## <a id="5"></a>5. MÉTODO FTECHACTION.DOCUMENTSTATUSFILE

Este método devuelve el estatus en el que se encuentra el documento cargado, recibe como parámetros los siguientes datos:

    a) Usuario de plataforma
    b) Contraseña Web Service encriptada con SHA256
    c) IDTransacción devuelto por método uploadInvoiceFile 

  ![imagen manual de usuario 12](/public/images/manual_de_usuario/manualU_12.png)

Una vez procesada la información el Web Service nos debe presentar la respuesta con la confirmación de que el documento enviado ha sido procesado correctamente.

  ![imagen manual de usuario 13](/public/images/manual_de_usuario/manualU_13.png)

De acuerdo con el procesamiento de la información este método está programado para devolver siempre esta estructura. Por tanto, de manera puntual podemos determinar que una respuesta positiva siempre será devuelta como SUCCESS con el código 200 o 201, según sea el caso. Este una vez consumido tendremos los siguientes valores: SIGNED_XML [documento firmado correctamente] PROCESSING [documento aún en proceso de validación por la DIAN]

### <a id="5-1"></a>5.1 CATÁLOGO DE RESPUESTA FTECHACTION.DOCUMENTSTATUSFILE

  ![imagen manual de usuario 14](/public/images/manual_de_usuario/manualU_14.png)

## <a id="6"></a>6. MÉTODO FTECHACTION.DOWNLOADXMLFILE

Este método devuelve el XML en formato base64, recibe como parámetros los siguientes datos:

    a)	Usuario de plataforma
    b)	Contraseña Web Service encriptada con SHA256
    c)	Prefijo del documento firmado
    d)	Folio del documento firmado

  ![imagen manual de usuario 15](/public/images/manual_de_usuario/manualU_15.png)

### <a id="6-1"></a>6.1 Estructura de Respuesta

Una vez procesada la información el Web Service nos presenta la respuesta, con el adjunto del XML firmado, en la figura 9 se presenta el ejemplo de una respuesta positiva.

  ![imagen manual de usuario 16](/public/images/manual_de_usuario/manualU_16.png)

De acuerdo con el procesamiento de la información este método está programado para devolver
siempre esta estructura. Por tanto, de manera puntual podemos determinar que una respuesta positiva siempre será devuelta en el índice SUCCES con el código 201, según sea el caso y el nodo resourceData con la representación gráfica en formato base64. Para una mayor comprensión y detalle en el capítulo 6.2 se presentan los códigos de respuesta que devuelve el Web Service.

### <a id="6-2"></a>6.2 CATÁLOGOS DE RESPUESTA FTECHACTION.DOWNLOADXMLFILE

  ![imagen manual de usuario 17](/public/images/manual_de_usuario/manualU_17.png)

## <a id="7"></a>7. MÉTODO FTECHACTION.DOWNLOADPDFFILE

Este método devuelve la representación gráfica en formato PDF del documento firmado, recibe cómo parámetros los siguientes datos: 

    a) Usuario de plataforma 
    b) Contraseña Web Service encriptada con SHA256 
    c) Prefijo del documento firmado 
    d) Folio del documento firmado En la figura 10 se muestra cómo se realiza un consumo del método donwloadPDFFile.

  ![imagen manual de usuario 18](/public/images/manual_de_usuario/manualU_18.png)

### <a id="7-1"></a>7.1 Estructura de Respuesta

Una vez procesada la información el Web Service nos presenta la respuesta, con el adjunto de la representación gráfica del PDF en formato base64, en la figura 11 se presenta el ejemplo de una respuesta positiva.

  ![imagen manual de usuario 19](/public/images/manual_de_usuario/manualU_19.png)

### <a id="7-2"></a>7.2 CATÁLOGOS DE RESPUESTA FTECHACTION.DONWLOADPDFFILE

  ![imagen manual de usuario 20](/public/images/manual_de_usuario/manualU_20.png)

## <a id="8"></a>8. METODO FTECHACTION.GETCUFEFILE

Este método devuelve un string con el valor de CUFE del documento firmado, recibe cómo parámetros los siguientes datos:

    a)	Usuario de plataforma
    b)	Contraseña Web Service encriptada con SHA256
    c)	Prefijo del documento firmado
    d)	Folio del documento firmado

  ![imagen manual de usuario 21](/public/images/manual_de_usuario/manualU_21.png)

### <a id="8-1"></a>8.1 Estructura de Respuesta

De acuerdo al procesamiento de la información este método está programado para devolver siempre esta estructura. Por tanto, de manera puntual podemos determinar que una respuesta positiva siempre será devuelta en el índice success con el código 201, según sea el caso y el nodo resourceData con el valor del CUFE. Para una mayor comprensión y detalle en el capítulo 8.2 se presentan los códigos de respuesta que devuelve el Web Service.

  ![imagen manual de usuario 22](/public/images/manual_de_usuario/manualU_22.png)

### <a id="8-2"></a>8.2 CATÁLOGOS DE RESPUESTA FTECHACTION.GETCUFEFILE

  ![imagen manual de usuario 23](/public/images/manual_de_usuario/manualU_23.png)

## <a id="9"></a>9. METODO FTECHACTION.GETQRFILE

Este método devuelve los datos que componen el QR, que pertenece al documento firmado, recibe cómo parámetros los siguientes datos:

    a)	Usuario de plataforma
    b)	Contraseña Web Service encriptada con SHA256
    c)	Prefijo del documento firmado
    d)	Folio del documento firmado

  ![imagen manual de usuario 24](/public/images/manual_de_usuario/manualU_24.png)

Una vez procesada la información el Web Service nos presenta la respuesta, con los datos que componen el QR.

  ![imagen manual de usuario 25](/public/images/manual_de_usuario/manualU_25.png)

De acuerdo al procesamiento de la información este método está programado para devolver siempre esta estructura. Por tanto, de manera puntual podemos determinar que una respuesta positiva siempre será devuelta en el índice SUCCESS con el código 201, según sea el caso y el nodo resourceData con los datos que componen el QR. Para una mayor comprensión y detalle en el capítulo 9.1 se presentan los códigos de respuesta que devuelve el Web Service.

### <a id="9-1"></a>9.1 CATÁLOGO DE RESPUESTA FTECHACTION.GETQRFILE

  ![imagen manual de usuario 26](/public/images/manual_de_usuario/manualU_26.png)

## <a id="10"></a>10. CONCLUSIONES

La implementación de las funcionalidades del Web Service FACTURATECH sigue siendo optimizada de acuerdo a los últimos cambios que la DIAN libera de forma gradual. Por ello, ponemos a su disposición el siguiente correo, en donde con atención puntual y personalizada se dará seguimiento a cada uno de sus casos.


SOPORTE WEB SERVICE


CORREO ELECTRONICO: soportews@facturatech.co