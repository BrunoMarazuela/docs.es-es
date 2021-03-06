---
title: "Controlar inicio automático del host de servicio de WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- WcfOptions
ms.assetid: 6abe5d34-519b-4cef-8f02-3c0a7f125585
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 65daceac9b865f3e8224c709d672344606905d9f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="controlling-auto-launching-of-wcf-service-host"></a>Controlar inicio automático del host de servicio de WCF
Puede controlar la capacidad de inicio automático del host de servicio de [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] (WcfSvcHost.exe) para un proyecto de biblioteca de servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] al depurar otro proyecto de la misma solución de [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] que contiene varios proyectos.  
  
 Para ello, haga clic en el [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] proyecto de servicio en **el Explorador de soluciones**, elija **propiedades**y haga clic en **opciones de WCF** ficha. El **iniciar cuando se depure otro proyecto en la misma solución el Host de servicio de WCF** casilla de verificación está habilitada de forma predeterminada. Puede desactivarla para que no se inicie el host de servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] para este proyecto concreto cuando se depure otro proyecto en la misma solución.  
  
 Este comportamiento no afecta a la depuración de F5 o a las funcionalidades de Agregar referencia de servicio para este proyecto.  
  
 Esta opción está disponible para los proyectos siguientes:  
  
-   Proyecto de biblioteca de servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
-   Proyecto de biblioteca de servicio de flujo de trabajo secuencial.  
  
-   Proyecto de biblioteca de servicio de flujo de trabajo de equipo de estado.  
  
-   Proyecto de biblioteca de servicio de distribución.  
  
## <a name="see-also"></a>Vea también  
 [Host de servicio WCF (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)
