---
title: '&lt;resolver&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0c00200c-f135-4e5c-a024-76b72bcbc021
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: db95b6f9a988c133a6b4afd55849fc6fb650c24c
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="ltresolvergt"></a>&lt;resolver&gt;
Especifica una resolución del mismo nivel que se utiliza para resolver un id. de malla del mismo nivel como un conjunto de direcciones del nodo del mismo nivel que representa varios nodos que participan en la malla.  
  
 \<system.ServiceModel>  
\<enlaces >  
\<netPeerBinding>  
\<binding>  
\<resolución >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<resolver mode="Auto/Custom/Pnrp"  
   referralPolicy="DoNotShare/Service/Share">  
</resolver>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`mode`|Una cadena que especifica si la instancia de la resolución del mismo nivel asociada con este servicio es específica del PNRP, una resolución personalizada o si se determina de manera automática. Este atributo es del tipo <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.|  
|`referralPolicy`|Una cadena que especifica la manera en que las referencias se comparten entre pares. Este atributo es del tipo <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<headers>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)|Especifica la configuración concreta para un servicio de resolución del mismo nivel personalizado.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<binding>](../../../../../docs/framework/misc/binding.md)|Define todas las funcionalidades de enlace de la [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).|  
  
## <a name="remarks"></a>Comentarios  
 Una resolución de nombres del mismo nivel es un servicio de descubrimiento utilizado por los canales del mismo nivel para buscar nodos del mismo nivel que participen en una malla del mismo nivel. También se utiliza para "registrar" un nodo con una malla del mismo nivel, el mecanismo por el que se conoce el nodo del mismo nivel y está disponible en la malla del mismo nivel. Para obtener más información sobre resoluciones del mismo nivel, consulte [resoluciones del mismo nivel](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.PeerResolver>  
 <xref:System.ServiceModel.PeerResolvers.PeerResolverSettings>  
 <xref:System.ServiceModel.NetPeerTcpBinding.Resolver%2A>  
 <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Resolver%2A>  
 <xref:System.ServiceModel.Configuration.PeerResolverElement>  
 [Resoluciones del mismo nivel](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)  
 [Agregar a un solucionador personalizado a una aplicación de PeerChannel](http://msdn.microsoft.com/library/12aa3787-2962-439c-ad27-46523c8b0419)
