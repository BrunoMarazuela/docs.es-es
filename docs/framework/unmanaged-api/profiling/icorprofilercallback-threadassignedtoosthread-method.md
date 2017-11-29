---
title: "ICorProfilerCallback::ThreadAssignedToOSThread (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ThreadAssignedToOSThread
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ThreadAssignedToOSThread
helpviewer_keywords:
- ThreadAssignedToOSThread method [.NET Framework profiling]
- ICorProfilerCallback::ThreadAssignedToOSThread method [.NET Framework profiling]
ms.assetid: f9671e5a-7b14-4f5b-8404-58136422c8b2
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c70de2b53fd428361d5404aa406d2b2be67d0914
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackthreadassignedtoosthread-method"></a><span data-ttu-id="8274e-102">ICorProfilerCallback::ThreadAssignedToOSThread (Método)</span><span class="sxs-lookup"><span data-stu-id="8274e-102">ICorProfilerCallback::ThreadAssignedToOSThread Method</span></span>
<span data-ttu-id="8274e-103">Notifica al generador de perfiles que se va a implementar un subproceso administrado mediante un subproceso concreto del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="8274e-103">Notifies the profiler that a managed thread is being implemented using a particular operating system thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8274e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8274e-104">Syntax</span></span>  
  
```  
HRESULT ThreadAssignedToOSThread(  
    [in] ThreadID managedThreadId,  
    [in] DWORD    osThreadId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8274e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8274e-105">Parameters</span></span>  
 `managedThreadId`  
 <span data-ttu-id="8274e-106">[in] El identificador del subproceso administrado.</span><span class="sxs-lookup"><span data-stu-id="8274e-106">[in] The identifier of the managed thread.</span></span>  
  
 `osThreadId`  
 <span data-ttu-id="8274e-107">[in] El identificador de subproceso del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="8274e-107">[in] The identifier of the operating system thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8274e-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8274e-108">Remarks</span></span>  
 <span data-ttu-id="8274e-109">El `ThreadAssignedToOSThread` existe devolución de llamada para que el generador de perfiles puede mantener una asignación precisa entre las fibras de subprocesos del sistema operativo para los subprocesos administrados.</span><span class="sxs-lookup"><span data-stu-id="8274e-109">The `ThreadAssignedToOSThread` callback exists so that the profiler can maintain an accurate mapping across fibers of operating system threads to managed threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8274e-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8274e-110">Requirements</span></span>  
 <span data-ttu-id="8274e-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8274e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8274e-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8274e-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8274e-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8274e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8274e-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8274e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8274e-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="8274e-115">See Also</span></span>  
 [<span data-ttu-id="8274e-116">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8274e-116">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)