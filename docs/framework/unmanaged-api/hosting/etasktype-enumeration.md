---
title: "ETaskType (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ETaskType
api_location: mscoree.dll
api_type: COM
f1_keywords: ETaskType
helpviewer_keywords: ETaskType enumeration [.NET Framework hosting]
ms.assetid: aa527b31-89d4-41f2-ad6f-63b76950b7df
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 52e027c5d2ead70bbd624fafe3021121557cd261
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="etasktype-enumeration"></a><span data-ttu-id="e8f3e-102">ETaskType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="e8f3e-102">ETaskType Enumeration</span></span>
<span data-ttu-id="e8f3e-103">Contiene valores que indican el tipo de tarea que se representa mediante un [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) o un [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="e8f3e-103">Contains values that indicate the type of task that is represented by either an [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) or an [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8f3e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e8f3e-104">Syntax</span></span>  
  
```  
typedef enum ETaskType {  
    TT_DEBUGGERHELPER           = 0x1,  
    TT_GC                       = 0x2,  
    TT_FINALIZER                = 0x4,  
    TT_THREADPOOL_TIMER         = 0x8,  
    TT_THREADPOOL_GATE          = 0x10,  
    TT_THREADPOOL_WORKER        = 0x20,  
    TT_THREADPOOL_IOCOMPLETION  = 0x40,  
    TT_ADUNLOAD                 = 0x80,  
    TT_USER                     = 0x100,  
    TT_THREADPOOL_WAIT          = 0x200,  
    TT_UNKNOWN                  = 0x80000000  
} ETaskType;  
```  
  
## <a name="members"></a><span data-ttu-id="e8f3e-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="e8f3e-105">Members</span></span>  
  
|<span data-ttu-id="e8f3e-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="e8f3e-106">Member</span></span>|<span data-ttu-id="e8f3e-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="e8f3e-107">Description</span></span>|  
|------------|-----------------|  
|`TT_ADUNLOAD`|<span data-ttu-id="e8f3e-108">La interfaz representa una tarea de descarga de dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="e8f3e-108">The interface represents an application domain unloading task.</span></span>|  
|`TT_DEBUGGERHELPER`|<span data-ttu-id="e8f3e-109">La interfaz representa una tarea de la aplicación auxiliar de depurador.</span><span class="sxs-lookup"><span data-stu-id="e8f3e-109">The interface represents a debugger helper task.</span></span>|  
|`TT_FINALIZER`|<span data-ttu-id="e8f3e-110">La interfaz representa una tarea de finalizador.</span><span class="sxs-lookup"><span data-stu-id="e8f3e-110">The interface represents a finalizer task.</span></span>|  
|`TT_GC`|<span data-ttu-id="e8f3e-111">La interfaz representa una tarea de recopilación de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="e8f3e-111">The interface represents a garbage collection task.</span></span>|  
|`TT_THREADPOOL_GATE`|<span data-ttu-id="e8f3e-112">La interfaz representa una tarea de subproceso de puerta.</span><span class="sxs-lookup"><span data-stu-id="e8f3e-112">The interface represents a gate thread task.</span></span>|  
|`TT_THREADPOOL_IOCOMPLETION`|<span data-ttu-id="e8f3e-113">La interfaz representa una tarea de subproceso de E/S o una tarea de subproceso de puerto de finalización.</span><span class="sxs-lookup"><span data-stu-id="e8f3e-113">The interface represents an I/O thread task or a completion port thread task.</span></span>|  
|`TT_THREADPOOL_TIMER`|<span data-ttu-id="e8f3e-114">La interfaz representa una tarea de subproceso de temporizador.</span><span class="sxs-lookup"><span data-stu-id="e8f3e-114">The interface represents a timer thread task.</span></span>|  
|`TT_THREADPOOL_WAIT`|<span data-ttu-id="e8f3e-115">La interfaz representa una tarea de subproceso de espera.</span><span class="sxs-lookup"><span data-stu-id="e8f3e-115">The interface represents a wait thread task.</span></span>|  
|`TT_THREADPOOL_WORKER`|<span data-ttu-id="e8f3e-116">La interfaz representa una tarea de subproceso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="e8f3e-116">The interface represents a worker thread task.</span></span>|  
|`TT_UNKNOWN`|<span data-ttu-id="e8f3e-117">La tarea es desconocida.</span><span class="sxs-lookup"><span data-stu-id="e8f3e-117">The task is unknown.</span></span>|  
|`TT_USER`|<span data-ttu-id="e8f3e-118">La interfaz representa una tarea de usuario.</span><span class="sxs-lookup"><span data-stu-id="e8f3e-118">The interface represents a user task.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e8f3e-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e8f3e-119">Requirements</span></span>  
 <span data-ttu-id="e8f3e-120">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8f3e-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8f3e-121">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e8f3e-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e8f3e-122">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e8f3e-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e8f3e-123">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8f3e-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8f3e-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="e8f3e-124">See Also</span></span>  
 [<span data-ttu-id="e8f3e-125">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="e8f3e-125">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)