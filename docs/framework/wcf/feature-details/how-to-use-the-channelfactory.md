---
title: "Cómo utilizar ChannelFactory"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: d48f01b5-582b-4c8b-b547-8adddae7e371
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 644160f11bd743a0c1d598cc01b3e365adea5c56
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-the-channelfactory"></a>Cómo utilizar ChannelFactory
La clase <xref:System.ServiceModel.ChannelFactory%601> genérica se usa en escenarios avanzados que requieren la creación de un generador de canal que se puede utilizar para crear más de un canal.  
  
### <a name="to-create-and-use-the-channelfactory-class"></a>Crear y utilizar la clase ChannelFactory  
  
1.  Compile y ejecute un servicio [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Diseñar e implementar servicios](../../../../docs/framework/wcf/designing-and-implementing-services.md), [configuración de servicios](../../../../docs/framework/wcf/configuring-services.md), y [servicios de hospedaje](../../../../docs/framework/wcf/hosting-services.md).  
  
2.  Use la [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) para generar el contrato (interfaz) para el cliente.  
  
3.  En el código de cliente, utilice la clase <xref:System.ServiceModel.ChannelFactory%601> para crear varios agentes de escucha de extremo.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[c_HowToUseChannelFactory#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtousechannelfactory/cs/source.cs#1)]
 [!code-vb[c_HowToUseChannelFactory#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtousechannelfactory/vb/source.vb#1)]
