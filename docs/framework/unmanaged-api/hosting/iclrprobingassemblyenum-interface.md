---
title: ICLRProbingAssemblyEnum (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRProbingAssemblyEnum
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRProbingAssemblyEnum
helpviewer_keywords: ICLRProbingAssemblyEnum interface [.NET Framework hosting]
ms.assetid: e7d3ccab-b0f0-4872-8935-0ed72920171b
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6d810ab6e62c6df1b00305947de552ecdbe82141
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="iclrprobingassemblyenum-interface"></a><span data-ttu-id="cefc8-102">ICLRProbingAssemblyEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cefc8-102">ICLRProbingAssemblyEnum Interface</span></span>
<span data-ttu-id="cefc8-103">Proporciona métodos que permiten al host obtener las identidades de sondeo de un ensamblado mediante el uso de información de identidad del ensamblado que es interno de common language runtime (CLR), sin necesidad de crear o reconocer dicha identidad.</span><span class="sxs-lookup"><span data-stu-id="cefc8-103">Provides methods that enable the host to get the probing identities of an assembly by using the assembly's identity information that is internal to the common language runtime (CLR), without needing to create or understand that identity.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cefc8-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="cefc8-104">Methods</span></span>  
  
|<span data-ttu-id="cefc8-105">Método</span><span class="sxs-lookup"><span data-stu-id="cefc8-105">Method</span></span>|<span data-ttu-id="cefc8-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="cefc8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cefc8-107">Get (método)</span><span class="sxs-lookup"><span data-stu-id="cefc8-107">Get Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-get-method.md)|<span data-ttu-id="cefc8-108">Obtiene la identidad del ensamblado en el índice especificado.</span><span class="sxs-lookup"><span data-stu-id="cefc8-108">Gets the assembly identity at the specified index.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cefc8-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cefc8-109">Remarks</span></span>  
 <span data-ttu-id="cefc8-110">Métodos como [ICLRAssemblyIdentityManager:: GetProbingAssembliesFromReference](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) devolver un `ICLRProbingAssemblyEnum` instancia.</span><span class="sxs-lookup"><span data-stu-id="cefc8-110">Methods such as [ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) return an `ICLRProbingAssemblyEnum` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cefc8-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cefc8-111">Requirements</span></span>  
 <span data-ttu-id="cefc8-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cefc8-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cefc8-113">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="cefc8-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cefc8-114">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cefc8-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cefc8-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cefc8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cefc8-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="cefc8-116">See Also</span></span>  
 [<span data-ttu-id="cefc8-117">ICLRAssemblyIdentityManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cefc8-117">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="cefc8-118">ICLRAssemblyReferenceList (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cefc8-118">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="cefc8-119">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="cefc8-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)