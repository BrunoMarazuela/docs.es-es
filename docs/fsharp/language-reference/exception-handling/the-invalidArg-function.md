---
title: "Excepciones: función invalidArg (F#)"
description: "Obtenga información acerca de cómo la función de F # 'invalidArg' genera una excepción de argumento."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: d375b704-6b27-493e-bd1d-ee217a53c4b5
ms.openlocfilehash: 107bef361a6bd034e3d6a2227e18cf64b1b04576
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="exceptions-the-invalidarg-function"></a>Excepciones: función invalidArg

El `invalidArg` función genera una excepción de argumento.


## <a name="syntax"></a>Sintaxis

```fsharp
invalidArg parameter-name error-message-string
```

## <a name="remarks"></a>Comentarios
El nombre del parámetro en la sintaxis anterior es una cadena con el nombre del parámetro cuyo argumento no era válido. El *cadena de mensaje de error* es una cadena literal o un valor de tipo `string`. Se convierte en el `Message` propiedad del objeto de excepción.

La excepción generada por `invalidArg` es un `System.ArgumentException` excepción. El código siguiente muestra el uso de `invalidArg` para producir una excepción.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet6101.fs)]

El resultado es el siguiente, seguido de un seguimiento de pila (no se muestra).

```
December
January
System.ArgumentException: Month parameter out of range.
```

## <a name="see-also"></a>Vea también
[Control de excepciones](index.md)

[Tipos de excepción](exception-types.md)

[Exceptions: The `try...with` Expression](the-try-with-expression.md) (Excepciones: la expresión `try...with`)

[Exceptions: The `try...finally` Expression](the-try-finally-expression.md) (Excepciones: la expresión `try...finally`)

[Exceptions: the `raise` Function](the-raise-function.md) (Excepciones: la función `raise`)

[Exceptions: the `failwith` Function](the-failwith-function.md) (Excepciones: la función `failwith`)
