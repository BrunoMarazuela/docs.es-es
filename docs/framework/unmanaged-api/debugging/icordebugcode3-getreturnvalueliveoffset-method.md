---
title: "ICorDebugCode3::GetReturnValueLiveOffset (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICorDebugCode3.GetReturnValueLiveOffset
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode3::GetReturnValueLiveOffset
helpviewer_keywords:
- ICorDebugCode3::GetReturnValueLiveOffset method [.NET Framework debugging]
- GetReturnValueLiveOffset method [.NET Framework debugging]
ms.assetid: 8c2ff5d8-8c04-4423-b1e1-e1c8764b36d3
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4516f2244b72bd4f254c5090b09d6d90579f1ae6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugcode3getreturnvalueliveoffset-method"></a><span data-ttu-id="ecfa4-102">ICorDebugCode3::GetReturnValueLiveOffset (Método)</span><span class="sxs-lookup"><span data-stu-id="ecfa4-102">ICorDebugCode3::GetReturnValueLiveOffset Method</span></span>
<span data-ttu-id="ecfa4-103">Para un desplazamiento de IL especificado, obtiene los desplazamientos nativos donde se debe colocar un punto de interrupción de modo que el depurador pueda obtener el valor devuelto de una función.</span><span class="sxs-lookup"><span data-stu-id="ecfa4-103">For a specified IL offset, gets the native offsets where a breakpoint should be placed so that the debugger can obtain the return value from a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecfa4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ecfa4-104">Syntax</span></span>  
  
```cpp
HRESULT GetReturnValueLiveOffset(  
    [in] ULONG32 ILoffset,  
    [in] ULONG32 bufferSize,   
    [out] ULONG32 *pFetched,   
    [out, size_is(buffersize), length_is(*pFetched)] ULong32 pOffsets[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ecfa4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ecfa4-105">Parameters</span></span>  
 `ILoffset`  
 <span data-ttu-id="ecfa4-106">Desplazamiento IL.</span><span class="sxs-lookup"><span data-stu-id="ecfa4-106">The IL offset.</span></span> <span data-ttu-id="ecfa4-107">Debe ser un sitio de la llamada de función o la llamada de función generará un error.</span><span class="sxs-lookup"><span data-stu-id="ecfa4-107">It must be a function call site or the function call will fail.</span></span>  
  
 `bufferSize`  
 <span data-ttu-id="ecfa4-108">Número de bytes disponible para almacenar `pOffsets`.</span><span class="sxs-lookup"><span data-stu-id="ecfa4-108">The number of bytes available to store `pOffsets`.</span></span>  
  
 `pFetched`  
 <span data-ttu-id="ecfa4-109">Un puntero al número de desplazamientos realmente devueltos.</span><span class="sxs-lookup"><span data-stu-id="ecfa4-109">A pointer to the number of offsets actually returned.</span></span> <span data-ttu-id="ecfa4-110">Generalmente, su valor es 1, pero una sola instrucción IL puede asignarse a varias instrucciones de ensamblado `CALL`.</span><span class="sxs-lookup"><span data-stu-id="ecfa4-110">Usually, its value is 1, but a single IL instruction can map to multiple `CALL` assembly instructions.</span></span>  
  
 `pOffsets`  
 <span data-ttu-id="ecfa4-111">Matriz de desplazamientos nativos.</span><span class="sxs-lookup"><span data-stu-id="ecfa4-111">An array of native offsets.</span></span> <span data-ttu-id="ecfa4-112">Normalmente, `pOffsets` contiene un único desplazamiento, aunque una sola instrucción IL puede asociar varios mapas a varias instrucciones de ensamblado `CALL`.</span><span class="sxs-lookup"><span data-stu-id="ecfa4-112">Typically, `pOffsets` contains a single offset, although a single IL instruction can map to multiple map to multiple `CALL` assembly instructions.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ecfa4-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ecfa4-113">Remarks</span></span>  
 <span data-ttu-id="ecfa4-114">Este método se utiliza junto con la [icordebugilframe3:: Getreturnvalueforiloffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) método para obtener el valor devuelto de un método que devuelve un tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="ecfa4-114">This method is used along with the [ICorDebugILFrame3::GetReturnValueForILOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) method to get the return value of a method that returns a reference type.</span></span> <span data-ttu-id="ecfa4-115">Pasar un desplazamiento IL a un sitio de la llamada de función a este método devuelve uno o varios desplazamientos nativos.</span><span class="sxs-lookup"><span data-stu-id="ecfa4-115">Passing an IL offset to a function call site to this method returns one or more native offsets.</span></span> <span data-ttu-id="ecfa4-116">El depurador puede establecer puntos de interrupción en estos desplazamientos nativos en la función.</span><span class="sxs-lookup"><span data-stu-id="ecfa4-116">The debugger can then set breakpoints on these native offsets in the function.</span></span> <span data-ttu-id="ecfa4-117">Cuando el depurador llega a uno de los puntos de interrupción, a continuación, puede pasar el mismo desplazamiento IL que pasó a este método para el [icordebugilframe3:: Getreturnvalueforiloffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) método para obtener el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="ecfa4-117">When the debugger hits one of the breakpoints, you can then pass the same IL offset that you passed to this method to the [ICorDebugILFrame3::GetReturnValueForILOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) method to get the return value.</span></span> <span data-ttu-id="ecfa4-118">A continuación, el depurador debe borrar todos los puntos de interrupción que estableció.</span><span class="sxs-lookup"><span data-stu-id="ecfa4-118">The debugger should then clear all the breakpoints that it set.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="ecfa4-119">El `ICorDebugCode3::GetReturnValueLiveOffset` y [icordebugilframe3:: Getreturnvalueforiloffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) métodos permiten obtener información del valor devuelto para solo los tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="ecfa4-119">The `ICorDebugCode3::GetReturnValueLiveOffset` and [ICorDebugILFrame3::GetReturnValueForILOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) methods allow you to get return value information for reference types only.</span></span> <span data-ttu-id="ecfa4-120">La recuperación de información de valor devuelto de tipos de valor (es decir, todos los tipos derivados de <xref:System.ValueType>) no se admite.</span><span class="sxs-lookup"><span data-stu-id="ecfa4-120">Retrieving return value information from value types (that is, all types that derive from <xref:System.ValueType>) is not supported.</span></span>  
  
 <span data-ttu-id="ecfa4-121">La función devuelve los valores `HRESULT` mostrados en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="ecfa4-121">The function returns the `HRESULT` values shown in the following table.</span></span>  
  
|<span data-ttu-id="ecfa4-122">Valor de `HRESULT`</span><span class="sxs-lookup"><span data-stu-id="ecfa4-122">`HRESULT` value</span></span>|<span data-ttu-id="ecfa4-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="ecfa4-123">Description</span></span>|  
|---------------------|-----------------|  
|`S_OK`|<span data-ttu-id="ecfa4-124">Correcto.</span><span class="sxs-lookup"><span data-stu-id="ecfa4-124">Success.</span></span>|  
|`CORDBG_E_INVALID_OPCODE`|<span data-ttu-id="ecfa4-125">El sitio de desplazamiento IL dado no es una instrucción de llamada o la función devuelve `void`.</span><span class="sxs-lookup"><span data-stu-id="ecfa4-125">The given IL offset site is not a call instruction, or the function returns `void`.</span></span>|  
|`CORDBG_E_UNSUPPORTED`|<span data-ttu-id="ecfa4-126">El desplazamiento IL dado es una llamada correcta, pero el tipo de valor devuelto no se admite para obtener un valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="ecfa4-126">The given IL offset is a proper call, but the return type is unsupported for getting a return value.</span></span>|  
  
 <span data-ttu-id="ecfa4-127">El método `ICorDebugCode3::GetReturnValueLiveOffset` solo está disponible en los sistemas basados en x86 y AMD64.</span><span class="sxs-lookup"><span data-stu-id="ecfa4-127">The `ICorDebugCode3::GetReturnValueLiveOffset` method is available only on x86-based and AMD64 systems.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ecfa4-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ecfa4-128">Requirements</span></span>  
 <span data-ttu-id="ecfa4-129">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ecfa4-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ecfa4-130">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ecfa4-130">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ecfa4-131">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ecfa4-131">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ecfa4-132">**Versiones de .NET framework:**[!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ecfa4-132">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecfa4-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="ecfa4-133">See Also</span></span>  
 [<span data-ttu-id="ecfa4-134">GetReturnValueForILOffset (método)</span><span class="sxs-lookup"><span data-stu-id="ecfa4-134">GetReturnValueForILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md)  
 [<span data-ttu-id="ecfa4-135">ICorDebugCode3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ecfa4-135">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)