---
title: Contratos
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF [WCF], contracts
- contracts [WCF]
- Windows Communication Foundation [WCF], contracts
ms.assetid: c8364183-4ac1-480b-804a-c5e6c59a5d7d
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9a45fc606ac962b4dc7aac8b49ed9a3c6c421ccd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="contracts"></a>Contratos
En esta sección se muestra cómo definir e implementar los contratos [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]. Un contrato de servicio especifica lo que un extremo comunica al mundo exterior. En un nivel más concreto, es una instrucción sobre un conjunto de mensajes concretos organizada en patrones de intercambio de mensajes básicos (MEP), como solicitud/respuesta, unidireccional y dúplex. Si un contrato de servicio es un conjunto relacionado de forma lógica de intercambios de mensajes, una operación de servicio es un intercambio único de mensajes. Por ejemplo, una operación `Hello` debe aceptar obviamente un mensaje (de manera que el autor de la llamada pueda anunciar el saludo) y puede o no devolver un mensaje (dependiendo de la cortesía de la operación).  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]contratos y otros principales [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] conceptos, vea [conceptos fundamentales de Windows Communication Foundation](../../../../docs/framework/wcf/fundamental-concepts.md). Este tema se centra en describir los contratos de servicio. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]los contratos de cómo los clientes que utilizan el servicio de compilación para conectarse a servicios, vea [información general sobre el cliente de WCF](../../../../docs/framework/wcf/wcf-client-overview.md). [!INCLUDE[crabout](../../../../includes/crabout-md.md)]los canales de cliente, la arquitectura de cliente y otros problemas del cliente, consulte [clientes](../../../../docs/framework/wcf/feature-details/clients.md).  
  
## <a name="overview"></a>Información general  
 En este tema se proporciona un nivel elevado de orientación conceptual para diseñar e implementar los servicios [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Los subtemas proporcionan más información detallada sobre las características del diseño e implementación. Antes de diseñar e implementar su aplicación [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], se recomienda lo siguiente:  
  
-   Entender lo que es un contrato de servicio, cómo funciona, y cómo crear uno.  
  
-   Comprenda que los contratos especifican requisitos mínimos que la configuración en tiempo de ejecución o el entorno de alojamiento pueden no admitir.  
  
## <a name="service-contracts"></a>Contratos de servicio  
 Un contrato de servicios es una instrucción que proporciona información sobre:  
  
-   La agrupación de operaciones en un servicio.  
  
-   La firma de las operaciones en términos de mensajes intercambiados.  
  
-   Los tipos de datos de estos mensajes.  
  
-   La ubicación de las operaciones.  
  
-   Los protocolos concretos y formatos de serialización que se utilizan para admitir la comunicación correcta con el servicio.  
  
 Por ejemplo, un contrato de orden de compra podría tener una operación `CreateOrder` que acepte una entrada de tipos de información de orden y devuelva información de error o completada, además de un identificador de orden. También podría tener una operación `GetOrderStatus` que acepte un identificador de orden y devuelva información de estado de la orden. Un contrato de servicio de este tipo especificaría lo siguiente:  
  
-   Que el contrato de la orden compra consistiese en las operaciones `CreateOrder` y `GetOrderStatus`.  
  
-   Que las operaciones han especificado mensajes de entrada y de salida.  
  
-   Los datos que estos mensajes pueden llevar.  
  
-   Instrucciones de categorías sobre la infraestructura de la comunicación necesaria para procesar correctamente los mensajes. Por ejemplo, estos detalles incluyen qué formularios de seguridad son necesarios para establecer una comunicación correcta.  
  
 Para transmitir este tipo de información a las aplicaciones en otras plataformas (plataformas no sean de Microsoft incluidas), los contratos de servicio XML públicamente se expresan en formatos XML estándar, como [lenguaje de descripción de servicios Web (WSDL)](http://go.microsoft.com/fwlink/?LinkId=87004) y [esquemas XML (XSD)](http://go.microsoft.com/fwlink/?LinkId=87005), entre otros. Los desarrolladores para muchas plataformas pueden utilizar esta información de contrato público para crear aplicaciones que pueden comunicarse con el servicio, porque entienden el lenguaje de la especificación y porque esos lenguajes están diseñados para permitir la interoperación describiendo los formularios, formatos y protocolos públicos que el servicio admite. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]cómo [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] identificadores de este tipo de información, consulte [metadatos](../../../../docs/framework/wcf/feature-details/metadata.md).  
  
 Los contratos se pueden expresar de muchas maneras, sin embargo, mientras WSDL y XSD son lenguajes excelentes para describir servicios de una manera accesible, son lenguajes difíciles de usar directamente. En cualquier caso, son simplemente descripciones de un servicio, no implementaciones de contratos de servicio. Por consiguiente, las aplicaciones [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utilizan atributos administrados, interfaces y clases para definir la estructura de un servicio e implementar un servicio.  
  
 El contrato resultante definido en tipos administrados se puede convertir (también denominado *exportar*) como metadatos, WSDL y XSD: cuando necesitan clientes u otros implementadores de servicio, sobre todo en otras plataformas. El resultado es un modelo de programación sencillo que se puede describir utilizando metadatos públicos en cualquier aplicación cliente. Los detalles de los mensajes SOAP subyacentes, como el transporte e información relacionada con la seguridad, etc., pueden dejarse en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], que realiza automáticamente las conversiones necesarias a y desde el sistema de tipos de contratos de servicio al sistema de tipos de XML.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Diseñar contratos, vea [diseñar contratos de servicio](../../../../docs/framework/wcf/designing-service-contracts.md). [!INCLUDE[crabout](../../../../includes/crabout-md.md)]implementación de contratos, consulte [implementar contratos de servicio](../../../../docs/framework/wcf/implementing-service-contracts.md).  
  
 Además, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] también proporciona la capacidad de desarrollar contratos de servicio completamente en el nivel de mensaje. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]desarrollar contratos de servicio en el nivel de mensaje, vea [usar contratos de mensaje](../../../../docs/framework/wcf/feature-details/using-message-contracts.md). [!INCLUDE[crabout](../../../../includes/crabout-md.md)]desarrollar servicios en XML no SOAP, vea [interoperabilidad con aplicaciones POX](../../../../docs/framework/wcf/feature-details/interoperability-with-pox-applications.md).  
  
### <a name="understanding-the-hierarchy-of-requirements"></a>Introducción a la jerarquía de los requisitos  
 Un contrato de servicio agrupa operaciones; especifica el MEP, tipos de mensaje y tipos de datos que llevan esos mensajes e indica categorías de comportamiento de tiempo de ejecución que una implementación debe tener para admitir el contrato (por ejemplo, puede requerir que los mensajes se cifren y firmen). El contrato de servicio en sí mismo, sin embargo, no especifica precisamente cómo se cumplen estos requisitos, solo que deben ser. Qué tipo de cifrado o cómo se firma un mensaje es tarea de la implementación y configuración de un servicio conforme.  
  
 Observe la manera en que el contrato requiere algunas cosas de la implementación del contrato de servicio y la configuración del tiempo de ejecución para agregar comportamiento. El conjunto de requisitos que se deben cumplir para exponer un servicio para usar compilaciones en el conjunto anterior de requisitos. Si un contrato realiza requisitos de la implementación, una implementación puede requerir todavía más de la configuración y enlaces que permiten al servicio ejecutarse. Finalmente, la aplicación host también debe admitir cualquier requisito que la configuración de servicio y los enlaces agreguen.  
  
 Este proceso de requisito aditivo es importante tenerlo presente mientras diseña, implementa, configura y aloja su aplicación de servicio [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]. Por ejemplo, el contrato puede especificar que necesita admitir una sesión. En ese caso, deberá configurar el enlace para admitir ese requisito contractual o la implementación del servicio no funcionará. O si su servicio requiere Autenticación integrada de Windows y se hospeda en Internet Information Services (IIS), la aplicación web en la que el servicio reside debe tener la Autenticación integrada de Windows activada y la compatibilidad anónima desactivada. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]las características y el impacto de los tipos de aplicación de host de servicio diferente, consulte [hospedaje](../../../../docs/framework/wcf/feature-details/hosting.md).  
  
## <a name="see-also"></a>Vea también  
 [Puntos de conexión: direcciones, enlaces y contratos](../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)  
 [Diseño de contratos de servicio](../../../../docs/framework/wcf/designing-service-contracts.md)  
 [Implementación de contratos de servicio](../../../../docs/framework/wcf/implementing-service-contracts.md)
