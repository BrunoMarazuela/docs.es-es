---
title: "typeof (Referencia de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "typeof"
  - "typeof_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "typeof (palabra clave) [C#]"
ms.assetid: 0c08d880-515e-46bb-8cd2-48b8dd62c08d
caps.latest.revision: 21
caps.handback.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# typeof (Referencia de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Obtenga el objeto `System.Type` para un tipo.  Una expresión `typeof` se presenta de la siguiente forma:  
  
```  
System.Type type = typeof(int);  
```  
  
## Comentarios  
 Para obtener el tipo de una expresión en tiempo de ejecución, puede utilizar el método <xref:System.Object.GetType%2A> de .NET Framework, como en el siguiente ejemplo:  
  
```  
int i = 0;  
System.Type type = i.GetType();  
```  
  
 El operador `typeof` no se puede sobrecargar.  
  
 El operador `typeof` también se puede utilizar en tipos de genéricos abiertos.  Los tipos con más de un parámetro de tipo deben tener el número adecuado de comas en la especificación.  El ejemplo siguiente muestra cómo determinar si el tipo de valor devuelto de un método es un <xref:System.Collections.Generic.IEnumerable%601> genérico.  Suponga que el método es una instancia de un tipo de MethodInfo:  
  
```  
string s = method.ReturnType.GetInterface  
    (typeof(System.Collections.Generic.IEnumerable<>).FullName);  
```  
  
## Ejemplo  
 [!code-cs[csrefKeywordsOperator#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_1.cs)]  
  
## Ejemplo  
 En este ejemplo se utiliza el método <xref:System.Object.GetType%2A> para determinar el tipo utilizado para contener el resultado de un cálculo numérico.  Esto depende de los requisitos de almacenamiento del número resultante.  
  
 [!code-cs[csrefKeywordsOperator#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_2.cs)]  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## Vea también  
 <xref:System.Type?displayProperty=fullName>   
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [is](../../../csharp/language-reference/keywords/is.md)   
 [Palabras clave de operador](../../../csharp/language-reference/keywords/operator-keywords.md)