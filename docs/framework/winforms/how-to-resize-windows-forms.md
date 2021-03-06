---
title: "Cómo: Cambiar el tamaño de los formularios Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- resizing Windows Forms
- Windows Forms, resizing
ms.assetid: 5d9dd47e-e68c-48c9-a0a3-a9ff34ba009d
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cc2e9f81094d16030dbe4595a8132569edab782a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-resize-windows-forms"></a>Cómo: Cambiar el tamaño de los formularios Windows Forms
Puede especificar el tamaño de su Windows Form de varias maneras. Puede cambiar el alto y el ancho del formulario mediante programación estableciendo un nuevo valor para la propiedad <xref:System.Windows.Forms.Form.Size%2A>, o ajustar las propiedades <xref:System.Windows.Forms.Control.Height%2A> o <xref:System.Windows.Forms.Control.Width%2A> individualmente. Si usa [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], puede cambiar el tamaño mediante el Diseñador de Windows Forms. Consulte también [Cómo: cambiar el tamaño de Windows Forms mediante el diseñador](http://msdn.microsoft.com/library/37k2zkwx\(v=vs.110\)).  
  
### <a name="to-resize-a-form-programmatically"></a>Para cambiar el tamaño de un formulario mediante programación  
  
-   Para definir el tamaño de un formulario en tiempo de ejecución, establezca la propiedad <xref:System.Windows.Forms.Form.Size%2A> del formulario.  
  
     En el ejemplo de código siguiente se muestra el tamaño del formulario establecido en 100 x 100 píxeles.  
  
    ```vb  
    Form1.Size = New System.Drawing.Size(100, 100)  
    ```  
  
    ```csharp  
    Form1.Size = new System.Drawing.Size(100, 100);  
    ```  
  
    ```cpp  
    Form1->Size = System::Drawing::Size(100, 100);  
    ```  
  
### <a name="to-change-form-width-and-height-programmatically"></a>Para cambiar el alto y ancho del formulario mediante programación  
  
-   Después de definir <xref:System.Windows.Forms.Form.Size%2A>, cambie el alto o el ancho del formulario usando las propiedades <xref:System.Windows.Forms.Control.Width%2A> o <xref:System.Windows.Forms.Control.Height%2A>.  
  
     En el ejemplo de código siguiente se muestra el ancho del formulario establecido en 300 píxeles desde el borde izquierdo del formulario, mientras que el alto permanece constante.  
  
    ```vb  
    Form1.Width = 300  
    ```  
  
    ```csharp  
    Form1.Width = 300;  
    ```  
  
    ```cpp  
    Form1->Width = 300;  
    ```  
  
     O bien  
  
     Cambie <xref:System.Drawing.Size.Width%2A> o <xref:System.Drawing.Size.Height%2A> estableciendo la propiedad <xref:System.Windows.Forms.Form.Size%2A>.  
  
     Sin embargo, tal y como se muestra en el ejemplo de código siguiente, este enfoque es más complejo que simplemente establecer las propiedades <xref:System.Windows.Forms.Control.Width%2A> o <xref:System.Windows.Forms.Control.Height%2A>.  
  
    ```vb  
    Form1.Size = New Size(300, Form1.Size.Height)  
    ```  
  
    ```csharp  
    Form1.Size = new Size(300, Form1.Size.Height);  
    ```  
  
    ```cpp  
    Form1->Size = System::Drawing::Size(300, Form1->Size.Height);  
    ```  
  
### <a name="to-change-form-size-by-increments-programmatically"></a>Para cambiar el tamaño del formulario por incrementos mediante programación  
  
-   Para incrementar el tamaño del formulario, establezca las propiedades <xref:System.Drawing.Size.Width%2A> y <xref:System.Drawing.Size.Height%2A>.  
  
     En el ejemplo de código siguiente se muestra el ancho del formulario establecido en 200 píxeles más que la configuración actual.  
  
    ```vb  
    Form1.Width += 200  
    ```  
  
    ```csharp  
    Form1.Width += 200;  
    ```  
  
    ```cpp  
    Form1->Width += 200;  
    ```  
  
    > [!CAUTION]
    >  Use siempre la propiedad <xref:System.Drawing.Size.Height%2A> o <xref:System.Drawing.Size.Width%2A> para cambiar una dimensión de un formulario, a menos que quiera establecer las dimensiones de alto y ancho al mismo tiempo estableciendo la propiedad <xref:System.Windows.Forms.Form.Size%2A> en una nueva estructura <xref:System.Drawing.Size>. La propiedad <xref:System.Windows.Forms.Form.Size%2A> devuelve una estructura <xref:System.Drawing.Size>, que es un tipo de valor. No se puede asignar un nuevo valor a la propiedad de un tipo de valor. Por lo tanto, el ejemplo de código siguiente no se compilará.  
  
    ```vb  
    ' NOTE: CODE WILL NOT COMPILE  
    Dim f As New Form()  
    f.Size.Width += 100  
    ```  
  
    ```csharp  
    // NOTE: CODE WILL NOT COMPILE  
    Form f = new Form();  
    f.Size.Width += 100;  
    ```  
  
    ```cpp  
    // NOTE: CODE WILL NOT COMPILE  
    Form^ f = gcnew Form();  
    f->Size->X += 100;  
    ```  
  
## <a name="see-also"></a>Vea también  
 [Introducción a los formularios Windows Forms](../../../docs/framework/winforms/getting-started-with-windows-forms.md)  
 [Mejorar las aplicaciones de Windows Forms](../../../docs/framework/winforms/advanced/index.md)
