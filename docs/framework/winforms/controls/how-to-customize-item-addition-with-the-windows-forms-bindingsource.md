---
title: "Cómo: Personalizar la forma de agregar elementos con el control BindingSource de formularios Windows Forms"
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
- controls [Windows Forms], creating new items
- BindingSource component [Windows Forms], customizing item addition with
- examples [Windows Forms], BindingSource component
- BindingSource component [Windows Forms], examples
ms.assetid: 1aae11fc-6fb2-4cb9-b3d0-e0638fe77ef0
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 807aa16e4d70a105bcd2fb1426a94d6fdcebbf31
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-customize-item-addition-with-the-windows-forms-bindingsource"></a>Cómo: Personalizar la forma de agregar elementos con el control BindingSource de formularios Windows Forms
Al usar un componente <xref:System.Windows.Forms.BindingSource> para enlazar un control de Windows Forms a un origen de datos, quizá necesite personalizar la creación de nuevos elementos. Para facilitar este proceso, el componente <xref:System.Windows.Forms.BindingSource> proporciona el evento <xref:System.Windows.Forms.BindingSource.AddingNew> , que normalmente se produce cuando el control enlazado necesita crear un nuevo elemento. El controlador de eventos puede proporcionar el comportamiento personalizado necesario (por ejemplo, llamar a un método en un servicio Web u obtener un nuevo objeto de un generador de clases).  
  
> [!NOTE]
>  Cuando se agrega un elemento controlando el evento <xref:System.Windows.Forms.BindingSource.AddingNew> , no se puede cancelar la adición.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra cómo enlazar un control <xref:System.Windows.Forms.DataGridView> a un generador de clases mediante un componente <xref:System.Windows.Forms.BindingSource> . Cuando el usuario hace clic en la nueva fila del control <xref:System.Windows.Forms.DataGridView> , se produce el evento <xref:System.Windows.Forms.BindingSource.AddingNew> . El controlador de eventos crea un nuevo objeto `DemoCustomer`, que se asigna a la propiedad <xref:System.ComponentModel.AddingNewEventArgs.NewObject%2A?displayProperty=nameWithType>. Esto hace que el nuevo objeto se agregue `DemoCustomer` a la lista del componente <xref:System.Windows.Forms.BindingSource> y que se muestre en la nueva fila del control <xref:System.Windows.Forms.DataGridView> .  
  
 [!code-cpp[System.Windows.Forms.DataConnector.AddingNew#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.AddingNew/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnector.AddingNew#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.AddingNew/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.AddingNew#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.AddingNew/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los ensamblados System, System.Data, System.Drawing y System.Windows.Forms.  
  
 Para información sobre cómo compilar este ejemplo desde la línea de comandos para [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] o [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], consulte [Compilación desde la línea de comandos](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [Compilar desde la línea de comandos con csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). También puede compilar este ejemplo en [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] pegando el código en un nuevo proyecto.  Consulte también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.BindingNavigator>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 [Componente BindingSource](../../../../docs/framework/winforms/controls/bindingsource-component.md)  
 [Cómo: Enlazar un control de Windows Forms a un tipo](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)
