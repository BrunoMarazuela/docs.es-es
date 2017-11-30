---
title: "CreateVersionStringFromModule (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CreateVersionStringFromModule
api_location: dbgshim.dll
api_type: COM
f1_keywords: CreateVersionStringFromModule
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
- CreateVersionStringFromModule function
ms.assetid: 3d2fe9bd-75ef-4364-84a6-da1e1994ac1a
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6b8fb3cdb0bb2d7536c1c1514d4202271411d112
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="createversionstringfrommodule-function"></a><span data-ttu-id="9c37a-102">CreateVersionStringFromModule (Función)</span><span class="sxs-lookup"><span data-stu-id="9c37a-102">CreateVersionStringFromModule Function</span></span>
<span data-ttu-id="9c37a-103">Crea una cadena de versión a partir de una ruta de acceso de Common Language Runtime (CLR) en un proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="9c37a-103">Creates a version string from a common language runtime (CLR) path in a target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c37a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9c37a-104">Syntax</span></span>  
  
```  
HRESULT CreateVersionStringFromModule (  
    [in]  DWORD      pidDebuggee,  
    [in]  LPCWSTR    szModuleName,  
    [out, size_is(cchBuffer),  
          length_is(*pdwLength)] LPWSTR Buffer,  
    [in]  DWORD      cchBuffer,  
    [out] DWORD*     pdwLength  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9c37a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9c37a-105">Parameters</span></span>  
 `pidDebuggee`  
 <span data-ttu-id="9c37a-106">[in] Identificador del proceso en el que se carga el CLR de destino.</span><span class="sxs-lookup"><span data-stu-id="9c37a-106">[in] Identifier of the process in which the target CLR is loaded.</span></span>  
  
 `szModuleName`  
 <span data-ttu-id="9c37a-107">[in] Ruta de acceso completa o relativa al CLR de destino que se carga en el proceso.</span><span class="sxs-lookup"><span data-stu-id="9c37a-107">[in] Full or relative path to the target CLR that is loaded in the process.</span></span>  
  
 `pBuffer`  
 <span data-ttu-id="9c37a-108">[out] Búfer de retorno para almacenar la cadena de versión del CLR de destino.</span><span class="sxs-lookup"><span data-stu-id="9c37a-108">[out] Return buffer for storing the version string for the target CLR.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="9c37a-109">[in] Tamaño de `pBuffer`.</span><span class="sxs-lookup"><span data-stu-id="9c37a-109">[in] Size of `pBuffer`.</span></span>  
  
 `pdwLength`  
 <span data-ttu-id="9c37a-110">[out] Longitud de la cadena de versión devuelta por `pBuffer`.</span><span class="sxs-lookup"><span data-stu-id="9c37a-110">[out] Length of the version string returned by `pBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9c37a-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9c37a-111">Return Value</span></span>  
 <span data-ttu-id="9c37a-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="9c37a-112">S_OK</span></span>  
 <span data-ttu-id="9c37a-113">La cadena de versión del CLR de destino se devolvió correctamente en `pBuffer`.</span><span class="sxs-lookup"><span data-stu-id="9c37a-113">The version string for the target CLR was successfully returned in `pBuffer`.</span></span>  
  
 <span data-ttu-id="9c37a-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="9c37a-114">E_INVALIDARG</span></span>  
 <span data-ttu-id="9c37a-115">`szModuleName` es NULL, o bien `pBuffer` o `cchBuffer` es NULL.</span><span class="sxs-lookup"><span data-stu-id="9c37a-115">`szModuleName` is null, or either `pBuffer` or `cchBuffer` is null.</span></span> <span data-ttu-id="9c37a-116">`pBuffer` y `cchBuffer` deben ser ambos NULL o no NULL.</span><span class="sxs-lookup"><span data-stu-id="9c37a-116">`pBuffer` and `cchBuffer` must both be null or non-null.</span></span>  
  
 <span data-ttu-id="9c37a-117">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="9c37a-117">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>  
 <span data-ttu-id="9c37a-118">`pdwLength` es mayor que `cchBuffer`.</span><span class="sxs-lookup"><span data-stu-id="9c37a-118">`pdwLength` is greater than `cchBuffer`.</span></span> <span data-ttu-id="9c37a-119">Este puede ser el resultado esperado si pasó NULL tanto para `pBuffer` como para `cchBuffer`, y consultó el tamaño del búfer necesario usando `pdwLength`.</span><span class="sxs-lookup"><span data-stu-id="9c37a-119">This may be an expected result if you have passed null for both `pBuffer` and `cchBuffer`, and queried the necessary buffer size by using `pdwLength`.</span></span>  
  
 <span data-ttu-id="9c37a-120">HRESULT_FROM_WIN32(ERROR_MOD_NOT_FOUND)</span><span class="sxs-lookup"><span data-stu-id="9c37a-120">HRESULT_FROM_WIN32(ERROR_MOD_NOT_FOUND)</span></span>  
 <span data-ttu-id="9c37a-121">`szModuleName` no contiene una ruta de acceso a un CLR válido en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="9c37a-121">`szModuleName` does not contain a path to a valid CLR in the target process.</span></span>  
  
 <span data-ttu-id="9c37a-122">E_FAIL (u otros códigos devueltos de E_)</span><span class="sxs-lookup"><span data-stu-id="9c37a-122">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="9c37a-123">`pidDebuggee` no hace referencia a un proceso válido, u otro error.</span><span class="sxs-lookup"><span data-stu-id="9c37a-123">`pidDebuggee` does not refer to a valid process, or other failure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9c37a-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9c37a-124">Remarks</span></span>  
 <span data-ttu-id="9c37a-125">Esta función acepta un proceso de CLR que se identifica mediante `pidDebuggee` y una ruta de acceso de cadena especificada por `szModuleName`.</span><span class="sxs-lookup"><span data-stu-id="9c37a-125">This function accepts a CLR process that is identified by `pidDebuggee` and a string path that is specified by `szModuleName`.</span></span> <span data-ttu-id="9c37a-126">La cadena de versión se devuelve en el búfer al que `pBuffer` apunta.</span><span class="sxs-lookup"><span data-stu-id="9c37a-126">The version string is returned in the buffer that `pBuffer` points to.</span></span> <span data-ttu-id="9c37a-127">Esta cadena es opaca para el usuario de la función; es decir, no tiene ningún significado intrínseco en la propia cadena de versión.</span><span class="sxs-lookup"><span data-stu-id="9c37a-127">This string is opaque to the function user; that is, there is no intrinsic meaning in the version string itself.</span></span> <span data-ttu-id="9c37a-128">Se usa únicamente en el contexto de esta función y la [CreateDebuggingInterfaceFromVersion (función)](../../../../docs/framework/unmanaged-api/debugging/createdebugginginterfacefromversion-function-for-silverlight.md).</span><span class="sxs-lookup"><span data-stu-id="9c37a-128">It is used solely in the context of this function and the [CreateDebuggingInterfaceFromVersion function](../../../../docs/framework/unmanaged-api/debugging/createdebugginginterfacefromversion-function-for-silverlight.md).</span></span>  
  
 <span data-ttu-id="9c37a-129">Se debe llamar dos veces a esta función.</span><span class="sxs-lookup"><span data-stu-id="9c37a-129">This function should be called twice.</span></span> <span data-ttu-id="9c37a-130">Cuando la llame por primera vez, pase NULL tanto para `pBuffer` como para `cchBuffer`.</span><span class="sxs-lookup"><span data-stu-id="9c37a-130">When you call it the first time, pass null for both `pBuffer` and `cchBuffer`.</span></span> <span data-ttu-id="9c37a-131">Al hacerlo, el tamaño del búfer necesario para `pBuffer` se devuelve en `pdwLength`.</span><span class="sxs-lookup"><span data-stu-id="9c37a-131">When you do this, the size of the buffer necessary for `pBuffer` will be returned in `pdwLength`.</span></span> <span data-ttu-id="9c37a-132">Después puede llamar a la función una segunda vez y pasar el búfer en `pBuffer` y su tamaño en `cchBuffer`.</span><span class="sxs-lookup"><span data-stu-id="9c37a-132">You can then call the function a second time, and pass the buffer in `pBuffer` and its size in `cchBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c37a-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9c37a-133">Requirements</span></span>  
 <span data-ttu-id="9c37a-134">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c37a-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c37a-135">**Encabezado:** dbgshim.h</span><span class="sxs-lookup"><span data-stu-id="9c37a-135">**Header:** dbgshim.h</span></span>  
  
 <span data-ttu-id="9c37a-136">**Biblioteca:** dbgshim.dll</span><span class="sxs-lookup"><span data-stu-id="9c37a-136">**Library:** dbgshim.dll</span></span>  
  
 <span data-ttu-id="9c37a-137">**Versiones de .NET framework:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="9c37a-137">**.NET Framework Versions:** 3.5 SP1</span></span>