---
title: HttpListener
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- HTTP
ms.assetid: 5b89d3fb-3c9a-49e2-af1f-c34c020c68ac
caps.latest.revision: 
author: mcleblanc
ms.author: markl
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: b4b8c1e916aa9382d156a197fa15c2e72e900a1c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="httplistener"></a>HttpListener
La clase <xref:System.Net.HttpListener> proporciona un agente de escucha del protocolo HTTP controlado mediante programación. El agente de escucha está activo durante la vigencia del objeto <xref:System.Net.HttpListener> y se ejecuta dentro de la aplicación.  
  
## <a name="httpsys"></a>HTTP.SYS  
 La clase <xref:System.Net.HttpListener> se basa en HTTP.sys, que es el agente de escucha de modo kernel que controla todo el tráfico HTTP de Windows. HTTP.sys proporciona administración de conexiones, limitación del ancho de banda y registro del servidor web. Utilice la herramienta `HttpCfg.exe` para agregar certificados SSL. Para obtener más información, vea la documentación en la herramienta [HttpCfg.exe](http://go.microsoft.com/fwlink/?LinkID=178284) en la documentación de [Servidor](http://go.microsoft.com/fwlink/?LinkID=178285).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Net.HttpListener>  
 <xref:System.Net.HttpWebRequest>  
 <xref:System.Net.HttpWebResponse>  
 [Servidor HTTP](http://go.microsoft.com/fwlink/?LinkID=178285)  
 [Mejoras de seguridad en Internet Information](http://go.microsoft.com/fwlink/?LinkID=178286)  
 [Ejemplo de la aplicación host HttpListener de ASPX](http://go.microsoft.com/fwlink/?LinkID=179560)  
 [Ejemplo de tecnología HttpListener](http://go.microsoft.com/fwlink/?LinkID=179558)  
 [Network Programming Samples (Ejemplos de programación de red)](../../../docs/framework/network-programming/network-programming-samples.md)
