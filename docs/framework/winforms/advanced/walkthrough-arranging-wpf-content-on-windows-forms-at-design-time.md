---
title: "Tutorial: Organizar el contenido de WPF en Windows Forms en tiempo de diseño"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WPF user control [Windows Forms], hosting in a layout panel
- WPF content [Windows Forms], arranging at design time
- Windows Forms, arranging WPF content at design time
- WPF content [Windows Forms], hosting in Windows Forms
- Windows Forms, anchoring and docking WPF content
- interoperability [WPF]
ms.assetid: 5efb1c53-1484-43d6-aa8a-f4861b99bb8a
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: afde62d07c009de4612aa44ebbd81b5a71ef36e5
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="walkthrough-arranging-wpf-content-on-windows-forms-at-design-time"></a>Tutorial: Organizar el contenido de WPF en Windows Forms en tiempo de diseño
Este tutorial muestra cómo usar las características de diseño de Windows Forms, como la delimitación y las líneas de ajuste, para organizar los controles de Windows Presentation Foundation (WPF).  
  
 En este tutorial, realizará las tareas siguientes:  
  
-   Crear el proyecto.  
  
-   Crear el control WPF.  
  
-   Hospedar controles WPF en un panel de diseño.  
  
-   Usar líneas de ajuste para alinear os controles WPF.  
  
-   Delimitar y acoplar controles WPF.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Necesita los componentes siguientes para completar este tutorial:  
  
-   [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)].  
  
## <a name="creating-the-project"></a>Crear el proyecto  
 El primer paso es crear el proyecto de Windows Forms.  
  
> [!NOTE]
>  Al hospedar contenido de WPF, solo se admiten proyectos de C# y Visual Basic.  
  
#### <a name="to-create-the-project"></a>Para crear el proyecto  
  
-   Crear un nuevo proyecto de aplicación de Windows Forms en Visual Basic o Visual C# llamado `ArrangeElementHost`.  
  
## <a name="creating-the-wpf-control"></a>Crear el control WPF  
 Después de agregar un control WPF al proyecto, puede organizarlo en el formulario.  
  
#### <a name="to-create-wpf-controls"></a>Para crear controles WPF  
  
1.  Agregue un nuevo <xref:System.Windows.Controls.UserControl> WPF al proyecto. Use el nombre predeterminado del tipo de control, `UserControl1.xaml`. Para obtener más información, consulte [Tutorial: crear nuevo WPF contenido en Windows Forms en tiempo de diseño](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).  
  
2.  En la vista Diseño, asegúrese de que `UserControl1` está seleccionado. Para obtener más información, consulte [Cómo: seleccionar y mover elementos en la superficie de diseño](http://msdn.microsoft.com/library/54cb70b6-b35b-46e4-a0cc-65189399c474).  
  
3.  En el **propiedades** ventana, establezca el valor de la <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> propiedades para `200`.  
  
4.  Establezca el valor de la propiedad <xref:System.Windows.Controls.Control.Background%2A> en `Blue`.  
  
5.  Compile el proyecto.  
  
## <a name="hosting-wpf-controls-in-a-layout-panel"></a>Hospedar controles WPF en un panel de diseño  
 Puede usar controles WPF en paneles de diseño de la misma forma que usa otros controles de Windows Forms.  
  
#### <a name="to-host-wpf-controls-in-a-layout-panel"></a>Para hospedar controles WPF en un panel de diseño  
  
1.  Abra `Form1` en el Diseñador de Windows Forms.  
  
2.  En el **cuadro de herramientas**, arrastre un <xref:System.Windows.Forms.TableLayoutPanel> al formulario.  
  
3.  En el <xref:System.Windows.Forms.TableLayoutPanel> panel de etiquetas inteligentes del control, seleccione **quitar la última fila**.  
  
4.  Cambie el tamaño del control <xref:System.Windows.Forms.TableLayoutPanel> a un ancho y alto mayor.  
  
5.  En el **cuadro de herramientas**, haga doble clic en `UserControl1` para crear una instancia de `UserControl1` en la primera celda de la <xref:System.Windows.Forms.TableLayoutPanel> control.  
  
     La instancia de `UserControl1` se hospeda en un nuevo control <xref:System.Windows.Forms.Integration.ElementHost> llamado `elementHost1`.  
  
6.  En el **cuadro de herramientas**, haga doble clic en `UserControl1` para crear otra instancia de la segunda celda de la <xref:System.Windows.Forms.TableLayoutPanel> control.  
  
7.  En el **esquema del documento** ventana, seleccione `tableLayoutPanel1`. Para obtener más información, consulte [ventana Esquema del documento](http://msdn.microsoft.com/library/9054f2bc-f6f8-4242-9fe0-be71089b12f8).  
  
8.  En el **propiedades** ventana, establezca el valor de la <xref:System.Windows.Forms.Control.Padding%2A> propiedad `10, 10, 10, 10`.  
  
     Ambos controles <xref:System.Windows.Forms.Integration.ElementHost> cambian de tamaño para ajustarse al nuevo diseño.  
  
## <a name="using-snaplines-to-align-wpf-controls"></a>Usar líneas de ajuste para alinear controles WPF  
 Las líneas de ajuste permiten alinear fácilmente los controles en un formulario. Puede usar líneas de ajuste para alinear también controles WPF. Para obtener más información, consulte [Tutorial: organizar controles en Windows Forms usando las guías de alineación](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).  
  
#### <a name="to-use-snaplines-to-align-wpf-controls"></a>Para usar líneas de ajuste para alinear controles WPF  
  
1.  Desde el **cuadro de herramientas**, arrastre una instancia de `UserControl1` hasta el formulario y lo coloca en el espacio debajo el <xref:System.Windows.Forms.TableLayoutPanel> control.  
  
     La instancia de `UserControl1` se hospeda en un nuevo control <xref:System.Windows.Forms.Integration.ElementHost> llamado `elementHost3`.  
  
2.  Use las líneas de ajuste para alinear el borde izquierdo de `elementHost3` con el borde izquierdo del control <xref:System.Windows.Forms.TableLayoutPanel>.  
  
3.  Use las líneas de ajuste para ajustar el tamaño de `elementHost3` al mismo ancho que el control <xref:System.Windows.Forms.TableLayoutPanel>.  
  
4.  Mueva `elementHost3` hacia el control <xref:System.Windows.Forms.TableLayoutPanel> hasta que aparezca una línea de ajuste central entre los controles.  
  
5.  En el **propiedades** ventana, establezca el valor de la propiedad Margin en `20, 20, 20, 20`.  
  
6.  Aleje `elementHost3` del control <xref:System.Windows.Forms.TableLayoutPanel> hasta que la línea de ajuste central aparezca de nuevo. Ahora, la línea de ajuste central indica un margen de 20.  
  
7.  Mueva `elementHost3` hacia la derecha, hasta que su borde izquierdo quede alineado con el borde izquierdo de `elementHost1`.  
  
8.  Cambie el ancho de `elementHost3` hasta que su borde derecho quede alineado con el borde derecho de `elementHost2`.  
  
## <a name="anchoring-and-docking-wpf-controls"></a>Delimitar y acoplar controles WPF  
 La delimitación y el acoplamiento de un control WPF hospedado en un formulario se comportan igual que los de otros controles de Windows Forms.  
  
#### <a name="to-anchor-and-dock-wpf-controls"></a>Para delimitar y acoplar controles WPF  
  
1.  Seleccione `elementHost1`.  
  
2.  En el **propiedades** ventana, establezca el <xref:System.Windows.Forms.Control.Anchor%2A> propiedad **superior, inferior, izquierda, derecha**.  
  
3.  Cambie el tamaño del control <xref:System.Windows.Forms.TableLayoutPanel> a un tamaño mayor.  
  
     El control `elementHost1` cambia de tamaño para llenar la celda.  
  
4.  Seleccione `elementHost2`.  
  
5.  En el **propiedades** ventana, establezca el valor de la <xref:System.Windows.Forms.Control.Dock%2A> propiedad <xref:System.Windows.Forms.DockStyle.Fill>.  
  
     El control `elementHost2` cambia de tamaño para llenar la celda.  
  
6.  Seleccione el control <xref:System.Windows.Forms.TableLayoutPanel>.  
  
7.  Establezca el valor de su propiedad <xref:System.Windows.Forms.Control.Dock%2A> en <xref:System.Windows.Forms.DockStyle.Top>.  
  
8.  Seleccione `elementHost3`.  
  
9. Establezca el valor de su propiedad <xref:System.Windows.Forms.Control.Dock%2A> en <xref:System.Windows.Forms.DockStyle.Fill>.  
  
     El control `elementHost3` cambia de tamaño para llenar el espacio restante en el formulario.  
  
10. Cambie de tamaño el formulario.  
  
     Los tres controles <xref:System.Windows.Forms.Integration.ElementHost> ajustan su tamaño correctamente.  
  
     Para obtener más información, consulte [Cómo: delimitador y acoplar controles secundarios en un TableLayoutPanel Control](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [Delimitar y acoplar controles secundarios en un control TableLayoutPanel](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 [Cómo: Alinear un control con los bordes de los formularios en tiempo de diseño](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)  
 [Tutorial: Organizar controles en formularios Windows Forms mediante líneas de ajuste](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)  
 [Migración e interoperabilidad](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [Utilizar controles WPF](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [WPF Designer](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)
