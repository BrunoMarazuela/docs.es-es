---
title: TcpConnectionPoolSettings
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 19acfba3-c057-4dbc-bac7-8674d7844d83
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 04e6a457a9f4c3f93a52f851aafe70578b7d7444
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="tcpconnectionpoolsettings"></a>TcpConnectionPoolSettings
TcpConnectionPoolSettings  
  
## <a name="syntax"></a>Sintaxis  
  
```  
class TcpConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## <a name="methods"></a>Métodos  
 La clase TcpConnectionPoolSettings no define ningún método.  
  
## <a name="properties"></a>Propiedades  
 La clase TcpConnectionPoolSettings tiene las siguientes propiedades:  
  
### <a name="groupname"></a>GroupName  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 El nombre del grupo de conexiones utilizado por el elemento de enlace.  
  
### <a name="idletimeout"></a>IdleTimeout  
 Tipo de datos: datetime  
  
 Tipo de acceso: solo lectura  
  
 El tiempo máximo que la conexión puede estar inactiva antes de desconectarse.  
  
### <a name="leasetimeout"></a>LeaseTimeout  
 Tipo de datos: datetime  
  
 Tipo de acceso: solo lectura  
  
 El tiempo máximo para que la operación de concesión se complete antes de que se agote el tiempo de espera.  
  
### <a name="maxoutboundconnectionsperendpoint"></a>MaxOutboundConnectionsPerEndpoint  
 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 Las conexiones máximas salientes para cada extremo.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings>
