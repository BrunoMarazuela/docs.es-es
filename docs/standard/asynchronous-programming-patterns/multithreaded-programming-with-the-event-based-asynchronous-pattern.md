---
title: "Programación multiproceso con el modelo asincrónico basado en eventos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- components [.NET Framework], asynchronous
- AsyncOperation class
- AsyncCompletedEventArgs class
ms.assetid: 958d6617-5e70-4b36-b5db-63c16dc35e43
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 557d639cc8a4e7ade2cfbd1f5d7264bca226d273
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="multithreaded-programming-with-the-event-based-asynchronous-pattern"></a>Programación multiproceso con el modelo asincrónico basado en eventos
Hay varias maneras de exponer las características asincrónicas al código de cliente. El modelo asincrónico basado en eventos prescribe la manera recomendada para que las clases presenten comportamiento asincrónico.  
  
## <a name="in-this-section"></a>En esta sección  
 [Información general sobre el modelo asincrónico basado en eventos](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 Describe cómo el Modelo asincrónico basado en evento pone a su disposición las ventajas de las aplicaciones multithreading ocultando muchos de los problemas complejos inherentes al diseño multithreading.  
  
 [Implementación del modelo asincrónico basado en eventos](../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md)  
 Describe la manera estándar de empaquetar una clase que tiene características asincrónicas.  
  
 [Procedimientos recomendados para implementar el modelo asincrónico basado en eventos](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md)  
 Describe los requisitos para exponer las características asincrónicas según el Modelo asincrónico basado en evento.  
  
 [Decisión de cuándo implementar el modelo asincrónico basado en eventos](../../../docs/standard/asynchronous-programming-patterns/deciding-when-to-implement-the-event-based-asynchronous-pattern.md)  
 Describe cómo determinar cuándo se debería decidir implementar el Modelo asincrónico basado en evento en lugar del modelo <xref:System.IAsyncResult>.  
  
 [Tutorial: Implementación de un componente que admita el modelo asincrónico basado en eventos](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)  
 Explica cómo crear un componente que implementa el Modelo asincrónico basado en evento. Se implementa utilizando las clases auxiliares del espacio de nombres <xref:System.ComponentModel?displayProperty=nameWithType>, que garantiza que el componente funciona correctamente bajo cualquier modelo de aplicación.  
  
 [Uso de componentes que admitan el modelo asincrónico basado en eventos](../../../docs/standard/asynchronous-programming-patterns/how-to-use-components-that-support-the-event-based-asynchronous-pattern.md)  
 Describe cómo utilizar un componente que admite el Modelo asincrónico basado en evento.  
  
## <a name="reference"></a>Referencia  
 <xref:System.ComponentModel.AsyncOperation>  
 Describe la clase <xref:System.ComponentModel.AsyncOperation> y contiene vínculos a todos sus miembros.  
  
 <xref:System.ComponentModel.AsyncOperationManager>  
 Describe la clase <xref:System.ComponentModel.AsyncOperationManager> y contiene vínculos a todos sus miembros.  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 Describe el componente <xref:System.ComponentModel.BackgroundWorker> y contiene vínculos a todos sus miembros.  
  
## <a name="see-also"></a>Vea también  
 [Procedimientos recomendados para el subprocesamiento administrado](../../../docs/standard/threading/managed-threading-best-practices.md)  
 [Eventos](../../../docs/standard/events/index.md)  
 [Subprocesamiento múltiple en componentes](http://msdn.microsoft.com/library/2fc31e68-fb71-4544-b654-0ce720478779)  
 [Modelo asincrónico basado en eventos (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)
