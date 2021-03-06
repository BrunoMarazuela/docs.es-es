---
title: '&lt;enlace&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 666183d6-4d1f-45c7-ac64-bdf93ee8f36f
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7b9e0c7e077a9f47de6df31b00f4df320b845150
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltbindinggt"></a>&lt;enlace&gt;
Puede utilizar el elemento de `binding` para configurar los tipos diferentes de enlaces predefinidos proporcionados por Windows Communication Foundation (WCF).  
  
## <a name="system-provided-binding"></a>Enlace proporcionado por el sistema  
 Los enlaces proporcionados por el sistema ocultan la complejidad de la pila de mensajería de WCF. Las aplicaciones que utilizan los enlaces proporcionados por el sistema no requieren el control completo sobre la pila. Los atributos expuestos en cada enlace proporcionado por el sistema son los más apropiados para el escenario de uso de las direcciones de enlace.  
  
 La sección de configuración para cada enlace proporcionado por el sistema puede definir varias configuraciones utilizadas para configurar el enlace. Un nombre único identifica a cada configuración.  
  
 No es posible agregar elementos o atributos a un enlace proporcionado por el sistema. Para esto, debería implementar un enlace personalizado como se describe en la sección "Enlace personalizado" de este tema. Es posible definir un enlace personalizado que imite perfectamente un enlace proporcionado por el sistema y agregue unos valores sobre los que la aplicación de usuario desee tener el control.  
  
## <a name="custom-binding"></a>Enlace personalizado  
 Los enlaces personalizados proporcionan el control completo sobre la pila de mensajería WCF. Un enlace individual define la pila de mensajes mediante la especificación de los elementos de configuración para los elementos de la pila en el orden que aparecen en la pila. Cada elemento define y configura un elemento de la pila. Debe haber un único elemento de `transport` en cada enlace personalizado. Sin este elemento, la pila de la mensajería está incompleta.  
  
 El orden de aparición de los elementos en la pila es importante, porque es el orden en el que las operaciones se aplican al mensaje. El orden recomendado de elementos de pila es el siguiente:  
  
1.  Transacciones (opcional)  
  
2.  Mensajería de confianza (opcional)  
  
3.  Seguridad (opcional)  
  
4.  Codificador  
  
5.  Transporte  
  
 Los enlaces personalizados se identifican mediante su atributo `name`.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Configuration.BindingsSection>  
 <xref:System.ServiceModel.Channels.Binding>  
 <xref:System.ServiceModel.Channels.BindingElement>  
 [Enlaces](../../../docs/framework/wcf/bindings.md)  
 [Enlaces personalizados](../../../docs/framework/wcf/extending/custom-bindings.md)  
 [\<customBinding >](../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
