---
title: "Cómo: Implementar explícitamente miembros de dos interfaces (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- inheritance [C#], explicitly implementing interface members
- interfaces [C#], explicitly implementing with inheritance
ms.assetid: 8b402ddc-dff9-4869-89cb-d718c764e68e
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f0820328f037008c152b2e23071ae0ba8dba02bd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-explicitly-implement-members-of-two-interfaces-c-programming-guide"></a>Cómo: Implementar explícitamente miembros de dos interfaces (Guía de programación de C#)
La implementación explícita de [interfaces](../../../csharp/language-reference/keywords/interface.md) también permite al programador implementar dos interfaces que tienen los mismos nombres de miembros y dar a cada miembro de una interfaz una implementación independiente. En este ejemplo se muestran las dimensiones de un cuadro en unidades métricas e inglesas. La [clase](../../../csharp/language-reference/keywords/class.md) Box implementa dos interfaces, IEnglishDimensions e IMetricDimensions, que representan los diferentes sistemas de medida. Ambas interfaces tienen nombres de miembros idénticos, Length y Width.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csProgGuideInheritance#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-members-of-two-interfaces_1.cs)]  
  
## <a name="robust-programming"></a>Programación sólida  
 Si quiere realizar las medidas en unidades inglesas de manera predeterminada, implemente los métodos Length y Width con normalidad e implemente explícitamente los métodos Length y Width de la interfaz IMetricDimensions:  
  
 [!code-csharp[csProgGuideInheritance#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-members-of-two-interfaces_2.cs)]  
  
 En este caso, se puede tener acceso a las unidades inglesas desde la instancia de clase y acceso a las unidades métricas desde la instancia de interfaz:  
  
 [!code-csharp[csProgGuideInheritance#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-members-of-two-interfaces_3.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Clases y structs](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [Interfaces](../../../csharp/programming-guide/interfaces/index.md)  
 [Cómo: Implementar explícitamente miembros de interfaz](../../../csharp/programming-guide/interfaces/how-to-explicitly-implement-interface-members.md)
