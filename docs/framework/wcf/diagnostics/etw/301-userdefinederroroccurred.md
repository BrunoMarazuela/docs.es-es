---
title: 301 - UserDefinedErrorOccurred
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a0285d1c-550f-4c14-9c36-a96e97f1c4e4
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b24d54930a29a24dab97ce403c2808fb74b8cbfe
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="301---userdefinederroroccurred"></a>301 - UserDefinedErrorOccurred
## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|301|  
|Palabras clave|Solución de problemas, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring|  
|Nivel|Error|  
|Canal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descripción  
 Este evento se emite desde el código de usuario. Los desarrolladores pueden emitir este evento cuando se produce un error definido por el usuario en su servicio. Esto se puede llevar a cabo mediante las API de <xref:System.Diagnostics.Eventing>. Además, hay un ejemplo de WCF que ajusta esa API y muestra cómo emitir este evento correctamente.  
  
## <a name="message"></a>Mensaje  
 Nombre: '%1', referencia: '%2', carga:%3  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|nombre|`xs:string`|El nombre del evento definido por el usuario.|  
|HostReference|`xs:string`|En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web. El formato se define como ' ruta de acceso Virtual de sitio Web de nombre de aplicación &#124; Ruta de acceso Virtual del servicio &#124; ServiceName'. Ejemplo: ' sitio Web/CalculatorApplication &#124;/CalculatorService.svc &#124; predeterminada CalculatorService'.|  
|Payload|`xs:string`|La carga del evento definida por el usuario.|
