---
title: Usar varianza en delegados (C#) | Microsoft Docs
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 1638c95d-dc8b-40c1-972c-c2dcf84be55e
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: fbcf08eafe05e3299379b0455640fc08ec80e0ca
ms.lasthandoff: 03/13/2017

---
# <a name="using-variance-in-delegates-c"></a>Usar varianza en delegados (C#)
Al asignar un método a un delegado, la *covarianza* y la *contravarianza* proporcionan flexibilidad para hacer coincidir un tipo de delegado con una firma de método. La covarianza permite que un método tenga un tipo de valor devuelto más derivado que el definido en el delegado. La contravarianza permite un método que tiene tipos de parámetro menos derivados que los del tipo de delegado.  
  
## <a name="example-1-covariance"></a>Ejemplo 1: covarianza  
  
### <a name="description"></a>Descripción  
 En este ejemplo se muestra cómo se pueden usar delegados con métodos que tienen tipos de valor devuelto derivados del tipo de valor devuelto en la firma del delegado. El tipo de datos devuelto por `DogsHandler` es de tipo `Dogs`, que se deriva del tipo `Mammals` definido en el delegado.  
  
### <a name="code"></a>Código  
  
```csharp  
class Mammals{}  
class Dogs : Mammals{}  
  
class Program  
{  
    // Define the delegate.  
    public delegate Mammals HandlerMethod();  
  
    public static Mammals MammalsHandler()  
    {  
        return null;  
    }  
  
    public static Dogs DogsHandler()  
    {  
        return null;  
    }  
  
    static void Test()  
    {  
        HandlerMethod handlerMammals = MammalsHandler;  
  
        // Covariance enables this assignment.  
        HandlerMethod handlerDogs = DogsHandler;  
    }  
}  
```  
  
## <a name="example-2-contravariance"></a>Ejemplo 2: contravarianza  
  
### <a name="description"></a>Descripción  
 En este ejemplo se muestra cómo se pueden usar delegados con métodos que tienen parámetros de un tipo que son tipos base del tipo de parámetro de la firma del delegado. Con la contravarianza, puede usar un controlador de eventos en lugar de controladores independientes. Por ejemplo, puede crear un controlador de eventos que acepta un parámetro de entrada `EventArgs` y usarlo con un evento `Button.MouseClick` que envía un tipo `MouseEventArgs` como parámetro, pero también con un evento `TextBox.KeyDown` que envía un parámetro `KeyEventArgs`.  
  
### <a name="code"></a>Código  
  
```csharp  
// Event hander that accepts a parameter of the EventArgs type.  
private void MultiHandler(object sender, System.EventArgs e)  
{  
    label1.Text = System.DateTime.Now.ToString();  
}  
  
public Form1()  
{  
    InitializeComponent();  
  
    // You can use a method that has an EventArgs parameter,  
    // although the event expects the KeyEventArgs parameter.  
    this.button1.KeyDown += this.MultiHandler;  
  
    // You can use the same method   
    // for an event that expects the MouseEventArgs parameter.  
    this.button1.MouseClick += this.MultiHandler;  
  
}  
```  
  
## <a name="see-also"></a>Vea también  
 [Varianza en delegados (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)   
 [Usar varianza para los delegados genéricos Func y Action (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)