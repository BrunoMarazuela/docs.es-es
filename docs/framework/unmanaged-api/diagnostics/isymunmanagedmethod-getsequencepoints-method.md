---
title: "ISymUnmanagedMethod::GetSequencePoints (Método)"
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
- ISymUnmanagedMethod.GetSequencePoints
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetSequencePoints
helpviewer_keywords:
- ISymUnmanagedMethod::GetSequencePoints method [.NET Framework debugging]
- GetSequencePoints method [.NET Framework debugging]
ms.assetid: f909ac48-3d8f-49fb-a369-e3d9959151cd
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 071cbb6c33b56cb4fb409ab634a89f589db5bab8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedmethodgetsequencepoints-method"></a>ISymUnmanagedMethod::GetSequencePoints (Método)
Obtiene todos los puntos de secuencia dentro de este método.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetSequencePoints(  
    [in]  ULONG32  cPoints,  
    [out] ULONG32  *pcPoints,  
    [in, size_is(cPoints)] ULONG32  offsets[],  
    [in, size_is(cPoints)] ISymUnmanagedDocument* documents[],  
    [in, size_is(cPoints)] ULONG32  lines[],  
    [in, size_is(cPoints)] ULONG32  columns[],  
    [in, size_is(cPoints)] ULONG32  endLines[],  
    [in, size_is(cPoints)] ULONG32  endColumns[]);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `cPoints`  
 [in] A `ULONG32` que recibe el tamaño de la `offsets`, `documents`, `lines`, `columns`, `endLines`, y `endColumns` matrices.  
  
 `pcPoints`  
 [out] Un puntero a un `ULONG32` que recibe la longitud del búfer necesario para contener los puntos de secuencia.  
  
 `offsets`  
 [in] Una matriz en la que se va a almacenar el Microsoft intermedio desplazamientos del lenguaje (MSIL) desde el principio del método para los puntos de secuencia.  
  
 `documents`  
 [in] Matriz en la que se va a almacenar los documentos en el que se ubican los puntos de secuencia.  
  
 `lines`  
 [in] Matriz en la que se almacenan las líneas de los documentos en el que se ubican los puntos de secuencia.  
  
 `columns`  
 [in] Matriz en la que se almacenan las columnas de los documentos en el que se ubican los puntos de secuencia.  
  
 `endLines`  
 [in] Matriz de líneas de los documentos en las que la secuencia de puntos finales.  
  
 `endColumns`  
 [in] Matriz de columnas de los documentos en las que la secuencia de puntos finales.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vea también  
 [ISymUnmanagedMethod (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
