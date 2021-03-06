---
title: "Cómo: Alinear un control con los bordes de los formularios"
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
helpviewer_keywords:
- Dock property [Windows Forms], aligning controls (using code)
- forms [Windows Forms], aligning controls
- controls [Windows Forms], aligning on forms
- custom controls [Windows Forms], docking using code
ms.assetid: 5994cb59-242b-4e75-bd0e-62879c34d702
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7979b58d52c6df7341259af50a39e104781dd148
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-align-a-control-to-the-edges-of-forms"></a>Cómo: Alinear un control con los bordes de los formularios
Puede alinear el control con el borde de los formularios estableciendo la propiedad <xref:System.Windows.Forms.Control.Dock%2A>. Esta propiedad designa el lugar en el que se encuentra el control en el formulario. La propiedad <xref:System.Windows.Forms.Control.Dock%2A> puede establecerse en los valores siguientes:  
  
|Parámetro|Efecto en el control|  
|-------------|----------------------------|  
|<xref:System.Windows.Forms.DockStyle.Bottom>|Lo acopla en la parte inferior del formulario.|  
|<xref:System.Windows.Forms.DockStyle.Fill>|Llena todo el espacio restante del formulario.|  
|<xref:System.Windows.Forms.DockStyle.Left>|Lo acopla en el lado izquierdo del formulario.|  
|<xref:System.Windows.Forms.DockStyle.None>|No lo acopla en ningún lugar y aparece en la ubicación especificada por su propiedad <xref:System.Windows.Forms.Control.Location%2A>.|  
|<xref:System.Windows.Forms.DockStyle.Right>|Lo acopla en el lado derecho del formulario.|  
|<xref:System.Windows.Forms.DockStyle.Top>|Lo acopla en la parte superior del formulario.|  
  
 Hay compatibilidad en tiempo de diseño para esta característica en Visual Studio.  
  
### <a name="to-set-the-dock-property-for-your-control-at-run-time"></a>Para establecer la propiedad Dock en su control en tiempo de ejecución  
  
1.  Establezca un valor adecuado en el código para la propiedad <xref:System.Windows.Forms.Control.Dock%2A>.  
  
    ```vb  
    ' To set the Dock property internally.  
    Me.Dock = DockStyle.Top  
    ' To set the Dock property from another object.  
    UserControl1.Dock = DockStyle.Top  
    ```  
  
    ```csharp  
    // To set the Dock property internally.  
    this.Dock = DockStyle.Top;  
    // To set the Dock property from another object.  
    UserControl1.Dock = DockStyle.Top;  
    ```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=nameWithType>  
 [Desarrollar controles personalizados de Windows Forms con .NET Framework](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 [Delimitar y acoplar controles secundarios en un control FlowLayoutPanel](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)  
 [Delimitar y acoplar controles secundarios en un control TableLayoutPanel](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 [Información general sobre la propiedad AutoSize](../../../../docs/framework/winforms/controls/autosize-property-overview.md)
