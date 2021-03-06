---
title: Perfil seguro confiable
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 921edc41-e91b-40f9-bde9-b6148b633e61
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 89a6d5c2e485699a55c77797c34eaca2c9848c40
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="reliable-secure-profile"></a>Perfil seguro confiable
En este ejemplo se muestra cómo crear [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] y [perfil de protección confiable](http://go.microsoft.com/fwlink/?LinkId=178140) (RSP). Este ejemplo muestra la implementación de un [establecer conexión](http://go.microsoft.com/fwlink/?LinkId=178141) canal que se puede formular junto con la mensajería de confianza y, opcionalmente, un canal seguro para crear un enlace seguro confiable basado en la especificación de RSP.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\ReliableSecureProfile`  
  
## <a name="discussion"></a>Explicación  
 En este ejemplo se muestra un escenario de intercambio de mensajes bidireccional asincrónico confiable. El servicio tiene un contrato dúplex y el cliente implementa el contrato de devolución de llamadas dúplex. El cliente inicia una solicitud a un servicio, para el que se espera una respuesta en una conexión independiente. El mensaje de solicitud se envía de forma confiable. El cliente no desea abrir un extremo para realizar escuchas hasta el fin. Por tanto, sondea el servicio con solicitudes de 'Establecer conexión' para el servicio de modo que la respuesta se devuelva en el canal secundario de esta solicitud de 'Establecer conexión'. En este ejemplo se muestra cómo conseguir una comunicación dúplex, confiable y segura a través de HTTP sin que el cliente exponga un punto de conexión para realizar escuchas (y cree una excepción de firewall).  
  
## <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1.  Abra la **ReliableSecureProfile** solución.  
  
2.  Haga clic con el **servicio** proyecto **el Explorador de soluciones**, seleccione **depurar**, **Iniciar nueva instancia** en el menú contextual. De esta forma se inicia el host de servicio.  
  
3.  Haga clic con el **cliente** proyecto **el Explorador de soluciones**, seleccione **depurar**, **Iniciar nueva instancia** en el menú contextual. De esta forma se inicia el cliente.  
  
4.  Escriba una cadena en el símbolo del sistema de la ventana de la consola del cliente y haga clic en ENTRAR. De este modo se envía la cadena de entrada al servicio, que calcula un valor hash de la misma.  
  
5.  Vea el resultado en las ventanas de cliente cuando el servicio llama de nuevo a la operación de contrato de devolución de llamada dúplex para mostrar el resultado en la ventana de la consola del cliente. Hay un retraso intencionado en el servicio para simular una operación que tarda en ejecutarse y procesa los datos.  
  
6.  Al supervisar el tráfico HTTP (mediante alguna de las herramientas de supervisión de red en línea, como Monitor de red, Fiddler, etc.), se muestra que se establece una secuencia para la comunicación entre el cliente y el servicio que el Perfil de protección confiable rechaza, y cómo sondea el cliente dicho servicio con las solicitudes 'Establecer conexión'. Cuando el servicio está preparado para devolver la respuesta procesada, utiliza el canal secundario de la última solicitud 'Establecer conexión' para enviar de vuelta los resultados.  
  
7.  Presione ENTRAR en la ventana de la consola del servicio para cerrar el servicio. Presione ENTRAR en la ventana de la consola de cliente para cerrar el cliente.
