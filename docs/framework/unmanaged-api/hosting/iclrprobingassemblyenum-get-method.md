---
title: "ICLRProbingAssemblyEnum::Get (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRProbingAssemblyEnum.Get
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRProbingAssemblyEnum::Get
helpviewer_keywords:
- Get method, ICLRProbingAssemblyEnum interface [.NET Framework hosting]
- ICLRProbingAssemblyEnum::Get method [.NET Framework hosting]
ms.assetid: fdb67a77-782f-44cf-a8a1-b75999b0f3c8
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cdd198f7a7a35fe4df371f3a53964b94459fd314
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="iclrprobingassemblyenumget-method"></a><span data-ttu-id="4b56f-102">ICLRProbingAssemblyEnum::Get (Método)</span><span class="sxs-lookup"><span data-stu-id="4b56f-102">ICLRProbingAssemblyEnum::Get Method</span></span>
<span data-ttu-id="4b56f-103">Obtiene la identidad del ensamblado en el índice especificado.</span><span class="sxs-lookup"><span data-stu-id="4b56f-103">Gets the assembly identity at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b56f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4b56f-104">Syntax</span></span>  
  
```  
HRESULT Get (  
    [in] DWORD dwIndex,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4b56f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4b56f-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="4b56f-106">[in] Índice de base cero de la identidad del ensamblado para devolver.</span><span class="sxs-lookup"><span data-stu-id="4b56f-106">[in] The zero-based index of the assembly identity to return.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="4b56f-107">[out] Un búfer que contiene los datos de identidad de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="4b56f-107">[out] A buffer containing the assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="4b56f-108">[entrada, salida] El tamaño de la `pwzBuffer` búfer.</span><span class="sxs-lookup"><span data-stu-id="4b56f-108">[in, out] The size of the `pwzBuffer` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4b56f-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4b56f-109">Return Value</span></span>  
  
|<span data-ttu-id="4b56f-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4b56f-110">HRESULT</span></span>|<span data-ttu-id="4b56f-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="4b56f-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4b56f-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="4b56f-112">S_OK</span></span>|<span data-ttu-id="4b56f-113">`Get`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="4b56f-113">`Get` returned successfully.</span></span>|  
|<span data-ttu-id="4b56f-114">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="4b56f-114">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="4b56f-115">`pwzBuffer`es demasiado pequeño.</span><span class="sxs-lookup"><span data-stu-id="4b56f-115">`pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="4b56f-116">ERROR_NO_MORE_ITEMS</span><span class="sxs-lookup"><span data-stu-id="4b56f-116">ERROR_NO_MORE_ITEMS</span></span>|<span data-ttu-id="4b56f-117">La enumeración no contiene más elementos.</span><span class="sxs-lookup"><span data-stu-id="4b56f-117">The enumeration contains no more items.</span></span>|  
|<span data-ttu-id="4b56f-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4b56f-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4b56f-119">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="4b56f-119">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4b56f-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4b56f-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4b56f-121">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="4b56f-121">The call timed out.</span></span>|  
|<span data-ttu-id="4b56f-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4b56f-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4b56f-123">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="4b56f-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4b56f-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4b56f-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4b56f-125">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="4b56f-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4b56f-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4b56f-126">E_FAIL</span></span>|<span data-ttu-id="4b56f-127">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="4b56f-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4b56f-128">Si el método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="4b56f-128">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4b56f-129">Las llamadas subsiguientes a cualquier método de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="4b56f-129">Subsequent calls to any hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4b56f-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4b56f-130">Remarks</span></span>  
 <span data-ttu-id="4b56f-131">La identidad en el índice 0 es la identidad específica para la arquitectura de procesador.</span><span class="sxs-lookup"><span data-stu-id="4b56f-131">The identity at index 0 is the identity specific to the processor architecture.</span></span> <span data-ttu-id="4b56f-132">La identidad en el índice 1 es el ensamblado de arquitectura neutral para el lenguaje intermedio de Microsoft (MSIL).</span><span class="sxs-lookup"><span data-stu-id="4b56f-132">The identity at index 1 is the architecture-neutral assembly for Microsoft intermediate language (MSIL).</span></span> <span data-ttu-id="4b56f-133">La identidad en el índice 2 no contiene ninguna información de arquitectura.</span><span class="sxs-lookup"><span data-stu-id="4b56f-133">The identity at index 2 contains no architecture information.</span></span>  
  
 <span data-ttu-id="4b56f-134">`Get`Normalmente se llama dos veces.</span><span class="sxs-lookup"><span data-stu-id="4b56f-134">`Get` is typically called twice.</span></span> <span data-ttu-id="4b56f-135">La primera llamada proporciona un valor null para `pwzBuffer`y establece `pcchBufferSize` en el tamaño adecuado para `pwzBuffer`.</span><span class="sxs-lookup"><span data-stu-id="4b56f-135">The first call supplies a null value for `pwzBuffer`, and sets `pcchBufferSize` to the size appropriate for `pwzBuffer`.</span></span> <span data-ttu-id="4b56f-136">La segunda llamada proporciona un tamaño adecuado `pwzBuffer`y contiene los datos de identidad de ensamblado canónicos tras la finalización.</span><span class="sxs-lookup"><span data-stu-id="4b56f-136">The second call supplies an appropriately sized `pwzBuffer`, and contains the canonical assembly identity data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b56f-137">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4b56f-137">Requirements</span></span>  
 <span data-ttu-id="4b56f-138">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b56f-138">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b56f-139">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4b56f-139">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4b56f-140">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4b56f-140">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4b56f-141">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b56f-141">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b56f-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="4b56f-142">See Also</span></span>  
 [<span data-ttu-id="4b56f-143">ICLRProbingAssemblyEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4b56f-143">ICLRProbingAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)  
 [<span data-ttu-id="4b56f-144">ICLRAssemblyIdentityManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4b56f-144">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)