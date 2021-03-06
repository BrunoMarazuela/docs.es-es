---
title: "Cómo: Implementar eventos de interfaz (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- interfaces [C#], event implementation in classes
- events [C#], in interfaces
ms.assetid: 63527447-9535-4880-8e95-35e2075827df
caps.latest.revision: "21"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: a53c6ba29837ad8827d97ea745be0462451eb145
ms.sourcegitcommit: 2142a4732bb4ff519b9817db4c24a237b9810d4b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/05/2018
---
# <a name="how-to-implement-interface-events-c-programming-guide"></a>Cómo: Implementar eventos de interfaz (Guía de programación de C#)
Un [interfaz](../../../csharp/language-reference/keywords/interface.md) puede declarar un [evento](../../../csharp/language-reference/keywords/event.md). En el siguiente ejemplo, se muestra cómo implementar eventos de interfaz en una clase. Básicamente, las reglas son las mismas que para implementar cualquier propiedad o método de interfaz.  
  
### <a name="to-implement-interface-events-in-a-class"></a>Para implementar eventos de interfaz en una clase  
  
-   Declare el evento en la clase y, después, invóquelo en las áreas apropiadas.  
  
    ```csharp
    namespace ImplementInterfaceEvents  
    {  
        public interface IDrawingObject  
        {  
            event EventHandler ShapeChanged;  
        }  
        public class MyEventArgs : EventArgs   
        {  
            // class members  
        }  
        public class Shape : IDrawingObject  
        {  
            public event EventHandler ShapeChanged;  
            void ChangeShape()  
            {  
                // Do something here before the event…  
  
                OnShapeChanged(new MyEventArgs(/*arguments*/));  
  
                // or do something here after the event.   
            }  
            protected virtual void OnShapeChanged(MyEventArgs e)  
            {  
                if(ShapeChanged != null)  
                {  
                   ShapeChanged(this, e);  
                }  
            }  
        }  
  
    }  
    ```  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo controlar la situación menos común en que la clase hereda de dos o más interfaces y cada interfaz tiene un evento con el mismo nombre. En esta situación, debe proporcionar una implementación de interfaz explícita para uno de los eventos como mínimo. Al escribir una implementación de interfaz explícita para un evento, también debe escribir los descriptores de acceso del evento `add` y `remove`. Normalmente, los proporciona el compilador, pero en este caso no es posible.  
  
 Al proporcionar sus propios descriptores de acceso, puede especificar si los dos eventos se representan mediante el mismo evento en la clase o mediante eventos diferentes. Por ejemplo, si los eventos deben provocarse en momentos diferentes según las especificaciones de la interfaz, puede asociar cada evento a una implementación distinta en su clase. En el ejemplo siguiente, los suscriptores determinan qué evento `OnDraw` recibirán al convertir la referencia de forma en `IShape` o en `IDrawingObject`.  
  
 [!code-csharp[csProgGuideEvents#10](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-implement-interface-events_1.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Eventos](../../../csharp/programming-guide/events/index.md)  
 [Delegados](../../../csharp/programming-guide/delegates/index.md)  
 [Implementación de interfaz explícita](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md)  
 [Cómo: Producir eventos de una clase base en clases derivadas](../../../csharp/programming-guide/events/how-to-raise-base-class-events-in-derived-classes.md)
