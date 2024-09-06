# Manual de Usuario: Documentación Web Service UBL 2.1 Facturatech - Anexo Técnico 1.9


## Menú

1. **[Introducción](#introducción)**
    - 1.1 Código de Respuesta del Servicio Web

2. **[Autenticación](#autenticación)**

3. **[Estructura WSDL](#estructura-wsdl)**

4. **Método de Consumo: FTECHACTION.UPLOADINVOICEFILE**
    - 4.1 Estructura de Respuesta
    - 4.2 Catálogo de Respuesta

5. **Método de Consumo: FTECHACTION.DOCUMENTSTATUSFILE**
    - 5.1 Estructura de Respuesta
    - 5.2 Catálogo de Respuesta

6. **Método de Consumo: FTECHACTION.DOWNLOADXMLFILE**
    - 6.1 Estructura de Respuesta
    - 6.2 Catálogo de Respuesta

7. **Método de Consumo: FTECHACTION.DOWNLOADPDFFILE**
    - 7.1 Estructura de Respuesta
    - 7.2 Catálogo de Respuesta

8. **Método de Consumo: FTECHACTION.DOWNLOADGETCUFEFILE**
    - 8.1 Estructura de Respuesta
    - 8.2 Catálogo de Respuesta

9. **Método de Consumo: FTECHACTION.DOWNLOADGETQRFILE**
    - 9.1 Estructura de Respuesta
    - 9.2 Catálogo de Respuesta

10. **Conclusiones**

## INTRODUCCIÓN
El presente manual tiene como objetivo detallar el funcionamiento del WSDL que brinda Facturatech como parte de la solución web service, para la integración de soluciones de facturación hacia softwares de terceros.
- **1.1 Código de respuesta del servicio web service**

  ![imagen manual de usuario 1](/public/images/manual_de_usuario/manualU_1.png)

## AUTENTICACIÓN
El proceso de autenticación utiliza las credenciales que constan del NIT y su contraseña Web Service, con estos dos elementos podemos acceder a la funcionalidad de los métodos, es importante señalar que esta información, no es la misma contraseña con la que ingresan al portal FACTURATECH, y es proporcionada por el departamento de Web Service a través de solicitud vía correo electrónico. En caso de no tener estos datos favor de contactar al equipo de soporte en la siguiente dirección de correo: soportews@facturatech.co

## ESTRUCTURA WSDL
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
