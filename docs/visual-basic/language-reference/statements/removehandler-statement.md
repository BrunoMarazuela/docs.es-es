---
title: "RemoveHandler (Instrucción)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.RemoveHandlerMethod
- vb.RemoveHandler
- RemoveHandler
helpviewer_keywords:
- RemoveHandler keyword [Visual Basic]
- RemoveHandler statement [Visual Basic]
ms.assetid: 647cd825-e877-4910-b4f1-8d168beebe6a
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 82d130c6536df7d72977a028333293b4e0ee89de
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="removehandler-statement"></a>RemoveHandler (Instrucción)
Quita la asociación entre un evento y un controlador de eventos.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|Definición|  
|---|---|  
|`event`|El nombre del evento que se va a controlar.|  
|`eventhandler`|El nombre del procedimiento que controla actualmente el evento.|  
  
## <a name="remarks"></a>Comentarios  
 El `AddHandler` y `RemoveHandler` instrucciones permiten iniciar y detener el control de eventos para un evento concreto en cualquier momento durante la ejecución del programa.  
  
> [!NOTE]
>  Para los eventos personalizados, la `RemoveHandler` instrucción invoca el evento `RemoveHandler` descriptor de acceso. Para obtener más información sobre eventos personalizados, vea [Event (instrucción)](../../../visual-basic/language-reference/statements/event-statement.md).  
  
## <a name="example"></a>Ejemplo  
 [!code-vb[VbVbalrEvents#17](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/removehandler-statement_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [AddHandler (instrucción)](../../../visual-basic/language-reference/statements/addhandler-statement.md)  
 [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)  
 [Event (instrucción)](../../../visual-basic/language-reference/statements/event-statement.md)  
 [Eventos](../../../visual-basic/programming-guide/language-features/events/index.md)
