---
title: "IMetaDataAssemblyEmit::DefineExportedType (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataAssemblyEmit.DefineExportedType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineExportedType
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineExportedType method [.NET Framework metadata]
- DefineExportedType method [.NET Framework metadata]
ms.assetid: fad01d7a-3178-4c8c-9f0a-4641e3701c9b
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 59aae188e404ebc717a140fb7918e3fbf69f3f70
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyemitdefineexportedtype-method"></a>IMetaDataAssemblyEmit::DefineExportedType (Método)
Crea una estructura `ExportedType` que contiene los metadatos para el tipo exportado especificado y devuelve el token de metadatos asociado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT DefineExportedType (  
    [in]  LPCWSTR             szName,  
    [in]  mdToken             tkImplementation,   
    [in]  mdTypeDef           tkTypeDef,  
    [in]  DWORD               dwExportedTypeFlags,  
    [out] mdExportedType      *pmdct  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `szName`  
 [in] El nombre de tipo que se exportarán. Para la versión 1.1 de common language runtime, el nombre del tipo exportado debe coincidir exactamente con el nombre proporcionado en el `TypeDef` para el tipo.  
  
 `tkImplementation`  
 [in] Un token que especifica donde se implementa el tipo exportado. Los valores válidos y sus significados asociados son:  
  
-   `mdFile`El tipo se implementa en un archivo diferente dentro de este ensamblado.  
  
-   `mdAssemblyRef`El tipo se implementa en un ensamblado diferente.  
  
-   `mdExportedTYpe`El tipo está anidado dentro de otro tipo.  
  
-   `mdFileNil`El tipo está en el mismo archivo que el manifiesto y no es un tipo anidado.  
  
 `tkTypeDef`  
 [in] Un token de los metadatos que especifica el tipo que se exportarán. Este valor se introduce en el `TypeDef` tabla en el archivo que implementa el tipo y solo es pertinente si ese archivo está en este ensamblado.  
  
 `dwExportedTypeFlags`  
 [in] Una combinación bit a bit de [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) valores de enumeración que definen los valores de propiedad para el tipo exportado.  
  
 `pmdct`  
 [out] Un puntero al token de metadatos devuelto que indica el tipo exportado.  
  
## <a name="remarks"></a>Comentarios  
 Un `ExportedType` estructura de los metadatos se debe definir para cada tipo que está expuesto por este ensamblado y que se implementa en un módulo distinto del que contiene el manifiesto.  
  
## <a name="requirements"></a>Requisitos  
 **Plataforma:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** usada como recurso en MsCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [IMetaDataAssemblyEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
