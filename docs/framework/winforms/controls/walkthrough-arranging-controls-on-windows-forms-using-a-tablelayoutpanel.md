---
title: 'Tutorial: Organizar controles en formularios Windows Forms mediante TableLayoutPanel'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [Windows Forms], arranging with TableLayoutPanel
- TableLayoutPanel control [Windows Forms], walkthroughs
- Windows Forms controls, arranging
ms.assetid: d474885e-12cc-4ab7-b997-2a23a643049b
caps.latest.revision: "28"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9636585fe9671b8822a6510d405eef5e6f23527e
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel"></a>Tutorial: Organizar controles en formularios Windows Forms mediante TableLayoutPanel
Algunas aplicaciones requieren un formulario con un diseño que se organice de manera adecuada y automática a medida que el formulario o el contenido cambien de tamaño. Si necesita un diseño dinámico y no desea controlar los eventos <xref:System.Windows.Forms.Control.Layout> de forma explícita en el código, considere la posibilidad de usar un panel de diseño.  
  
 El control <xref:System.Windows.Forms.FlowLayoutPanel> y el control <xref:System.Windows.Forms.TableLayoutPanel> proporcionan formas intuitivas para organizar los controles en el formulario. Ambos proporcionan una capacidad automática y configurable para controlar las posiciones relativas de los controles secundarios que contienen, y ambos ofrecen características de diseño dinámico en tiempo de ejecución, lo que permite cambiar el tamaño y la posición de los controles secundarios a medida que las dimensiones del formulario primario cambian. Los paneles de diseño se pueden anidar dentro de paneles de diseño para habilitar la creación de interfaces de usuario sofisticadas.  
  
 El control <xref:System.Windows.Forms.FlowLayoutPanel> organiza su contenido en una dirección de flujo específica: horizontal o vertical. Su contenido puede ajustarse desde una fila a la siguiente o desde una columna a la siguiente. Además, el contenido puede recortarse en lugar de ajustarse. Para obtener más información, consulte [Tutorial: organizar controles en Windows Forms mediante FlowLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md).  
  
 El <xref:System.Windows.Forms.TableLayoutPanel> organiza su contenido en una cuadrícula, proporcionando una funcionalidad similar en el código HTML \<tabla > elemento. El <xref:System.Windows.Forms.TableLayoutPanel> control le permite colocar los controles en un diseño de cuadrícula sin necesidad de especificar con precisión la posición de cada control individual. Las celdas se organizan en filas y columnas, y pueden tener distintos tamaños. Pueden combinar celdas en filas y columnas. Las celdas pueden contener cualquier elemento puede contener y se comportan de la mayoría de los demás aspectos como contenedores de un formulario.  
  
 El <xref:System.Windows.Forms.TableLayoutPanel> control también proporciona una funcionalidad de cambio de tamaño proporcional en tiempo de ejecución, por lo que su diseño puede cambiar fácilmente cuando se cambia el tamaño del formulario. Esto hace que el <xref:System.Windows.Forms.TableLayoutPanel> control idónea para propósitos tales como formularios de entrada de datos y aplicaciones localizadas. Para obtener más información, consulte [Tutorial: crear un formulario de Windows puede cambiar el tamaño de entrada de datos](http://msdn.microsoft.com/library/e193b4fc-912a-4917-b036-b76c7a6f58ab) y [Tutorial: crear un formulario de Windows Localizable](http://msdn.microsoft.com/library/c5240b6e-aaca-4286-9bae-778a416edb9c).  
  
 En general, no debe usar un <xref:System.Windows.Forms.TableLayoutPanel> control como un contenedor para todo el diseño. Use <xref:System.Windows.Forms.TableLayoutPanel> controles para proporcionar capacidades de cambio de tamaño proporcionales a las partes del diseño.  
  
 Las tareas ilustradas en este tutorial incluyen:  
  
-   Crear un proyecto de Windows Forms  
  
-   Organizar controles en filas y columnas  
  
-   Propiedades de columna y fila de valores  
  
-   Abarcar filas y columnas con un Control  
  
-   Control automático de desbordamientos  
  
-   Insertar controles mediante un doble clic en estos en el cuadro de herramientas  
  
-   Insertar un control dibujando su contorno  
  
-   Reasignar controles existentes en un elemento primario diferente  
  
 Cuando termine, comprenderá el rol de estas importantes características de diseño.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="creating-the-project"></a>Crear el proyecto  
 El primer paso es crear el proyecto y configurar el formulario.  
  
#### <a name="to-create-the-project"></a>Para crear el proyecto  
  
1.  Cree un proyecto de aplicación de Windows denominado "TableLayoutPanelExample". Para obtener más información, consulte [Cómo: crear un proyecto de aplicación de Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) .  
  
2.  Seleccione el formulario en el **Windows** **Diseñador de formularios**.  
  
## <a name="arranging-controls-in-rows-and-columns"></a>Organizar controles en filas y columnas  
 El <xref:System.Windows.Forms.TableLayoutPanel> control le permite organizar fácilmente los controles en filas y columnas.  
  
#### <a name="to-arrange-controls-in-rows-and-columns-using-a-tablelayoutpanel"></a>Para organizar los controles en filas y columnas mediante TableLayoutPanel  
  
1.  Arrastre un <xref:System.Windows.Forms.TableLayoutPanel> controlar desde la **cuadro de herramientas** al formulario. Tenga en cuenta que, de forma predeterminada, el <xref:System.Windows.Forms.TableLayoutPanel> control tiene cuatro celdas.  
  
2.  Arrastre un <xref:System.Windows.Forms.Button> controlar desde la **cuadro de herramientas** en el <xref:System.Windows.Forms.TableLayoutPanel> controlar y colóquelo en una de las celdas. Tenga en cuenta que el <xref:System.Windows.Forms.Button> control se crea dentro de la celda seleccionada.  
  
3.  Arrastre tres más <xref:System.Windows.Forms.Button> controla desde el **cuadro de herramientas** en el <xref:System.Windows.Forms.TableLayoutPanel> control, de modo que cada celda contiene un botón.  
  
4.  Arrastrar el controlador de tamaño vertical entre las dos columnas y muévalo a la izquierda. Tenga en cuenta que la <xref:System.Windows.Forms.Button> controles de la primera columna se cambia el tamaño a un ancho menor, al tamaño de la <xref:System.Windows.Forms.Button> controles en la segunda columna se ha modificado.  
  
5.  Arrastrar el controlador de tamaño vertical entre las dos columnas y muévalo a la derecha. Tenga en cuenta que la <xref:System.Windows.Forms.Button> controles de la primera columna se devuelven a su tamaño original, mientras el <xref:System.Windows.Forms.Button> controles en la segunda columna se mueven a la derecha.  
  
6.  Mueva el controlador de tamaño horizontal hacia arriba y hacia abajo para ver el efecto en los controles en el panel.  
  
## <a name="positioning-controls-within-cells-using-docking-and-anchoring"></a>Colocar controles en celdas mediante el acoplamiento y delimitación  
 El comportamiento de anclaje de controles secundarios en un <xref:System.Windows.Forms.TableLayoutPanel> difiere del comportamiento de otros controles contenedor. El comportamiento de acoplamiento de los controles secundarios es igual que otros controles contenedor.  
  
#### <a name="positioning-controls-within-cells"></a>Colocar controles en celdas  
  
1.  Seleccione la primera <xref:System.Windows.Forms.Button> control. Cambie el valor de su propiedad <xref:System.Windows.Forms.Control.Dock%2A> a <xref:System.Windows.Forms.DockStyle.Fill>. Tenga en cuenta que el <xref:System.Windows.Forms.Button> control se expande para rellenar la celda.  
  
2.  Seleccione uno de los otros <xref:System.Windows.Forms.Button> controles. Cambie el valor de su propiedad <xref:System.Windows.Forms.Control.Anchor%2A> a <xref:System.Windows.Forms.AnchorStyles.Right>. Tenga en cuenta que se mueve para que su borde derecho esté cerca del borde derecho de la celda. La distancia entre los bordes es la suma de la <xref:System.Windows.Forms.Button> del control <xref:System.Windows.Forms.Control.Margin%2A> propiedad y el panel <xref:System.Windows.Forms.Control.Padding%2A> propiedad.  
  
3.  Cambie el valor de la <xref:System.Windows.Forms.Button> del control <xref:System.Windows.Forms.Control.Anchor%2A> propiedad <xref:System.Windows.Forms.AnchorStyles.Right> y <xref:System.Windows.Forms.AnchorStyles.Left>. Tenga en cuenta que el control de tamaño se ajusta el ancho de la celda, con el <xref:System.Windows.Forms.Control.Margin%2A> y <xref:System.Windows.Forms.Control.Padding%2A> valores tomados en consideración.  
  
4.  Repita los pasos 2 y 3 con el <xref:System.Windows.Forms.AnchorStyles.Top> y <xref:System.Windows.Forms.AnchorStyles.Bottom> estilos.  
  
## <a name="setting-row-and-column-properties"></a>Propiedades de columna y fila de valores  
 Puede establecer las propiedades individuales de filas y columnas mediante el <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A> y <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> colecciones.  
  
#### <a name="to-set-row-and-column-properties"></a>Para establecer las propiedades de columna y fila  
  
1.  Seleccione el <xref:System.Windows.Forms.TableLayoutPanel> controlar en el **Diseñador de Windows Forms**.  
  
2.  En el **propiedades** windows, abra la <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> colección haciendo clic en el botón de puntos suspensivos (![de pantalla de VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) botón junto a la **columnas** entrada.  
  
3.  Seleccione la primera columna y cambie el valor de su <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> propiedad <xref:System.Windows.Forms.SizeType.AutoSize>. Haga clic en **Aceptar** para aceptar el cambio. Tenga en cuenta que el ancho de la primera columna se reduce para ajustarse a la <xref:System.Windows.Forms.Button> control. Tenga en cuenta también que el ancho de la columna no es de tamaño variable.  
  
4.  En el **propiedades** ventana, abra el <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> colección y seleccione la primera columna. Cambie el valor de su <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> propiedad <xref:System.Windows.Forms.SizeType.Percent>. Haga clic en **Aceptar** para aceptar el cambio. Cambiar el tamaño de la <xref:System.Windows.Forms.TableLayoutPanel> el control a un ancho mayor y observe que el ancho de la primera columna se expande. Cambiar el tamaño de la <xref:System.Windows.Forms.TableLayoutPanel> el control a un ancho menor y tenga en cuenta que los botones de la primera columna se ajusta el tamaño para ajustarse a la celda. Tenga en cuenta también que el ancho de la columna es de tamaño variable.  
  
5.  En el **propiedades** ventana, abra el <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> colección y seleccione todas las columnas enumeradas. Establezca el valor de cada <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> propiedad <xref:System.Windows.Forms.SizeType.Percent>. Haga clic en **Aceptar** para aceptar el cambio. Repita el proceso con el <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A> colección.  
  
6.  Tome uno de los controladores de tamaño de esquina y cambiar el tamaño el ancho y el alto de la <xref:System.Windows.Forms.TableLayoutPanel> control. Tenga en cuenta que se cambia el tamaño de las filas y columnas como el <xref:System.Windows.Forms.TableLayoutPanel> cambios de tamaño del control. También observe que las filas y columnas se puede cambiar el tamaño horizontal y vertical de controladores de tamaño.  
  
## <a name="spanning-rows-and-columns-with-a-control"></a>Abarcar filas y columnas con un Control  
 El <xref:System.Windows.Forms.TableLayoutPanel> control agrega varias nuevas propiedades a los controles en tiempo de diseño. Dos de estas propiedades son `RowSpan` y `ColumnSpan`. Puede usar estas propiedades para realizar un control abarque más de una fila o columna.  
  
#### <a name="to-span-rows-and-columns-with-a-control"></a>Para abarcar filas y columnas con un control  
  
1.  Seleccione el <xref:System.Windows.Forms.Button> control en la primera fila y primera columna.  
  
2.  En el **propiedades** windows, cambie el valor de la `ColumnSpan` propiedad **2**. Tenga en cuenta que el <xref:System.Windows.Forms.Button> control rellena la primera columna y la segunda columna. Tenga en cuenta que se ha agregado una fila adicional para dar cabida a este cambio.  
  
3.  Repita el paso 2 para el `RowSpan` propiedad.  
  
## <a name="inserting-controls-by-double-clicking-them-in-the-toolbox"></a>Insertar controles mediante un doble clic en estos en el cuadro de herramientas  
 Puede rellenar el <xref:System.Windows.Forms.TableLayoutPanel> control haciendo doble clic en los controles en el **cuadro de herramientas**.  
  
#### <a name="to-insert-controls-by-double-clicking-in-the-toolbox"></a>Para insertar controles mediante un doble clic en el cuadro de herramientas  
  
1.  Arrastre un <xref:System.Windows.Forms.TableLayoutPanel> controlar desde la **cuadro de herramientas** al formulario.  
  
2.  Haga doble clic en el icono del control <xref:System.Windows.Forms.Button> en el **Cuadro de herramientas**. Tenga en cuenta que aparece un nuevo control de botón en el <xref:System.Windows.Forms.TableLayoutPanel> primera celda del control.  
  
3.  Haga doble clic en algunos controles más en el **cuadro de herramientas**. Tenga en cuenta que los nuevos controles aparecen consecutivamente en el <xref:System.Windows.Forms.TableLayoutPanel> celdas desocupadas del control. Tenga en cuenta también que el <xref:System.Windows.Forms.TableLayoutPanel> control se expande para dar cabida a los nuevos controles si no hay ninguna celda abierta está disponible.  
  
## <a name="automatic-handling-of-overflows"></a>Control automático de desbordamientos  
 Cuando se insertan los controles en el <xref:System.Windows.Forms.TableLayoutPanel> (control), puede quedarse sin celdas vacías para los nuevos controles. El <xref:System.Windows.Forms.TableLayoutPanel> control controla automáticamente esta situación si aumenta el número de celdas.  
  
#### <a name="to-observe-automatic-handling-of-overflows"></a>Para observar el control automático de desbordamientos  
  
1.  Si hay celdas vacías todavía en el <xref:System.Windows.Forms.TableLayoutPanel> de control, siga insertando nuevos <xref:System.Windows.Forms.Button> controla hasta que el <xref:System.Windows.Forms.TableLayoutPanel> control está lleno.  
  
2.  Una vez el <xref:System.Windows.Forms.TableLayoutPanel> control está lleno, haga doble clic en el <xref:System.Windows.Forms.Button> icono en el **cuadro de herramientas** para insertar otro <xref:System.Windows.Forms.Button> control. Tenga en cuenta que el <xref:System.Windows.Forms.TableLayoutPanel> control crea nuevas celdas para alojar el nuevo control. Inserte algunos controles más y observe el comportamiento de cambio de tamaño.  
  
3.  Cambie el valor de la propiedad <xref:System.Windows.Forms.TableLayoutPanel.GrowStyle%2A> del control <xref:System.Windows.Forms.TableLayoutPanel> a <xref:System.Windows.Forms.TableLayoutPanelGrowStyle.FixedSize>. Haga doble clic en el <xref:System.Windows.Forms.Button> icono en el **cuadro de herramientas** para insertar <xref:System.Windows.Forms.Button> controla hasta que el <xref:System.Windows.Forms.TableLayoutPanel> control está lleno. Haga doble clic en el <xref:System.Windows.Forms.Button> icono en el **cuadro de herramientas** nuevo. Tenga en cuenta que recibe un mensaje de error de la **Diseñador de Windows Forms** que le informa de que no se puede crear otras filas y columnas.  
  
## <a name="inserting-a-control-by-drawing-its-outline"></a>Insertar un control dibujando su contorno  
 Puede insertar un control en un <xref:System.Windows.Forms.TableLayoutPanel> controlar y especificar su tamaño dibujando su contorno en una celda.  
  
#### <a name="to-insert-a-control-by-drawing-its-outline"></a>Para insertar un control dibujando su contorno  
  
1.  Arrastre un <xref:System.Windows.Forms.TableLayoutPanel> controlar desde la **cuadro de herramientas** al formulario.  
  
2.  En el **cuadro de herramientas**, haga clic en el icono del control <xref:System.Windows.Forms.Button> . No lo arrastre hasta el formulario.  
  
3.  Mueva el puntero del mouse sobre el <xref:System.Windows.Forms.TableLayoutPanel> control. Observe que el puntero cambia a una cruz con el icono del control <xref:System.Windows.Forms.Button> agregado.  
  
4.  Haga clic y mantenga presionado el botón del mouse.  
  
5.  Arrastre el puntero del mouse para dibujar el contorno del control <xref:System.Windows.Forms.Button> . Cuando esté satisfecho con el tamaño, suelte el botón del mouse. Tenga en cuenta que el <xref:System.Windows.Forms.Button> control se crea en la celda en la que dibujó el contorno.  
  
## <a name="multiple-controls-within-cells-are-not-permitted"></a>No se permiten varios controles dentro de las celdas  
 El <xref:System.Windows.Forms.TableLayoutPanel> control puede contener sólo un control secundario por celda.  
  
#### <a name="to-demonstrate-that-multiple-controls-within-cells-are-not-permitted"></a>Para demostrar que no se permiten varios controles dentro de las celdas  
  
-   Arrastre un <xref:System.Windows.Forms.Button> controlar desde la **cuadro de herramientas** en el <xref:System.Windows.Forms.TableLayoutPanel> controlar y colóquelo en una de las celdas ocupadas. Tenga en cuenta que la <xref:System.Windows.Forms.TableLayoutPanel> control no permite quitar el <xref:System.Windows.Forms.Button> control en la celda ocupada.  
  
## <a name="swapping-controls"></a>Intercambiar los controles  
 El <xref:System.Windows.Forms.TableLayoutPanel> control le permite intercambiar los controles que ocupan dos celdas diferentes.  
  
#### <a name="to-swap-controls"></a>Para intercambiar los controles  
  
-   Arrastre uno de los <xref:System.Windows.Forms.Button> controles de una celda ocupada y colocar en a otra celda ocupada. Tenga en cuenta que los dos controles se mueven de una celda en el otro.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Puede lograr un diseño complejo mediante una combinación de controles y paneles de diseño. Estas son otras sugerencias para seguir con la exploración:  
  
-   Intente cambiar el tamaño de uno de los <xref:System.Windows.Forms.Button> controles a un tamaño mayor y observe el efecto en el diseño.  
  
-   Pegar una selección de varios controles en el <xref:System.Windows.Forms.TableLayoutPanel> controlar y tenga en cuenta cómo se insertan los controles.  
  
-   Los paneles de diseño pueden contener otros paneles de diseño. Experimente colocando un control <xref:System.Windows.Forms.TableLayoutPanel> en el control existente.  
  
-   Acoplar el <xref:System.Windows.Forms.TableLayoutPanel> control al formulario principal. Cambie el tamaño del formulario y observe el efecto en el diseño.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.FlowLayoutPanel>  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 [Tutorial: Organizar controles en Windows Forms mediante FlowLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  
 [Tutorial: Organizar controles en formularios Windows Forms mediante líneas de ajuste](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)  
 [Microsoft Windows User Experience, Official Guidelines for User Interface Developers and diseñadores. Redmond, WA: Microsoft Press, 1999. (USBN: 0-7356-0566-1)](http://www.microsoft.com/mspress/southpacific/books/book11588.htm)  
 [Tutorial: Crear Windows Forms de entrada de datos de tamaño variable](http://msdn.microsoft.com/library/e193b4fc-912a-4917-b036-b76c7a6f58ab)  
 [Tutorial: Crear un formulario Localizable Windows Forms](http://msdn.microsoft.com/library/c5240b6e-aaca-4286-9bae-778a416edb9c)  
 [Procedimientos recomendados para el control TableLayoutPanel](../../../../docs/framework/winforms/controls/best-practices-for-the-tablelayoutpanel-control.md)  
 [Información general sobre la propiedad AutoSize](../../../../docs/framework/winforms/controls/autosize-property-overview.md)  
 [Procedimiento para acoplar controles en formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-dock-controls-on-windows-forms.md)  
 [Procedimiento para delimitar controles en formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-anchor-controls-on-windows-forms.md)  
 [Tutorial: Diseñar controles de Windows Forms con relleno, márgenes y la propiedad AutoSize](../../../../docs/framework/winforms/controls/windows-forms-controls-padding-autosize.md)
