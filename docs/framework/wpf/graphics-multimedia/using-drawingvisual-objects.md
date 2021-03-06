---
title: Usar objetos DrawingVisual
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
- visual layer [WPF], DrawingVisual objects
- DrawingVisual objects in visual layer [WPF]
ms.assetid: 0b4e711d-e640-40cb-81c3-8f5c59909b7d
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a33e56b69a357694a1d1a23d5cd3c887c88cea37
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="using-drawingvisual-objects"></a>Usar objetos DrawingVisual
Este tema proporciona información general sobre cómo usar <xref:System.Windows.Media.DrawingVisual> objetos en la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] capa visual.  
  
<a name="drawingvisual_object"></a>   
## <a name="drawingvisual-object"></a>Objeto DrawingVisual  
 El <xref:System.Windows.Media.DrawingVisual> es una ligera dibujo de la clase que se usa para representar formas, imágenes o texto. Esta clase se considera ligera porque no proporciona control de diseño ni control de eventos, lo que mejora su rendimiento. Por esta razón, los dibujos son ideales para fondos e imágenes prediseñadas.  
  
<a name="drawingvisual_host_container"></a>   
## <a name="drawingvisual-host-container"></a>Contenedor host de objetos DrawingVisual  
 Para poder usar <xref:System.Windows.Media.DrawingVisual> objetos, debe crear un contenedor para los objetos. El objeto contenedor host debe derivar de la <xref:System.Windows.FrameworkElement> (clase), que proporciona el diseño y el control de eventos que admiten el <xref:System.Windows.Media.DrawingVisual> la falta de clase. El objeto contenedor host no muestra ninguna propiedad visible, puesto que su finalidad principal es contener objetos secundarios. Sin embargo, el <xref:System.Windows.UIElement.Visibility%2A> propiedad del contenedor host debe establecerse en <xref:System.Windows.Visibility.Visible>; en caso contrario, ninguno de sus elementos secundarios estará visible.  
  
 Cuando se crea un objeto de contenedor host para objetos visuales, debe almacenar las referencias de objeto visual en un <xref:System.Windows.Media.VisualCollection>. Use la <xref:System.Windows.Media.VisualCollection.Add%2A> método para agregar un objeto visual para el contenedor del host. En el ejemplo siguiente, se crea un objeto host de contenedor y se agregan tres objetos visuales a su <xref:System.Windows.Media.VisualCollection>.  
  
 [!code-csharp[DrawingVisualSample#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#100)]
 [!code-vb[DrawingVisualSample#100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#100)]  
  
> [!NOTE]
>  Para obtener el código completo del que se ha extraído el ejemplo de código anterior, vea [Ejemplo Hit Test Using DrawingVisuals](http://go.microsoft.com/fwlink/?LinkID=159994).  
  
<a name="creating_drawingvisual_objects"></a>   
## <a name="creating-drawingvisual-objects"></a>Crear objetos DrawingVisual  
 Cuando se crea un <xref:System.Windows.Media.DrawingVisual> de objeto, no tiene contenido dibujo. Puede agregar texto, gráficos o contenido de la imagen mediante la recuperación del objeto <xref:System.Windows.Media.DrawingContext> y dibujo en él. A <xref:System.Windows.Media.DrawingContext> devuelto por una llamada a la <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> método de una <xref:System.Windows.Media.DrawingVisual> objeto.  
  
 Para dibujar un rectángulo en el <xref:System.Windows.Media.DrawingContext>, use la <xref:System.Windows.Media.DrawingContext.DrawRectangle%2A> método de la <xref:System.Windows.Media.DrawingContext> objeto. Existen métodos similares para dibujar otros tipos de contenido. Cuando haya terminado de dibujo contenido en el <xref:System.Windows.Media.DrawingContext>, llame a la <xref:System.Windows.Media.DrawingContext.Close%2A> método para cerrar la <xref:System.Windows.Media.DrawingContext> y conservar el contenido.  
  
 En el ejemplo siguiente, un <xref:System.Windows.Media.DrawingVisual> objeto se crea y se dibuja un rectángulo en su <xref:System.Windows.Media.DrawingContext>.  
  
 [!code-csharp[DrawingVisualSample#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#101)]
 [!code-vb[DrawingVisualSample#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#101)]  
  
<a name="creating_overrides"></a>   
## <a name="creating-overrides-for-frameworkelement-members"></a>Crear invalidaciones para los miembros FrameworkElement  
 El objeto contenedor host es responsable de administrar su colección de objetos visuales. Esto requiere que el contenedor host debe implementar invalidaciones de miembros para la clase derivada <xref:System.Windows.FrameworkElement> clase.  
  
 En la lista siguiente se describen los dos miembros que debe invalidar:  
  
-   <xref:System.Windows.FrameworkElement.GetVisualChild%2A>: Devuelve a un elemento secundario en el índice especificado de la colección de elementos secundarios.  
  
-   <xref:System.Windows.FrameworkElement.VisualChildrenCount%2A>: Obtiene el número de elementos secundarios visuales de este elemento.  
  
 En el siguiente ejemplo, invalidaciones para los dos <xref:System.Windows.FrameworkElement> se implementan los miembros.  
  
 [!code-csharp[DrawingVisualSample#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#102)]
 [!code-vb[DrawingVisualSample#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#102)]  
  
<a name="providing_hit_testing_support"></a>   
## <a name="providing-hit-testing-support"></a>Proporcionar compatibilidad con las pruebas de posicionamiento  
 El objeto contenedor host puede proporcionar control de eventos, incluso si no se muestra ninguna propiedad visible, sin embargo, su <xref:System.Windows.UIElement.Visibility%2A> propiedad debe establecerse en <xref:System.Windows.Visibility.Visible>. Esto permite crear una rutina de control de eventos para el contenedor host que pueda interceptar los eventos del mouse, tales como soltar el botón izquierdo. La rutina de control de eventos, a continuación, pueden implementar la prueba de posicionamiento invocando el <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> método. El método <xref:System.Windows.Media.HitTestResultCallback> parámetro hace referencia a un procedimiento definido por el usuario que se puede utilizar para determinar la acción resultante de una prueba de posicionamiento.  
  
 En el ejemplo siguiente, se implementa la compatibilidad con las pruebas de posicionamiento para el objeto contenedor host y sus elementos secundarios.  
  
 [!code-csharp[DrawingVisualSample#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#103)]
 [!code-vb[DrawingVisualSample#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#103)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Media.DrawingVisual>  
 <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>  
 [Información general sobre la representación de gráficos en WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)  
 [Realizar pruebas de posicionamiento en la capa visual](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)
