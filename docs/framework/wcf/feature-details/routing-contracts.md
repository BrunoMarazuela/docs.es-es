---
title: Enrutar contratos
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9ceea7ae-ea19-4cf9-ba4f-d071e236546d
caps.latest.revision: "7"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1c026c57129672eb25bb244a4fc928b827398e08
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="routing-contracts"></a>Enrutar contratos
Los contratos de enrutamiento definen los patrones de mensaje que puede procesar el servicio de enrutamiento.  Todos los contratos son sin tipos y permiten al servicio recibir un mensaje sin conocimiento de la acción o del esquema del mensaje. Esto permite al servicio de enrutamiento enrutar mensajes genéricamente sin configuración adicional para las características de los mensajes subyacentes que se enrutan.  
  
## <a name="routing-contracts"></a>Enrutar contratos  
 Como el servicio de enrutamiento acepta un objeto de mensaje de WCF genérico, el aspecto más importante que se debe tener en cuenta al seleccionar un contrato es la forma del canal que se usará al comunicarse con los clientes y los servicios. Al procesar mensajes, el servicio de enrutamiento usa suministros de mensajes simétricos, así que, normalmente, la forma del contrato entrante debe coincidir con la forma del contrato saliente. Sin embargo, hay casos en el distribuidor del modelo de servicio puede modificar las formas, como cuando el distribuidor convierte un canal dúplex en un canal de solicitud y respuesta, o quita la compatibilidad de la sesión de un canal cuando no es necesario y no se está utilizando (es decir Cuando **SessionMode.Allowed**, convirtiendo un **IInputSessionChannel** en un **IInputChannel**).  
  
 Para admitir estos suministros de mensajes, el servicio de enrutamiento proporciona contratos en el espacio de nombres <xref:System.ServiceModel.Routing>, que se deben usar al definir los extremos de servicio empleados por el servicio de enrutamiento. Estos contratos son sin tipo, lo que permite recibir cualquier acción o tipo de mensaje, y permite al servicio de enrutamiento administrar mensajes sin conocer el esquema del mensaje concreto. Para obtener más información acerca de los contratos usados por el servicio de enrutamiento, consulte [contratos de enrutamiento](../../../../docs/framework/wcf/feature-details/routing-contracts.md).  
  
 Los contratos proporcionados por el servicio de enrutamiento se encuentran en el espacio de nombres <xref:System.ServiceModel.Routing> y se describen en la siguiente tabla.  
  
|Contrato|Forma|Forma del canal|  
|--------------|-----------|-------------------|  
|<xref:System.ServiceModel.Routing.ISimplexDatagramRouter>|SessionMode = SessionMode.Allowed<br /><br /> AsyncPattern = true<br /><br /> IsOneWay = true|IInputChannel -> IOutputChannel|  
|<xref:System.ServiceModel.Routing.ISimplexSessionRouter>|SessionMode = SessionMode.Required<br /><br /> AsyncPattern = true<br /><br /> IsOneWay = true|IInputSessionChannel -> IOutputSessionChannel|  
|<xref:System.ServiceModel.Routing.IRequestReplyRouter>|SessionMode = SessionMode.Allowed<br /><br /> AsyncPattern = true|IReplyChannel -> IRequestChannel|  
|<xref:System.ServiceModel.Routing.IDuplexSessionRouter>|SessionMode=SessionMode.Required<br /><br /> CallbackContract=typeof(ISimplexSession)<br /><br /> AsyncPattern = true<br /><br /> IsOneWay = true<br /><br /> TransactionFlow(TransactionFlowOption.Allowed)|IDuplexSessionChannel -> IDuplexSessionChannel|  
  
## <a name="see-also"></a>Vea también  
 [Servicio de enrutamiento](http://msdn.microsoft.com/library/5ac8718c-bcef-456f-bfd5-1e60a30d6eaa)  
 [Introducción al enrutamiento](../../../../docs/framework/wcf/feature-details/routing-introduction.md)
