---
title: "Opciones de hospedaje de flujo de trabajo | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 37bcd668-9c5c-4e7c-81da-a1f1b3a16514
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Opciones de hospedaje de flujo de trabajo
La mayoría de los ejemplos de [!INCLUDE[wf](../../../includes/wf-md.md)] usa los flujos de trabajo hospedados en una aplicación de consola, pero no es un escenario realista para los flujos de trabajo reales.Los flujos de trabajo de aplicaciones empresariales reales se hospedarán en procesos persistentes: un servicio de Windows creado por el desarrollador o una aplicación de servidor como [!INCLUDE[iisver](../../../includes/iisver-md.md)] o AppFabric.Las diferencias entre estas aproximaciones son las que se indican a continuación.  
  
## Hospedar flujos de trabajo en IIS con Windows AppFabric  
 Usar IIS con AppFabric es el host preferido para los flujos de trabajo.Windows Activation Service, que quita la dependencia de HTTP a través de IIS solamente, es la aplicación de host para flujos de trabajo que usan AppFabric.  
  
## Hospedar flujos de trabajo solo en IIS  
 No se recomienda usar [!INCLUDE[iisver](../../../includes/iisver-md.md)] solamente, ya que hay herramientas de administración y de supervisión disponibles en AppFabric que facilitan el mantenimiento de las aplicaciones en ejecución.Los flujos de trabajo solo se deben hospedar en [!INCLUDE[iisver](../../../includes/iisver-md.md)] si hay problemas de infraestructura al cambiar a AppFabric.  
  
> [!WARNING]
>  [!INCLUDE[iisver](../../../includes/iisver-md.md)] recicla grupos de aplicaciones periódicamente por varios motivos.Cuando se recicla un grupo de aplicaciones, IIS deja de aceptar mensajes en el grupo anterior y crea instancias en un grupo de aplicaciones nuevo para aceptar las nuevas solicitudes.Si un flujo de trabajo sigue funcionando después de enviar una respuesta, [!INCLUDE[iisver](../../../includes/iisver-md.md)] no tendrá constancia del trabajo que se está haciendo y puede que recicle los grupos de aplicaciones de hospedaje.Si esto sucede, el flujo de trabajo se anulará y los servicios de seguimiento registrarán un mensaje [1004 \- WorkflowInstanceAborted](../../../docs/framework/windows-workflow-foundation//1004-workflowinstanceaborted.md) con un campo Motivo vacío.  
>   
>  Si se usa la persistencia, el host debe reiniciar explícitamente las instancias anuladas desde el último punto de persistencia.  
>   
>  Si se usa AppFabric, el servicio de administración de flujo de trabajo reanudará finalmente el flujo de trabajo desde el último punto de persistencia correcto si se usa la persistencia.Si no se usa ninguna persistencia, y el flujo de trabajo realiza operaciones fuera de un modelo de solicitud y respuesta, los datos se perderán cuando se anule el flujo de trabajo.  
  
## Hospedar un flujo de trabajo en un servicio de Windows personalizado  
 Crear un servicio de flujo de trabajo personalizado para hospedar el flujo de trabajo requerirá que el desarrollador duplique muchas de las funcionalidades que AppFabric ha proporcionado de serie, pero permitirá más flexibilidad con las funcionalidades personalizadas.Esta opción solo debe tenerse en cuenta si no es posible AppFabric.