---
title: "ICeeGen::AddSectionReloc (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICeeGen.AddSectionReloc
api_location: mscoree.dll
api_type: COM
f1_keywords: ICeeGen::AddSectionReloc
helpviewer_keywords:
- AddSectionReloc method [.NET Framework metadata]
- ICeeGen::AddSectionReloc method [.NET Framework metadata]
ms.assetid: b500a260-1d57-4953-95e1-c27063f7c8da
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a74f01e3904c6f3f472110288abbec42fa892fdc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="iceegenaddsectionreloc-method"></a><span data-ttu-id="69a53-102">ICeeGen::AddSectionReloc (Método)</span><span class="sxs-lookup"><span data-stu-id="69a53-102">ICeeGen::AddSectionReloc Method</span></span>
<span data-ttu-id="69a53-103">Agrega una instrucción .reloc al código base.</span><span class="sxs-lookup"><span data-stu-id="69a53-103">Adds a .reloc instruction to the code base.</span></span>  
  
 <span data-ttu-id="69a53-104">Este método está obsoleto y no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="69a53-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69a53-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="69a53-105">Syntax</span></span>  
  
```  
HRESULT AddSectionReloc (  
   [in] HCEESECTION            section,  
   [in] ULONG                  offset,  
   [in] HCEESECTION            relativeTo,   
   [in] CeeSectionRelocType    relocType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="69a53-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="69a53-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="69a53-107">[in] La sección de código en memoria que se va a agregar una instrucción .reloc.</span><span class="sxs-lookup"><span data-stu-id="69a53-107">[in] The section of in-memory code to which to add a .reloc instruction.</span></span>  
  
 `offset`  
 <span data-ttu-id="69a53-108">[in] El desplazamiento de la sección.</span><span class="sxs-lookup"><span data-stu-id="69a53-108">[in] The offset of the section.</span></span>  
  
 `relativeTo`  
 <span data-ttu-id="69a53-109">[in] La sección a la que `offset` hace referencia.</span><span class="sxs-lookup"><span data-stu-id="69a53-109">[in] The section to which `offset` refers.</span></span>  
  
 `relocType`  
 <span data-ttu-id="69a53-110">[in] Uno de los [CeeSectionRelocType](../../../../docs/framework/unmanaged-api/metadata/ceesectionreloctype-enumeration.md) valores, que indica el tipo de instrucción .reloc para agregar.</span><span class="sxs-lookup"><span data-stu-id="69a53-110">[in] One of the [CeeSectionRelocType](../../../../docs/framework/unmanaged-api/metadata/ceesectionreloctype-enumeration.md) values, indicating the kind of .reloc instruction to add.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69a53-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="69a53-111">Requirements</span></span>  
 <span data-ttu-id="69a53-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="69a53-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69a53-113">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="69a53-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="69a53-114">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="69a53-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="69a53-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69a53-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69a53-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="69a53-116">See Also</span></span>  
 [<span data-ttu-id="69a53-117">ICeeGen (interfaz)</span><span class="sxs-lookup"><span data-stu-id="69a53-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)