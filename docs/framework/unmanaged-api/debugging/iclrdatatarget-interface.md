---
title: ICLRDataTarget (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataTarget
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDataTarget
helpviewer_keywords: ICLRDataTarget interface [.NET Framework debugging]
ms.assetid: e2f05155-9bef-4e11-b703-7f05890665ca
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6a40276b28f3d20428f0d7eb0556a762fdb56801
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdatatarget-interface"></a><span data-ttu-id="d2d3c-102">ICLRDataTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d2d3c-102">ICLRDataTarget Interface</span></span>
<span data-ttu-id="d2d3c-103">Proporciona métodos para la interacción con un elemento de destino de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="d2d3c-103">Provides methods for interaction with a target item of the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d2d3c-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="d2d3c-104">Methods</span></span>  
  
|<span data-ttu-id="d2d3c-105">Método</span><span class="sxs-lookup"><span data-stu-id="d2d3c-105">Method</span></span>|<span data-ttu-id="d2d3c-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="d2d3c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d2d3c-107">GetCurrentThreadID (método)</span><span class="sxs-lookup"><span data-stu-id="d2d3c-107">GetCurrentThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getcurrentthreadid-method.md)|<span data-ttu-id="d2d3c-108">Obtiene el identificador de sistema operativo para el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="d2d3c-108">Gets the operating system identifier for the current thread.</span></span>|  
|[<span data-ttu-id="d2d3c-109">GetImageBase (método)</span><span class="sxs-lookup"><span data-stu-id="d2d3c-109">GetImageBase Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getimagebase-method.md)|<span data-ttu-id="d2d3c-110">Obtiene la dirección de memoria de base de la imagen especificada.</span><span class="sxs-lookup"><span data-stu-id="d2d3c-110">Gets the base memory address for the specified image.</span></span>|  
|[<span data-ttu-id="d2d3c-111">GetMachineType (método)</span><span class="sxs-lookup"><span data-stu-id="d2d3c-111">GetMachineType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getmachinetype-method.md)|<span data-ttu-id="d2d3c-112">Obtiene un identificador para el tipo de conjunto de instrucciones que está usando el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="d2d3c-112">Gets an identifier for the kind of instruction set that the target process is using.</span></span>|  
|[<span data-ttu-id="d2d3c-113">GetPointerSize (método)</span><span class="sxs-lookup"><span data-stu-id="d2d3c-113">GetPointerSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getpointersize-method.md)|<span data-ttu-id="d2d3c-114">Obtiene el tamaño, en bytes, de un puntero al destino actual.</span><span class="sxs-lookup"><span data-stu-id="d2d3c-114">Gets the size, in bytes, of a pointer to the current target.</span></span>|  
|[<span data-ttu-id="d2d3c-115">GetThreadContext (método)</span><span class="sxs-lookup"><span data-stu-id="d2d3c-115">GetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getthreadcontext-method.md)|<span data-ttu-id="d2d3c-116">Obtiene un puntero al contexto del subproceso con el identificador especificado.</span><span class="sxs-lookup"><span data-stu-id="d2d3c-116">Gets a pointer to the context of the thread with the specified identifier.</span></span>|  
|[<span data-ttu-id="d2d3c-117">GetTLSValue (método)</span><span class="sxs-lookup"><span data-stu-id="d2d3c-117">GetTLSValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-gettlsvalue-method.md)|<span data-ttu-id="d2d3c-118">Obtiene un valor en el almacenamiento local de subprocesos (TLS) en el índice especificado para el subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="d2d3c-118">Gets a value in thread local storage (TLS) at the specified index for the specified thread.</span></span>|  
|[<span data-ttu-id="d2d3c-119">ReadVirtual (método)</span><span class="sxs-lookup"><span data-stu-id="d2d3c-119">ReadVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-readvirtual-method.md)|<span data-ttu-id="d2d3c-120">Lee datos de la dirección de memoria virtual especificada en el búfer especificado.</span><span class="sxs-lookup"><span data-stu-id="d2d3c-120">Reads data from the specified virtual memory address into the specified buffer.</span></span>|  
|[<span data-ttu-id="d2d3c-121">Request (método)</span><span class="sxs-lookup"><span data-stu-id="d2d3c-121">Request Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-request-method.md)|<span data-ttu-id="d2d3c-122">Llamado por los servicios de acceso a datos de common language runtime (CLR) para solicitar una operación, tal como se define por la implementación.</span><span class="sxs-lookup"><span data-stu-id="d2d3c-122">Called by the common language runtime (CLR) data access services to request an operation, as defined by the implementation.</span></span>|  
|[<span data-ttu-id="d2d3c-123">SetThreadContext (método)</span><span class="sxs-lookup"><span data-stu-id="d2d3c-123">SetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-setthreadcontext-method.md)|<span data-ttu-id="d2d3c-124">Establece el contexto actual del subproceso especificado en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="d2d3c-124">Sets the current context of the specified thread in the target process.</span></span>|  
|[<span data-ttu-id="d2d3c-125">SetTLSValue (método)</span><span class="sxs-lookup"><span data-stu-id="d2d3c-125">SetTLSValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-settlsvalue-method.md)|<span data-ttu-id="d2d3c-126">Establece un valor en el almacenamiento local de subprocesos (TLS) del subproceso especificado en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="d2d3c-126">Sets a value in the thread local storage (TLS) of the specified thread in the target process.</span></span>|  
|[<span data-ttu-id="d2d3c-127">WriteVirtual (método)</span><span class="sxs-lookup"><span data-stu-id="d2d3c-127">WriteVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-writevirtual-method.md)|<span data-ttu-id="d2d3c-128">Escribe datos desde el búfer especificado en la dirección de memoria virtual especificada.</span><span class="sxs-lookup"><span data-stu-id="d2d3c-128">Writes data from the specified buffer to the specified virtual memory address.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d2d3c-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d2d3c-129">Remarks</span></span>  
 <span data-ttu-id="d2d3c-130">El cliente API (es decir, el depurador) debe implementar esta interfaz según corresponda para el elemento de destino concreto.</span><span class="sxs-lookup"><span data-stu-id="d2d3c-130">The API client (that is, the debugger) must implement this interface as appropriate for the particular target item.</span></span> <span data-ttu-id="d2d3c-131">Por ejemplo, un proceso activo tendría una implementación diferente de la de un volcado de memoria.</span><span class="sxs-lookup"><span data-stu-id="d2d3c-131">For example, a live process would have an implementation different from that of a memory dump.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2d3c-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d2d3c-132">Requirements</span></span>  
 <span data-ttu-id="d2d3c-133">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2d3c-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2d3c-134">**Encabezado:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="d2d3c-134">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="d2d3c-135">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d2d3c-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d2d3c-136">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2d3c-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2d3c-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="d2d3c-137">See Also</span></span>  
 [<span data-ttu-id="d2d3c-138">ICLRDataTarget2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d2d3c-138">ICLRDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)  
 [<span data-ttu-id="d2d3c-139">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="d2d3c-139">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)