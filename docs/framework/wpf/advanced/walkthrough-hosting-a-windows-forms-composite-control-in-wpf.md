---
title: 'Tutorial: Hospedar un control compuesto de formularios Windows Forms en WPF'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
- composite controls [WPF], hosting in WPF
ms.assetid: 96fcd78d-1c77-4206-8928-3a0579476ef4
caps.latest.revision: "33"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9f332461bd5abb5e3fca705a8a5fd363c3d33296
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="walkthrough-hosting-a-windows-forms-composite-control-in-wpf"></a>Tutorial: Hospedar un control compuesto de formularios Windows Forms en WPF
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona un entorno rico para crear aplicaciones. Sin embargo, si tiene una inversión sustancial en [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] código, puede ser más eficaz volver a usar al menos parte de ese código en su [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicación en lugar de volver a escribir desde el principio. El escenario más común es cuando dispone de [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] controles. En algunos casos, incluso podría no tener acceso al código fuente de estos controles. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]Proporciona un procedimiento sencillo para hospedar estos controles en un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicación. Por ejemplo, puede usar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] para la mayor parte de la programación mientras lo hospeda su especializada <xref:System.Windows.Forms.DataGridView> controles.  
  
 Este tutorial le guía a través de una aplicación que hospeda un [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] control compuesto para realizar la entrada de datos en un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicación. El control compuesto se empaqueta en un archivo DLL. Este procedimiento general se puede extender a aplicaciones y controles más complejos. En este tutorial está diseñado para ser casi idénticos en apariencia y funcionalidad a [Tutorial: hospedar un Control compuesto de WPF en formularios Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md). La principal diferencia es que se invierte el escenario de hospedaje.  
  
 Este tutorial está dividido en dos secciones. La primera sección describe brevemente la implementación de la [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] control compuesto. La segunda sección analiza en detalle cómo hospedar el control compuesto en una [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] recibir eventos desde el control de aplicación y tener acceso a algunas de las propiedades del control.  
  
 Las tareas ilustradas en este tutorial incluyen:  
  
-   Implementar el control compuesto de formularios Windows Forms.  
  
-   Implementar la aplicación host de WPF.  
  
 Para obtener una lista de código completa de las tareas ilustradas en este tutorial, vea [hospedar un Control compuesto de Windows Forms en WPF Sample](http://go.microsoft.com/fwlink/?LinkID=159999).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Necesita los componentes siguientes para completar este tutorial:  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
## <a name="implementing-the-windows-forms-composite-control"></a>Implementar el control compuesto de formularios Windows Forms  
 El [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] control compuesto que se utiliza en este ejemplo es un formulario de entrada de datos simple. Este formulario toma el nombre y la dirección del usuario y, después, usa un evento personalizado para devolver esa información al host. En la ilustración siguiente se muestra la representación del control.  
  
 ![Control simple de Windows Forms](../../../../docs/framework/wpf/advanced/media/wfcontrol.gif "WFControl")  
Control compuesto de formularios Windows Forms  
  
### <a name="creating-the-project"></a>Crear el proyecto  
 Para iniciar el proyecto:  
  
1.  Iniciar [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]y abra el **nuevo proyecto** cuadro de diálogo.  
  
2.  En la categoría de la ventana, seleccione la **biblioteca de controles de Windows Forms** plantilla.  
  
3.  Asigne al nuevo proyecto el nombre de `MyControls`.  
  
4.  Para la ubicación, especifique una carpeta de nivel superior con el nombre, como `WpfHostingWindowsFormsControl`. Más tarde, colocará la aplicación host en esta carpeta.  
  
5.  Haga clic en **Aceptar** para crear el proyecto. El proyecto predeterminado contiene un solo control denominado `UserControl1`.  
  
6.  En el Explorador de soluciones, cambie el nombre `UserControl1` a `MyControl1`.  
  
 El proyecto debe tener referencias a los siguientes archivos DLL del sistema. Si alguno de estos archivos DLL no está incluido de forma predeterminada, agréguelo al proyecto.  
  
-   Sistema  
  
-   System.Data  
  
-   System.Drawing  
  
-   System.Windows.Forms  
  
-   System.Xml  
  
### <a name="adding-controls-to-the-form"></a>Agregar controles al formulario  
 Para agregar controles al formulario:  
  
-   Abra `MyControl1` en el diseñador.  
  
 Agregue cinco <xref:System.Windows.Forms.Label> controles y sus correspondientes <xref:System.Windows.Forms.TextBox> controles, tamaño y se ordenarán como aparecen en la ilustración anterior, en el formulario. En el ejemplo, el <xref:System.Windows.Forms.TextBox> se denominan controles:  
  
-   `txtName`  
  
-   `txtAddress`  
  
-   `txtCity`  
  
-   `txtState`  
  
-   `txtZip`  
  
 Agregar dos <xref:System.Windows.Forms.Button> controles etiquetados **Aceptar** y **cancelar**. En el ejemplo, los nombres de los botones son `btnOK` y `btnCancel`, respectivamente.  
  
### <a name="implementing-the-supporting-code"></a>Implementar el código auxiliar  
 Abra el formulario en la vista Código. El control devuelve los datos recopilados a su host generando personalizado `OnButtonClick` eventos. Los datos están contenidos en el objeto de argumento de evento. En el código siguiente se muestra la declaración de evento y delegado.  
  
 Agregue el código siguiente a la clase `MyControl1`.  
  
 [!code-csharp[WpfHostingWindowsFormsControl#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#2)]
 [!code-vb[WpfHostingWindowsFormsControl#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#2)]  
  
 La `MyControlEventArgs` clase contiene la información que se devuelve al host.  
  
 Agregue la clase siguiente al formulario.  
  
 [!code-csharp[WpfHostingWindowsFormsControl#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#3)]
 [!code-vb[WpfHostingWindowsFormsControl#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#3)]  
  
 Cuando el usuario hace clic en el **Aceptar** o **cancelar** botón, el <xref:System.Windows.Forms.Control.Click> crear controladores de eventos un `MyControlEventArgs` objeto que contiene los datos y genera el `OnButtonClick` eventos. La única diferencia entre los dos controladores es el argumento de evento `IsOK` propiedad. Esta propiedad permite que el host determine en qué botón se ha hecho clic. Se establece en `true` para el **Aceptar** botón, y `false` para el **cancelar** botón. En el código siguiente se muestran los dos controladores de botón.  
  
 Agregue el código siguiente a la clase `MyControl1`.  
  
 [!code-csharp[WpfHostingWindowsFormsControl#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#4)]
 [!code-vb[WpfHostingWindowsFormsControl#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#4)]  
  
### <a name="giving-the-assembly-a-strong-name-and-building-the-assembly"></a>Dar un nombre seguro al ensamblado y compilar el ensamblado  
 Para este ensamblado que hace referencia un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicación, debe tener un nombre seguro. Para crear un nombre seguro, cree un archivo de clave con Sn.exe y agregarlo al proyecto.  
  
1.  Abra un símbolo del sistema de [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]. Para ello, haga clic en el **iniciar** menú y, a continuación, seleccione **todos los programas/Microsoft Visual Studio 2010 o Visual Studio Tools/Visual Studio Command Prompt**. Esto inicia una ventana de consola con variables de entorno personalizadas.  
  
2.  En el símbolo del sistema, use la `cd` comando para ir a la carpeta del proyecto.  
  
3.  Ejecute el comando siguiente para generar un archivo de clave denominado MyControls.snk.  
  
    ```  
    Sn.exe -k MyControls.snk  
    ```  
  
4.  Para incluir el archivo de clave en el proyecto, haga clic en el nombre del proyecto en el Explorador de soluciones y, a continuación, haga clic en **propiedades**. En el Diseñador de proyectos, haga clic en el **firma** ficha, seleccione la **firmar el ensamblado** casilla de verificación y, a continuación, vaya al archivo de clave.  
  
5.  Compile la solución. La compilación generará un archivo DLL denominado MyControls.dll.  
  
## <a name="implementing-the-wpf-host-application"></a>Implementar la aplicación host de WPF  
 El [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] hospedar la aplicación usa el <xref:System.Windows.Forms.Integration.WindowsFormsHost> control al host `MyControl1`. Los identificadores de aplicación el `OnButtonClick` eventos para recibir los datos procedentes del control. También tiene una colección de botones de opción que le permiten cambiar algunas de las propiedades del control de la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicación. En la ilustración siguiente se muestra la aplicación finalizada.  
  
 ![Un control incrustado en una página WPF](../../../../docs/framework/wpf/advanced/media/avalonhost.gif "AvalonHost")  
La aplicación completa, en la que se muestra el control insertado en la aplicación WPF  
  
### <a name="creating-the-project"></a>Crear el proyecto  
 Para iniciar el proyecto:  
  
1.  Abra [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]y seleccione **nuevo proyecto**.  
  
2.  En la categoría de la ventana, seleccione la **aplicación WPF** plantilla.
  
3.  Asigne al nuevo proyecto el nombre de `WpfHost`.  
  
4.  Para la ubicación, especifique la misma carpeta de nivel superior que contiene el proyecto MyControls.  
  
5.  Haga clic en **Aceptar** para crear el proyecto.  
  
 También debe agregar referencias a la DLL que contiene `MyControl1` y otros ensamblados.  
  
1.  Haga clic en el nombre del proyecto en el Explorador de soluciones y seleccione **Agregar referencia**.  
  
2.  Haga clic en el **examinar** pestaña y vaya a la carpeta que contiene MyControls.dll. En este tutorial, esta carpeta es MyControls\bin\Debug.  
  
3.  Seleccione MyControls.dll y, a continuación, haga clic en **Aceptar**.  
  
4.  Agregue una referencia al ensamblado WindowsFormsIntegration, denominado WindowsFormsIntegration.dll.  
  
### <a name="implementing-the-basic-layout"></a>Implementar el diseño básico  
 El [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] del host de aplicación se implementa en MainWindow.xaml. Este archivo contiene [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] marcado que define el diseño y hospeda el [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] control. La aplicación se divide en tres regiones:  
  
-   El **propiedades del Control** panel, que contiene una colección de botones de opción que puede utilizar para modificar las distintas propiedades del control hospedado.  
  
-   El **datos desde el Control de** panel, que contiene varios <xref:System.Windows.Controls.TextBlock> devuelven elementos que mostrar los datos procedentes del control hospedado.  
  
-   El control hospedado.  
  
 En el siguiente código XAML se muestra el diseño básico. El marcado que se necesita para host `MyControl1` se omite en este ejemplo, pero se explicará más adelante.  
  
 Reemplace el código XAML del archivo MainWindow.xaml.vb por el código siguiente. Si está utilizando Visual Basic, cambie la clase para `x:Class="MainWindow"`.  
  
 [!code-xaml[WpfHostingWindowsFormsControl#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#100)]  
  
 La primera <xref:System.Windows.Controls.StackPanel> elemento contiene varios conjuntos de <xref:System.Windows.Controls.RadioButton> controles que permiten modificar diversas propiedades predeterminadas del control hospedado. Seguido por un <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento, qué hosts `MyControl1`. La última <xref:System.Windows.Controls.StackPanel> elemento contiene varios <xref:System.Windows.Controls.TextBlock> elementos que mostrar los datos devueltos por el control hospedado. El orden de los elementos y los <xref:System.Windows.Controls.DockPanel.Dock%2A> y <xref:System.Windows.FrameworkElement.Height%2A> valores de atributo incrustan el control hospedado en la ventana sin espacios ni distorsión.  
  
#### <a name="hosting-the-control"></a>Hospedar el control  
 La siguiente versión modificada del XAML anterior se centra en los elementos que son necesarios al host `MyControl1`.  
  
 [!code-xaml[WpfHostingWindowsFormsControl#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#101)]  
[!code-xaml[WpfHostingWindowsFormsControl#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#102)]  
  
 El `xmlns` atributo de asignación de espacio de nombres crea una referencia a la `MyControls` espacio de nombres que contiene el control hospedado. Esta asignación permite representar `MyControl1` en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] como `<mcl:MyControl1>`.  
  
 Dos elementos del código XAML controlan el hospedaje:  
  
-   `WindowsFormsHost`representa la <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento que permite al host una [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] controlar en un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicación.  
  
-   `mcl:MyControl1`, que representa `MyControl1`, se agrega a la <xref:System.Windows.Forms.Integration.WindowsFormsHost> colección de elemento secundario del elemento. Como resultado, este [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] control se representa como parte de la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ventana y puede comunicarse con el control de la aplicación.  
  
### <a name="implementing-the-code-behind-file"></a>Implementar el archivo de código subyacente  
 El archivo de código subyacente, el archivo MainWindow.Xaml.cs o MainWindow.Xaml.vb, contiene el código de procedimiento que implementa la funcionalidad de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] se describe en la sección anterior. Las tareas principales son:  
  
-   Asociar un controlador de eventos para `MyControl1`de `OnButtonClick` eventos.  
  
-   Modificar varias propiedades de `MyControl1`, en función de cómo se establece la colección de botones de opción.  
  
-   Mostrar los datos recopilados por el control.  
  
#### <a name="initializing-the-application"></a>Inicializar la aplicación  
 El código de inicialización está contenido en un controlador de eventos para la ventana <xref:System.Windows.FrameworkElement.Loaded> eventos y asocia un controlador de eventos para el control `OnButtonClick` eventos.  
  
 En el archivo MainWindow.Xaml.cs o MainWindow.Xaml.vb, agregue el código siguiente a la `MainWindow` clase.  
  
 [!code-csharp[WpfHostingWindowsFormsControl#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#11)]
 [!code-vb[WpfHostingWindowsFormsControl#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#11)]  
  
 Porque el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] descrito previamente agregado `MyControl1` a la <xref:System.Windows.Forms.Integration.WindowsFormsHost> colección de elementos secundarios del elemento, puede convertir el <xref:System.Windows.Forms.Integration.WindowsFormsHost> del elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A> para obtener la referencia a `MyControl1`. A continuación, puede usar esa referencia para adjuntar un controlador de eventos para `OnButtonClick`.  
  
 Además de proporcionar una referencia al propio control, <xref:System.Windows.Forms.Integration.WindowsFormsHost> expone una serie de propiedades del control, que se pueden manipular desde la aplicación. El código de inicialización asigna estos valores a variables globales privadas para su uso posterior en la aplicación.  
  
 Para que puedan acceder fácilmente a los tipos en el `MyControls` DLL, agregue el siguiente `Imports` o `using` instrucción al principio del archivo.  
  
```vb  
Imports MyControls  
```  
  
```csharp  
using MyControls;  
```  
  
#### <a name="handling-the-onbuttonclick-event"></a>Controlar el evento OnButtonClick  
 `MyControl1`genera el `OnButtonClick` eventos cuando el usuario hace clic en cualquiera de los botones del control.  
  
 Agregue el código siguiente a la clase `MainWindow`.  
  
 [!code-csharp[WpfHostingWindowsFormsControl#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#12)]
 [!code-vb[WpfHostingWindowsFormsControl#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#12)]  
  
 Los datos en los cuadros de texto se empaquetan en la `MyControlEventArgs` objeto. Si el usuario hace clic en el **Aceptar** botón, el controlador de eventos extrae los datos y lo muestra en el panel siguiente `MyControl1`.  
  
#### <a name="modifying-the-controls-properties"></a>Modificar las propiedades del control  
 El <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento expone varias propiedades de valor predeterminado del control hospedado. Como resultado, puede cambiar el aspecto del control para que se adapte mejor al estilo de la aplicación. Los conjuntos de botones de opción del panel izquierdo permiten al usuario modificar varias propiedades de color y fuente. Cada conjunto de botones tiene un controlador para el <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento, que detecta las selecciones de botón de opción del usuario y cambia la propiedad correspondiente en el control.  
  
 Agregue el código siguiente a la clase `MainWindow`.  
  
 [!code-csharp[WpfHostingWindowsFormsControl#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#13)]
 [!code-vb[WpfHostingWindowsFormsControl#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#13)]  
  
 Compile y ejecute la aplicación. Agregar texto en el control compuesto de formularios Windows Forms y, a continuación, haga clic en **Aceptar**. El texto aparece en las etiquetas. Haga clic en los diferentes botones de radio para ver el efecto en el control.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [WPF Designer](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 [Tutorial: Hospedar un control de Windows Forms en WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)  
 [Tutorial: Hospedar un control compuesto de WPF en formularios Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
