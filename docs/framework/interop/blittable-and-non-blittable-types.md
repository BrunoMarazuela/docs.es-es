---
title: Tipos que pueden o que no pueden transferirse en bloque de bits
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- interop marshaling, blittable types
- blittable types, interop marshaling
ms.assetid: d03b050e-2916-49a0-99ba-f19316e5c1b3
caps.latest.revision: "23"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 10e9f4be3d02ac24c70c4a370ed96ff0dada130a
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="blittable-and-non-blittable-types"></a>Tipos que pueden o que no pueden transferirse en bloque de bits
La mayoría de los tipos de datos tienen una representación común en la memoria administrada y no administrada, y no requieren un tratamiento especial por parte del serializador de interoperabilidad. Estos tipos se denominan *tipos que pueden transferirse en bloque de bits* porque no requieren conversión cuando se pasan entre código administrado y código no administrado.  
  
 Las estructuras que se devuelven de llamadas de invocación de plataforma deben ser tipos que pueden transferirse en bloque de bits. La invocación de plataforma no admite estructuras que no pueden transferirse en bloque de bits como tipos de valor devuelto.  
  
 Los siguientes tipos del espacio de nombres <xref:System> son tipos que pueden transferirse en bloque de bits:  
  
-   <xref:System.Byte?displayProperty=nameWithType>  
  
-   <xref:System.SByte?displayProperty=nameWithType>  
  
-   <xref:System.Int16?displayProperty=nameWithType>  
  
-   <xref:System.UInt16?displayProperty=nameWithType>  
  
-   <xref:System.Int32?displayProperty=nameWithType>  
  
-   <xref:System.UInt32?displayProperty=nameWithType>  
  
-   <xref:System.Int64?displayProperty=nameWithType>  
  
-   <xref:System.UInt64?displayProperty=nameWithType>  
  
-   <xref:System.IntPtr?displayProperty=nameWithType>  
  
-   <xref:System.UIntPtr?displayProperty=nameWithType>  
  
-   <xref:System.Single?displayProperty=nameWithType>  
  
-   <xref:System.Double?displayProperty=nameWithType>  
  
 Los siguientes tipos complejos también son tipos que pueden transferirse en bloque de bits:  
  
-   Las matrices unidimensionales de tipos que pueden transferirse en bloque de bits, como una matriz de enteros. Pero un tipo que contiene una matriz variable de tipos que pueden transferirse en bloque de bits no se puede transferir en bloque de bits.  
  
-   Los tipos de valor con formato que solo contienen tipos que pueden transferirse en bloque de bits (y clases si se serializan como tipos con formato). Para más información sobre los tipos de valor con formato, vea [Serialización predeterminada para tipos de valor](http://msdn.microsoft.com/library/4d9a876c-e05a-40ba-bd85-bd22877f984a).  
  
 Las referencias a objetos no pueden transferirse en bloque de bits. Esto incluye una matriz de referencias a objetos que pueden transferirse en bloque de bits por sí mismos. Por ejemplo, se puede definir una estructura que puede transferirse en bloque de bits, pero no se puede definir un tipo que puede transferirse en bloque de bits que contiene una matriz de referencias a esas estructuras.  
  
 Como optimización, las matrices de tipos que pueden transferirse en bloque de bits y las clases que solo contienen miembros que pueden transferirse en bloque de bits se [anclan](../../../docs/framework/interop/copying-and-pinning.md) en lugar de copiarse durante la serialización. Estos tipos pueden parecer serializados como parámetros In/Out cuando el autor y el destinatario de la llamada están en el mismo contenedor. Pero estos tipos se serializan realmente como parámetros In y se deben aplicar los atributos <xref:System.Runtime.InteropServices.InAttribute> y <xref:System.Runtime.InteropServices.OutAttribute> si se quiere serializar el argumento como un parámetro In/Out.  
  
 Algunos tipos de datos administrados requieren una representación diferente en un entorno sin administrar. Estos tipos de datos que no pueden transferirse en bloque de bits se deben convertir a un formato que se pueda serializar. Por ejemplo, las cadenas administradas son tipos que no pueden transferirse en bloque de bits porque se deben convertir en objetos de cadena antes de que se puedan serializar.  
  
 En la tabla siguiente se enumeran los tipos del espacio de nombres <xref:System> que no pueden transferirse en bloque de bits. [Delegados](http://msdn.microsoft.com/library/d176ee76-f982-494b-b03d-92e4118896e2), que son estructuras de datos que hacen referencia a un método estático o a una instancia de clase, y que tampoco pueden transferirse en bloque de bits.  
  
|Tipo que no puede transferirse en bloque de bits|Descripción|  
|-------------------------|-----------------|  
|[System.Array](../../../docs/framework/interop/default-marshaling-for-arrays.md)|Se convierte a una matriz de estilo de C o a una `SAFEARRAY`.|  
|[System.Boolean](http://msdn.microsoft.com/library/d4c00537-70f7-4ca6-8197-bfc1ec037ff9)|Se convierte a un valor de uno, dos o cuatro bytes con `true` como 1 o -1.|  
|[System.Char](http://msdn.microsoft.com/library/cecc87c1-075e-4cde-aa56-33d189f66feb)|Se convierte a un carácter ANSI o Unicode.|  
|[System.Class](http://msdn.microsoft.com/library/fe334af5-0123-43d8-be84-26f6f023ddb6)|Se convierte a una interfaz de clase.|  
|[System.Object](../../../docs/framework/interop/default-marshaling-for-objects.md)|Se convierte a una variante o una interfaz.|  
|[System.Mdarray](../../../docs/framework/interop/default-marshaling-for-arrays.md)|Se convierte a una matriz de estilo de C o a una `SAFEARRAY`.|  
|[System.String](../../../docs/framework/interop/default-marshaling-for-strings.md)|Se convierte a una cadena que termina en una referencia nula o a un tipo BSTR.|  
|[System.Valuetype](http://msdn.microsoft.com/library/4d9a876c-e05a-40ba-bd85-bd22877f984a)|Se convierte a una estructura con un diseño de memoria fijo.|  
|[System.Szarray](../../../docs/framework/interop/default-marshaling-for-arrays.md)|Se convierte a una matriz de estilo de C o a una `SAFEARRAY`.|  
  
 Solo se admiten los tipos de clase y objeto con la interoperabilidad COM. Para los tipos correspondientes en [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], C# y C++, vea la [Información general de la biblioteca de clases de .NET Framework](../../../docs/standard/class-library-overview.md).  
  
## <a name="see-also"></a>Vea también  
 [Comportamiento predeterminado del cálculo de referencias](../../../docs/framework/interop/default-marshaling-behavior.md)
