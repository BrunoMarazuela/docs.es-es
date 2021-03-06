---
title: "punto de conexión"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fe63370d-81a1-40f3-97c2-59cb357c78d2
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3bcb02ae01d66830d9bfd486c5ae3941c45c2a19
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="endpoint"></a>punto de conexión
punto de conexión  
  
## <a name="syntax"></a>Sintaxis  
  
```  
class Endpoint  
{  
  string Address;  
  string AddressHeaders[];  
  string AddressIdentity;  
  sint32 AppDomainId;  
  Behavior Behaviors[];  
  Binding Binding;  
  string ContractName;  
  string CounterInstanceName;  
  string ListenUri;  
  string Name;  
  sint32 ProcessId;  
  Contract ref;  
};  
```  
  
## <a name="methods"></a>Métodos  
 La clase Endpoint define el método siguiente.  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetOperationCounterInstanceName](../../../../../docs/framework/wcf/diagnostics/wmi/getoperationcounterinstancename.md)|Recupera el nombre de instancia del contador de rendimiento de la operación|  
  
## <a name="properties"></a>Propiedades  
 La clase Endpoint posee las siguientes propiedades:  
  
### <a name="address"></a>Dirección  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Un URI que contiene la dirección del extremo.  
  
### <a name="addressheaders"></a>AddressHeaders  
 Tipo de datos: matriz de cadenas  
  
 Tipo de acceso: solo lectura  
  
 La colección de encabezados de dirección adjunta a este extremo.  
  
### <a name="addressidentity"></a>AddressIdentity  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 La identidad del extremo.  
  
### <a name="appdomainid"></a>AppDomainId  
 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 El id. del appdomain que hospeda al extremo.  
  
### <a name="behaviors"></a>Controles de comportamiento  
 Tipo de datos: matriz de comportamientos  
  
 Tipo de acceso: solo lectura  
  
 Colección de comportamientos implementada por este extremo.  
  
### <a name="binding"></a>Enlaces  
 Tipo de datos: enlace  
  
 Tipo de acceso: solo lectura  
  
 El enlace utilizado por este extremo.  
  
### <a name="contractname"></a>ContractName  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Cadena que especifica qué contrato está exponiendo este extremo.  
  
### <a name="counterinstancename"></a>CounterInstanceName  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Nombre de la instancia del contador de rendimiento del extremo.  
  
### <a name="listenuri"></a>ListenUri  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 El URI en el que el extremo realiza escuchas.  
  
### <a name="name"></a>Name  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 El nombre único de este extremo.  
  
### <a name="processid"></a>ProcessId  
 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 El Id. del proceso que hospeda al extremo.  
  
### <a name="ref"></a>ref  
 Tipo de datos: Contrato  
  
 Tipo de acceso: solo lectura  
  
 El contrato que este extremo está exponiendo.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|
