---
title: "Serializar con una declaración XML (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8726f79e-2bb0-4ba0-969d-197cca591647
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e8544157104b202a36f2ef75b069bcdd297b9158
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="serializing-with-an-xml-declaration-visual-basic"></a>Serializar con una declaración XML (Visual Basic)
En este tema se describe cómo controlar si la serialización genera una declaración XML.  
  
## <a name="xml-declaration-generation"></a>Generación de declaración XML  
 La serialización en <xref:System.IO.File> o <xref:System.IO.TextWriter> mediante el método <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType> o el método <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType> genera una declaración XML. Cuando serializa en <xref:System.Xml.XmlWriter>, la configuración del escritor (especificada en un objeto <xref:System.Xml.XmlWriterSettings>) determina si se genera una declaración XML.  
  
 Si está serializando en una cadena mediante el método `ToString`, el XML resultante no incluirá una declaración XML.  
  
### <a name="serializing-with-an-xml-declaration"></a>Serializar con una declaración XML  
 En el ejemplo siguiente se crea un <xref:System.Xml.Linq.XElement>, se guarda el documento en un archivo y, a continuación, se imprime el archivo en la consola:  
  
```vb  
Dim root As XElement = <Root>  
                           <Child>child content</Child>  
                       </Root>  
root.Save("Root.xml")  
Dim str As String = File.ReadAllText("Root.xml")  
Console.WriteLine(str)  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<Root>  
  <Child>child content</Child>  
</Root>  
```  
  
### <a name="serializing-without-an-xml-declaration"></a>Serializar sin una declaración XML  
 En el siguiente ejemplo se muestra cómo guardar un <xref:System.Xml.Linq.XElement> en un <xref:System.Xml.XmlWriter>.  
  
```vb  
Dim sb As StringBuilder = New StringBuilder()  
Dim xws As XmlWriterSettings = New XmlWriterSettings()  
xws.OmitXmlDeclaration = True  
  
Using xw As XmlWriter = XmlWriter.Create(sb, xws)  
    Dim root = <Root>  
                   <Child>child content</Child>  
               </Root>  
    root.Save(xw)  
End Using  
Console.WriteLine(sb.ToString())  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```xml  
<Root><Child>child content</Child></Root>  
```  
  
## <a name="see-also"></a>Vea también  
 [Serializar árboles XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md)
