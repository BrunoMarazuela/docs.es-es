---
title: Propiedad de eje descendiente XML Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlPropertyDescendantsAxis
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML descendant axis property [Visual Basic]
- descendant axis property [Visual Baisc]
- XML axis [Visual Basic], descendant
- XML [Visual Basic], accessing
ms.assetid: a178f85b-5d54-438f-8479-40b62af6fe76
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0f3c42b5134b058c010ca4c7a5ee7c24627c65fe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="xml-descendant-axis-property-visual-basic"></a>Propiedad de eje descendiente XML Visual Basic)
Proporciona acceso a los descendientes de los siguientes valores: una <xref:System.Xml.Linq.XElement> objeto, un <xref:System.Xml.Linq.XDocument> (objeto), una colección de <xref:System.Xml.Linq.XElement> objetos o una colección de <xref:System.Xml.Linq.XDocument> objetos.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
object...<descendant>  
```  
  
## <a name="parts"></a>Elementos  
 `object`  
 Obligatorio. Un objeto <xref:System.Xml.Linq.XElement>, un objeto <xref:System.Xml.Linq.XDocument>, una colección de objetos <xref:System.Xml.Linq.XElement> o una colección de objetos <xref:System.Xml.Linq.XDocument>.  
  
 ...<  
 Requerido. Denota el inicio de una propiedad de eje descendiente.  
  
 `descendant`  
 Obligatorio. Nombre de los nodos descendientes para tener acceso a la forma [`prefix``:`]`name`.  
  
|Parte|Descripción|  
|----------|-----------------|  
|`prefix`|Opcional. Prefijo de espacio de nombres XML para el nodo descendiente. Debe ser un espacio de nombres XML global que se define mediante una `Imports` instrucción.|  
|`name`|Obligatorio. Nombre local del nodo descendiente. Vea [nombres de atributos y elementos XML declarados](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).|  
  
 \>  
 Obligatorio. Denota el final de una propiedad de eje descendiente.  
  
## <a name="return-value"></a>Valor devuelto  
 Una colección de objetos <xref:System.Xml.Linq.XElement>.  
  
## <a name="remarks"></a>Comentarios  
 Puede usar una propiedad de eje descendiente XML para tener acceso a los nodos descendientes por nombre desde un <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument> objeto, o de una colección de <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument> objetos. Use el código XML `Value` propiedad que se va a obtener acceso al valor del primer nodo descendiente en la colección devuelta. Para obtener más información, consulte [propiedad Value de XML](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).  
  
 El [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compilador convierte las propiedades de eje descendiente en llamadas a la <xref:System.Xml.Linq.XContainer.Descendants%2A> método.  
  
## <a name="xml-namespaces"></a>Espacios de nombres XML  
 El nombre de una propiedad de eje descendiente puede usar únicamente espacios de nombres XML declarados globalmente con la `Imports` instrucción. No puede utilizar espacios de nombres XML declarados localmente dentro de literales de elemento XML. Para obtener más información, consulte [instrucción Imports (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo tener acceso al valor del primer nodo descendiente denominado `name` y los valores de todos los nodos descendientes denominados `phone` desde el `contacts` objeto.  
  
 [!code-vb[VbXMLSamples#25](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-descendant-axis-property_1.vb)]  
  
 Este código muestra el siguiente texto:  
  
 `Name: Patrick Hines`  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se declara `ns` como un prefijo de espacio de nombres XML. A continuación, utiliza el prefijo del espacio de nombres para crear un literal XML y obtener acceso al valor del primer nodo secundario con el nombre completo `ns:name`.  
  
 [!code-vb[VbXMLSamples#26](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-descendant-axis-property_2.vb)]  
  
 Este código muestra el siguiente texto:  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Xml.Linq.XElement>  
 [Propiedades del eje XML](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 [Literales XML](../../../visual-basic/language-reference/xml-literals/index.md)  
 [Crear XML en Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [Nombres de atributos y elementos XML declarados](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
