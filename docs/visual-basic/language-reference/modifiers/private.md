---
title: Private (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Private
helpviewer_keywords:
- Private keyword [Visual Basic]
- Private keyword [Visual Basic], syntax
ms.assetid: aba74a2e-5824-4613-bf63-b9ec7787f4e6
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 07450c2a5443bf6bc147cad2cfc779072bfc363b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="private-visual-basic"></a>Private (Visual Basic)
Especifica que uno o varios elementos de programación declarados son accesibles únicamente desde dentro de su contexto de declaración, incluyendo desde dentro de los tipos contenidos.  
  
## <a name="remarks"></a>Comentarios  
 Si un elemento de programación representa la funcionalidad de propietario, o contiene datos confidenciales, normalmente es conveniente limitar el acceso a él como estrictamente como sea posible. Alcanzar la limitación máxima al permitir que el módulo, clase o estructura que define para tener acceso a él. Para limitar el acceso a un elemento de esta manera, puede declararlo con `Private`.  
  
## <a name="rules"></a>Reglas  
  
-   **Contexto de la declaración.** Solo se puede usar `Private` en un nivel de módulo. Esto significa que el contexto de la declaración de un `Private` elemento debe ser un módulo, clase o estructura y no puede ser un archivo de código fuente, el espacio de nombres, la interfaz o el procedimiento.  
  
## <a name="behavior"></a>Comportamiento  
  
-   **Nivel de acceso.** Puede tener acceso todo el código dentro de un contexto de declaración su `Private` elementos. Esto incluye el código dentro de un tipo contenido, como una clase anidada o una expresión de asignación en una enumeración. Ningún código fuera del contexto de declaración puede tener acceso a su `Private` elementos.  
  
-   **Modificadores de acceso.** Las palabras clave que especifican el nivel de acceso se denominan *los modificadores de acceso*. Para obtener una comparación de los modificadores de acceso, consulte [tener acceso a niveles en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 El modificador `Private` se puede utilizar en los contextos siguientes:  
  
 [Class (instrucción)](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [Const (instrucción)](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [Declare (instrucción)](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Delegate (instrucción)](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [Dim (instrucción)](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Enum (instrucción)](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [Event (instrucción)](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Interface (instrucción)](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Structure (instrucción)](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Vea también  
 [Public](../../../visual-basic/language-reference/modifiers/public.md)  
 [Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
 [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
 [Niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [Procedimientos](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [Estructuras](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Objetos y clases](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
