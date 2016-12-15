---
title: "Utilizar delegados (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "delegados [C#], cómo se utiliza"
ms.assetid: 99a2fc27-a32e-4a34-921c-e65497520eec
caps.latest.revision: 18
caps.handback.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Utilizar delegados (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Un [delegado](../../../csharp/language-reference/keywords/delegate.md) es un tipo que encapsula de forma segura un método, similar a un puntero de función en C y C\+\+.  A diferencia de los punteros de función de C, los delegados están orientados a objetos, proporcionan seguridad de tipos y son seguros.  El tipo de un delegado se define por el nombre del delegado.  En el ejemplo siguiente se declara un delegado denominado `Del` que puede encapsular un método que toma una [cadena](../../../csharp/language-reference/keywords/string.md) como argumento y devuelve [void](../../../csharp/language-reference/keywords/void.md):  
  
 [!code-cs[csProgGuideDelegates#21](../../../csharp/programming-guide/delegates/codesnippet/CSharp/using-delegates_1.cs)]  
  
 Normalmente, un objeto delegado se construye con el nombre del método que el delegado encapsulará o con un [método anónimo](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md).  Una vez que se crea una instancia de delegado, el delegado pasará al método una llamada de método realizada al delegado.  Los parámetros pasados al delegado por el autor de la llamada se pasan a su vez al método, y el valor devuelto desde el método, si lo hubiera, es devuelto por el delegado al autor de la llamada.  Esto se conoce como invocar al delegado.  Un delegado con instancias se puede invocar como si fuera el propio método encapsulado.  Por ejemplo:  
  
 [!code-cs[csProgGuideDelegates#22](../../../csharp/programming-guide/delegates/codesnippet/CSharp/using-delegates_2.cs)]  
  
 [!code-cs[csProgGuideDelegates#23](../../../csharp/programming-guide/delegates/codesnippet/CSharp/using-delegates_3.cs)]  
  
 Los tipos de delegado se derivan de la clase <xref:System.Delegate> en .NET Framework.  Los tipos de delegados son [sealed](../../../csharp/language-reference/keywords/sealed.md) —no se puede derivar— y no es posible derivar clases personalizadas de <xref:System.Delegate>.  Dado que el delegado con instancias es un objeto, puede pasarse como parámetro o asignarse a una propiedad.  De este modo, un método puede aceptar un delegado como parámetro y llamar al delegado en algún momento posterior.  Esto se conoce como devolución de llamada asincrónica y es un método común para notificar a un llamador que un proceso largo ha finalizado.  Cuando se utiliza un delegado de esta manera, el código que usa al delegado no necesita ningún conocimiento de la implementación del método empleado.  La funcionalidad es similar a la encapsulación que proporcionan las interfaces.  
  
 Otro uso común de devoluciones de llamada es definir un método de comparación personalizado y pasar ese delegado a un método de ordenación.  Permite que el código del llamador se convierta en parte del algoritmo de ordenación.  En el siguiente método de ejemplo se usa el tipo `Del` como parámetro:  
  
 [!code-cs[csProgGuideDelegates#24](../../../csharp/programming-guide/delegates/codesnippet/CSharp/using-delegates_4.cs)]  
  
 Luego puede pasar el delegado creado anteriormente a ese método:  
  
 [!code-cs[csProgGuideDelegates#25](../../../csharp/programming-guide/delegates/codesnippet/CSharp/using-delegates_5.cs)]  
  
 Y recibir los siguientes resultados en la consola:  
  
 `The number is: 3`  
  
 Si se usa el delegado como abstracción, no es necesario que `MethodWithCallback` llame directamente a la consola —no tiene que estar diseñado pensando en una consola—.  Lo que `MethodWithCallback` hace es simplemente preparar una cadena y pasarla a otro método.  Esto es especialmente eficaz, puesto que un método delegado puede utilizar cualquier número de parámetros.  
  
 Cuando se crea un delegado para encapsular un método de instancia, el delegado hace referencia tanto a la instancia como al método.  Un delegado no tiene conocimiento del tipo de instancia —aparte del método al que encapsula—, por lo que un delegado puede hacer referencia a cualquier tipo de objeto siempre que haya un método en ese objeto que coincida con la signatura del delegado.  Cuando se crea un delegado para encapsular un método estático, solo hace referencia al método.  Considere las siguientes declaraciones:  
  
 [!code-cs[csProgGuideDelegates#26](../../../csharp/programming-guide/delegates/codesnippet/CSharp/using-delegates_6.cs)]  
  
 Junto con el `DelegateMethod` estático mostrado anteriormente, ahora tenemos tres métodos que se pueden encapsularse mediante una instancia de `Del`.  
  
 Un delegado puede llamar a más de un método cuando se invoca.  Esto se conoce como multidifusión.  Para agregar un método adicional a la lista de métodos del delegado —la lista de invocación—, simplemente es necesario agregar dos delegados mediante los operadores de adición o asignación y suma \('\+' o '\+\='\).  Por ejemplo:  
  
 [!code-cs[csProgGuideDelegates#27](../../../csharp/programming-guide/delegates/codesnippet/CSharp/using-delegates_7.cs)]  
  
 En este momento `allMethodsDelegate` contiene tres métodos en su lista de invocación: `Method1`, `Method2` y `DelegateMethod`.  Los tres delegados originales, `d1`, `d2` y `d3`, permanecen sin cambios.  Cuando se invoca `allMethodsDelegate`, todos los métodos se llaman en orden.  Si el delegado usa parámetros de referencia, la referencia se pasa secuencialmente a cada uno de los tres métodos por turnos, y cualquier cambio que realice un método es visible para el siguiente método.  Cuando alguno de los métodos produce una excepción que no se captura dentro del método, esa excepción se pasa al llamador del delegado y no se llama a los métodos siguientes de la lista de invocación.  Si el delegado tiene un valor devuelto o los parámetros de salida, devuelve el valor devuelto y los parámetros del último método invocado.  Para quitar un método de la lista de invocación, utilice el operador de decremento o el operador de asignación de decremento \('\-' o '\-\= '\).  Por ejemplo:  
  
 [!code-cs[csProgGuideDelegates#28](../../../csharp/programming-guide/delegates/codesnippet/CSharp/using-delegates_8.cs)]  
  
 Dado que los tipos de delegado se derivan de `System.Delegate`, los métodos y propiedades definidas por esa clase se pueden llamar en el delegado.  Por ejemplo, para buscar el número de métodos en la lista de invocación de un delegado, se puede escribir:  
  
 [!code-cs[csProgGuideDelegates#29](../../../csharp/programming-guide/delegates/codesnippet/CSharp/using-delegates_9.cs)]  
  
 Los delegados con más de un método en su lista de invocación derivan de <xref:System.MulticastDelegate>, que es una subclase de `System.Delegate`.  El código anterior funciona en ambos casos porque las dos clases admiten `GetInvocationList`.  
  
 Los delegados de multidifusión se utilizan mucho en el control de eventos.  Los objetos de origen de evento envían notificaciones de evento a los objetos de destinatario que se han registrado para recibir ese evento.  Para suscribirse a un evento, el destinatario crea un método diseñado para controlar el evento; a continuación, crea a un delegado para dicho método y pasa el delegado al origen de eventos.  El origen llama al delegado cuando se produce el evento.  Después, el delegado llama al método que controla los eventos en el destinatario y entrega los datos del evento.  El origen del evento define el tipo de delegado para un evento determinado.  Para más información, vea [Eventos](../../../csharp/programming-guide/events/index.md).  
  
 La comparación de delegados de dos tipos distintos asignados en tiempo de compilación generará un error de compilación.  Si las instancias de delegado son estáticamente del tipo `System.Delegate`, entonces se permite la comparación, pero devolverá false en tiempo de ejecución.  Por ejemplo:  
  
 [!code-cs[csProgGuideDelegates#30](../../../csharp/programming-guide/delegates/codesnippet/CSharp/using-delegates_10.cs)]  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Delegados](../../../csharp/programming-guide/delegates/index.md)   
 [Usar varianza en delegados](../Topic/Using%20Variance%20in%20Delegates%20\(C%23%20and%20Visual%20Basic\).md)   
 [Varianza en delegados](../Topic/Variance%20in%20Delegates%20\(C%23%20and%20Visual%20Basic\).md)   
 [Usar la varianza para los delegados genéricos Func y Action](../Topic/Using%20Variance%20for%20Func%20and%20Action%20Generic%20Delegates%20\(C%23%20and%20Visual%20Basic\).md)   
 [Eventos](../../../csharp/programming-guide/events/index.md)