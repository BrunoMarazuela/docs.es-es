---
title: "Correlación basada en contenidos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8638b5d6-1d59-456d-8acd-179a5b39b260
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5971636df3393adda96dff779c1533969f67bf57
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="content-based-correlation"></a>Correlación basada en contenidos
En este ejemplo se muestra cómo las actividades de mensajería (<xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.SendReply> y <xref:System.ServiceModel.Activities.ReceiveReply>) se pueden utilizar con varias correlaciones basadas en contenido y con una correlación basada en contenido. En este escenario, en primer lugar se inicializa una correlación en función de un identificador de pedido de compra y, a continuación, se crea otra correlación basada en el identificador del cliente. Así se muestra cómo una actividad <xref:System.ServiceModel.Activities.Receive> puede seguir una correlación existente e inicializar una nueva correlación basada en el mismo mensaje de entrada.  
  
## <a name="demonstrates"></a>Demostraciones  
 Actividades de mensajería y correlación basada en contenido  
  
## <a name="discussion"></a>Explicación  
 En este ejemplo se muestra cómo utilizar varias correlaciones basadas en contenido.  En este escenario, en primer lugar se inicializa una correlación en función de un identificador de pedido de compra y, a continuación, se crea otra correlación basada en el identificador del cliente.  Las correlaciones se colocan en cascada utilizando una actividad <xref:System.ServiceModel.Activities.Receive> que sigue una correlación existente (PurchaseOrderId) e inicializa una nueva correlación (CustomerId) en función del mismo mensaje de entrada.  Para ello, la actividad <xref:System.ServiceModel.Activities.Receive> utiliza las propiedades <xref:System.ServiceModel.Activities.Receive.CorrelatesOn%2A>, <xref:System.ServiceModel.Activities.Receive.CorrelatesWith%2A> y <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A>.  
  
## <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
  
1.  Abra [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] con permisos elevados, haciendo clic en el [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] icono y seleccione **ejecutar como administrador**.  
  
2.  Con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], abra el archivo de solución CascadingCorrelation.sln.  
  
3.  Para compilar la solución, presione Ctrl+MAYÚS+B.  
  
4.  Presione F5 para ejecutar el servidor.  
  
5.  Cuando el servicio está listo y realizando escuchas para los mensajes, en el Explorador de soluciones, haga clic con el botón secundario en el proyecto Cliente y ejecútelo.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\ContentBasedCorrelation`