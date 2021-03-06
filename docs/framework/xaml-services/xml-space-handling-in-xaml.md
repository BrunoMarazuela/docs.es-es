---
title: Control de xml:space en XAML
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XAML [XAML Services], xml:space attribute
- XAML [XAML Services], whitespace processing
- xml:space attribute [XAML Services]
- whitespace processing [XAML Services]
ms.assetid: 5e1814f0-5b30-43d5-8c88-dede335a89d7
caps.latest.revision: "15"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8b8356cdb47b6b834e8d9a6bb84b26445af6d865
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="xmlspace-handling-in-xaml"></a>Control de xml:space en XAML
El `xml:space` es un atributo definido por el XML que declara el comportamiento del procesamiento de espacios en blanco significativos dentro de un elemento de objeto. Este comportamiento es pertinente para todo el contenido (texto interno) incluido dentro del elemento donde `xml:space` se declara y también limita su ámbito a los elementos secundarios.  
  
## <a name="xaml-attribute-usage"></a>Uso de atributos XAML  
  
```xaml  
<object xml:space="preserve" />  
```  
  
 \- o -  
  
```xaml  
<object xml:space="default" />  
```  
  
## <a name="remarks"></a>Comentarios  
 La definición de la `xml:space` atributo en XAML que incluye sus dos valores posibles se deriva de `xml:space` tal como se define como un "atributo especial" por especificaciones W3C para XML.  
  
 El valor predeterminado de la `xml:space` atributo es el valor literal `"default"`. Para el valor `"default"`, o si `xml:space` no se indica en absoluto, el comportamiento de análisis de espacio en blanco significativo es el control de forma predeterminada, tal como se define en el tema [procesamiento de espacios en blanco en XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).  
  
 Para conservar espacio en blanco en el contenido del elemento de objeto, especifique `xml:space="preserve"` en ese elemento de objeto.  
  
 En la mayoría de interpretaciones, la `xml:space` efectos del atributo y el valor del atributo se limitan a los elementos secundarios.  
  
 Para obtener una explicación completa de procesamiento de espacios en XAML, vea [procesamiento de espacios en blanco en XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento de espacios en blanco en XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md)  
 [Información general sobre XAML (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
