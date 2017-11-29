---
title: "IManagedObject::GetSerializedBuffer (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IManagedObject.GetSerializedBuffer
api_location: mscoree.dll
api_type: COM
f1_keywords: GetSerializedBuffer
helpviewer_keywords:
- IManagedObject::GetSerializedBuffer method [.NET Framework hosting]
- GetSerializedBuffer method [.NET Framework hosting]
ms.assetid: c17105bb-b49f-434e-8f9b-77f8c85b9220
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d326fba5cbdb38dd2c5d07f4f69f3f2d8e75114c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="imanagedobjectgetserializedbuffer-method"></a><span data-ttu-id="846ef-102">IManagedObject::GetSerializedBuffer (Método)</span><span class="sxs-lookup"><span data-stu-id="846ef-102">IManagedObject::GetSerializedBuffer Method</span></span>
<span data-ttu-id="846ef-103">Obtiene la representación de cadena de este objeto administrado.</span><span class="sxs-lookup"><span data-stu-id="846ef-103">Gets the string representation of this managed object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="846ef-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="846ef-104">Syntax</span></span>  
  
```  
HRESULT GetSerializedBuffer (  
    [out] BSTR *pBSTR  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="846ef-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="846ef-105">Parameters</span></span>  
 `pBSTR`  
 <span data-ttu-id="846ef-106">[out] Un puntero a una cadena que es el objeto serializado.</span><span class="sxs-lookup"><span data-stu-id="846ef-106">[out] A pointer to a string that is the serialized object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="846ef-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="846ef-107">Remarks</span></span>  
 <span data-ttu-id="846ef-108">El `GetSerializedBuffer` método serializa el objeto, por lo que se pueden calcular las referencias al cliente.</span><span class="sxs-lookup"><span data-stu-id="846ef-108">The `GetSerializedBuffer` method serializes the object so it can be marshaled to the client.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="846ef-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="846ef-109">Requirements</span></span>  
 <span data-ttu-id="846ef-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="846ef-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="846ef-111">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="846ef-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="846ef-112">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="846ef-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="846ef-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="846ef-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="846ef-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="846ef-114">See Also</span></span>  
 [<span data-ttu-id="846ef-115">IManagedObject (interfaz)</span><span class="sxs-lookup"><span data-stu-id="846ef-115">IManagedObject Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)