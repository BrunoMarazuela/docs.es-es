---
title: + (Operador) (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.+
helpviewer_keywords:
- arithmetic operators [Visual Basic], addition
- + operator
- concatenation operators [Visual Basic], syntax
- strings [Visual Basic], concatenating
- sum operator [Visual Basic]
ms.assetid: 5694778f-0a2c-4539-8009-f66f318fb46d
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fb0d66db2d777c046ccec69acc1f2069d21baf6c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-visual-basic"></a>+ (Operador, Visual Basic)
Suma dos números o devuelve el valor positivo de una expresión numérica. También puede utilizarse para concatenar dos expresiones de cadena.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
      expression1 + expression2  
- or -  
+ expression1  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|Definición|  
|---|---|  
|`expression1`|Obligatorio. Cualquier expresión numérica o de cadena.|  
|`expression2`|Obligatorio a menos que el `+` operador está calculando un valor negativo. Cualquier expresión numérica o de cadena.|  
  
## <a name="result"></a>Resultado  
 Si `expression1` y `expression2` son numéricos, el resultado es su suma aritmética.  
  
 Si `expression2` no está presente, el `+` operador es la *unario* operador de identidad para el valor sin modificar de una expresión. En este sentido, la operación consiste en conservar el signo de `expression1`, por lo que el resultado es negativo si `expression1` es negativo.  
  
 Si `expression1` y `expression2` son cadenas, el resultado es la concatenación de sus valores.  
  
 Si `expression1` y `expression2` son de tipos mixtos, la acción realizada depende de sus tipos, su contenido y la configuración de la [Option Strict (instrucción)](../../../visual-basic/language-reference/statements/option-strict-statement.md). Para obtener más información, vea las tablas en la sección "comentarios".  
  
## <a name="supported-types"></a>Tipos admitidos  
 Todos los tipos numéricos, incluidos los tipos sin signo y de punto flotante y `Decimal`, y `String`.  
  
## <a name="remarks"></a>Comentarios  
 En general, `+` realiza la suma aritmética cuando sea posible y los concatena solo cuando ambas expresiones son cadenas.  
  
 Si ninguna de las expresiones es un `Object`, Visual Basic realiza las siguientes acciones.  
  
|Tipos de datos de expresiones|Acción del compilador|  
|---|---|  
|Ambas expresiones son tipos de datos numéricos (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, o `Double`)|Agregar. El tipo de datos del resultado es un tipo numérico adecuado para los tipos de datos de `expression1` y `expression2`. Vea las tablas "Aritmética de enteros" en [tipos de datos de resultados de operador](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).|  
|Ambas expresiones son de tipo`String`|Concatenar.|  
|Una expresión es un tipo de datos numérico y la otra es una cadena|Si `Option Strict` es `On`, a continuación, generar un error del compilador.<br /><br /> Si `Option Strict` es `Off`, a continuación, convertir implícitamente el `String` a `Double` y agregar.<br /><br /> Si el `String` no se puede convertir a `Double`, a continuación, iniciar una <xref:System.InvalidCastException> excepción.|  
|Una expresión es un tipo de datos numéricos y el otro es [nada](../../../visual-basic/language-reference/nothing.md)|Agregar, con `Nothing` el valor es cero.|  
|Una expresión es una cadena y la otra es`Nothing`|Concatenación, con `Nothing` con valores como "".|  
  
 Si una expresión es un `Object` expresión, Visual Basic realiza las siguientes acciones.  
  
|Tipos de datos de expresiones|Acción del compilador|  
|---|---|  
|`Object`Expresión que contiene un valor numérico y el otro es un tipo de datos numéricos|Si `Option Strict` es `On`, a continuación, generar un error del compilador.<br /><br /> Si `Option Strict` es `Off`, a continuación, agregue.|  
|`Object`Expresión que contiene un valor numérico y el otro es de tipo`String`|Si `Option Strict` es `On`, a continuación, generar un error del compilador.<br /><br /> Si `Option Strict` es `Off`, a continuación, convertir implícitamente el `String` a `Double` y agregar.<br /><br /> Si el `String` no se puede convertir a `Double`, a continuación, iniciar una <xref:System.InvalidCastException> excepción.|  
|`Object`Expresión que contiene una cadena y la otra es un tipo de datos numéricos|Si `Option Strict` es `On`, a continuación, generar un error del compilador.<br /><br /> Si `Option Strict` es `Off`, a continuación, convertir implícitamente la cadena `Object` a `Double` y agregar.<br /><br /> Si la cadena `Object` no se puede convertir a `Double`, a continuación, iniciar una <xref:System.InvalidCastException> excepción.|  
|`Object`Expresión que contiene una cadena y la otra es de tipo`String`|Si `Option Strict` es `On`, a continuación, generar un error del compilador.<br /><br /> Si `Option Strict` es `Off`, a continuación, convertir implícitamente `Object` a `String` y concatenar.|  
  
 Si ambas expresiones son `Object` expresiones, Visual Basic realiza las siguientes acciones (`Option Strict Off` solo).  
  
|Tipos de datos de expresiones|Acción del compilador|  
|---|---|  
|Ambos `Object` expresiones contienen valores numéricos|Agregar.|  
|Ambos `Object` expresiones son de tipo`String`|Concatenar.|  
|Una `Object` expresión que contiene un valor numérico y el otro contiene una cadena|Convertir implícitamente la cadena `Object` a `Double` y agregar.<br /><br /> Si la cadena `Object` no se puede convertir en un valor numérico, a continuación, iniciar una <xref:System.InvalidCastException> excepción.|  
  
 Si el valor `Object` expresión se evalúa como [nada](../../../visual-basic/language-reference/nothing.md) o <xref:System.DBNull>, `+` operador lo trata como un `String` con un valor de "".  
  
> [!NOTE]
>  Cuando se usa el `+` (operador), es posible que no pueda determinar si se producirá la suma o la cadena de la concatenación. Use la `&` operador de concatenación para eliminar la ambigüedad y proporcionar código autoexplicativo.  
  
## <a name="overloading"></a>Sobrecarga  
 El `+` puede ser *sobrecargados*, lo que significa que una clase o estructura puede definir de nuevo su comportamiento cuando un operando tiene el tipo de esa clase o estructura. Si el código usa este operador en una clase o estructura de este tipo, asegúrese de que conocer su comportamiento redefinido. Para obtener más información, consulte [procedimientos de operadores](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `+` operador para sumar números. Si los operandos son ambos numéricos, Visual Basic calcula el resultado aritmético. El resultado aritmético representa la suma de los dos operandos.  
  
 [!code-vb[VbVbalrOperators#6](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_1.vb)]  
  
 También puede usar el `+` para concatenar cadenas. Si los operandos son cadenas, Visual Basic los concatena. El resultado de la concatenación representa una sola cadena que consta del contenido de los dos operandos uno tras otro.  
  
 Si los operandos son de tipos mixtos, el resultado depende de la configuración de la [Option Strict (instrucción)](../../../visual-basic/language-reference/statements/option-strict-statement.md). En el ejemplo siguiente se muestra el resultado cuando `Option Strict` es `On`.  
  
 [!code-vb[VbVbalrOperators#53](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_2.vb)]  
  
 [!code-vb[VbVbalrOperators#50](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_3.vb)]  
[!code-vb[VbVbalrOperators#51](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_4.vb)]  
  
 En el ejemplo siguiente se muestra el resultado cuando `Option Strict` es `Off`.  
  
 [!code-vb[VbVbalrOperators#54](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_5.vb)]  
  
 [!code-vb[VbVbalrOperators#50](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_3.vb)]  
[!code-vb[VbVbalrOperators#52](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_6.vb)]  
  
 Para eliminar la ambigüedad, debe usar el `&` en lugar del operador `+` para la concatenación.  
  
## <a name="see-also"></a>Vea también  
 [Operador &](../../../visual-basic/language-reference/operators/concatenation-operator.md)  
 [Operadores de concatenación](../../../visual-basic/language-reference/operators/concatenation-operators.md)  
 [Operadores aritméticos](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Operadores aritméticos en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)  
 [Option Strict (instrucción)](../../../visual-basic/language-reference/statements/option-strict-statement.md)
