---
title: "Información general de información sobre herramientas"
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
- ToolTip control [WPF], about ToolTip control
- controls [WPF], ToolTip
ms.assetid: f06c1603-e9cb-4809-8a62-234607fc52f7
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7c945d23def3bbf6284e7e0db95d391066256df6
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="tooltip-overview"></a>Información general de información sobre herramientas
Una información sobre herramientas es una pequeña ventana emergente que aparece cuando un usuario pausa el puntero del mouse sobre un elemento, por ejemplo, como en un <xref:System.Windows.Controls.Button>. En este tema se presenta la información sobre herramientas y se explica cómo crear y personalizar el contenido de la información sobre herramientas.  
  
 
  
<a name="what_is_a_tooltip"></a>   
## <a name="what-is-a-tooltip"></a>¿Qué es la información sobre herramientas?  
 Cuando un usuario mueve el puntero del mouse sobre un elemento que tiene información sobre herramientas, aparece una ventana con información sobre herramientas (por ejemplo, texto que describe la función de un control) durante un período de tiempo especificado. Si el usuario mueve el puntero del mouse fuera del control, la ventana desaparece porque el contenido de la información sobre herramientas deja de recibir el foco.  
  
 La información sobre herramientas puede contener una o más líneas de texto, imágenes, formas u otro contenido visual. Para definir la información sobre herramientas de un control, establezca una de las siguientes propiedades en el contenido de la información sobre herramientas.  
  
-   <xref:System.Windows.FrameworkContentElement.ToolTip%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.FrameworkElement.ToolTip%2A?displayProperty=nameWithType>  
  
 La propiedad que utilice depende de si el control que define la información sobre herramientas se hereda de la <xref:System.Windows.FrameworkContentElement> o <xref:System.Windows.FrameworkElement> clase.  
  
<a name="create_tooltip"></a>   
## <a name="creating-a-tooltip"></a>Creación de una información sobre herramientas  
 En el ejemplo siguiente se muestra cómo crear una información sobre herramientas simple estableciendo la <xref:System.Windows.FrameworkElement.ToolTip%2A> propiedad para un <xref:System.Windows.Controls.Button> control en una cadena de texto.  
  
 [!code-xaml[GroupBoxSnippet#ToolTipString](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#tooltipstring)]  
  
 También puede definir una información sobre herramientas como un <xref:System.Windows.Controls.ToolTip> objeto. En el ejemplo siguiente se utiliza [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] para especificar un <xref:System.Windows.Controls.ToolTip> objeto como la información sobre herramientas de un <xref:System.Windows.Controls.TextBox> elemento. Tenga en cuenta que el ejemplo se especifica la <xref:System.Windows.Controls.ToolTip> estableciendo el <xref:System.Windows.FrameworkElement.ToolTip%2A?displayProperty=nameWithType> propiedad.  
  
 [!code-xaml[ToolTipSimple#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipSimple/CSharp/Pane1.xaml#tooltip)]  
  
 En el ejemplo siguiente se utiliza código para generar un <xref:System.Windows.Controls.ToolTip> objeto. El ejemplo se crea un <xref:System.Windows.Controls.ToolTip> (`tt`) y lo asocia a un <xref:System.Windows.Controls.Button>.  
  
 [!code-csharp[ToolTipSimple#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipSimple/CSharp/Pane1.xaml.cs#2)]
 [!code-vb[ToolTipSimple#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipSimple/VisualBasic/Window1.xaml.vb#2)]  
  
 También puede crear contenido de información sobre herramientas que no está definido como un <xref:System.Windows.Controls.ToolTip> objeto, incluya el contenido de la información sobre herramientas en un elemento de diseño, como un <xref:System.Windows.Controls.DockPanel>. En el ejemplo siguiente se muestra cómo establecer el <xref:System.Windows.FrameworkElement.ToolTip%2A> propiedad de un <xref:System.Windows.Controls.TextBox> a contenido que se incluye en un <xref:System.Windows.Controls.DockPanel> control.  
  
 [!code-xaml[GroupBoxSnippet#ToolTipDockPanel](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#tooltipdockpanel)]  
  
<a name="Using_the_ToolTip_and_ToolTipService_Properties"></a>   
## <a name="using-the-properties-of-the-tooltip-and-tooltipservice-classes"></a>Uso de las propiedades de las clases ToolTip y ToolTipService  
 Para personalizar el contenido de la información sobre herramientas, puede establecer las propiedades visuales y aplicar estilos. Si se define la información sobre herramientas contenido como un <xref:System.Windows.Controls.ToolTip> objeto, puede establecer las propiedades visuales de la <xref:System.Windows.Controls.ToolTip> objeto. En caso contrario, debe establecer las propiedades adjuntas equivalente en el <xref:System.Windows.Controls.ToolTipService> clase.  
  
 Para obtener un ejemplo de cómo establecer propiedades para especificar la posición del contenido de la información sobre herramientas mediante la <xref:System.Windows.Controls.ToolTip> y <xref:System.Windows.Controls.ToolTipService> propiedades, consulte [colocar una información sobre herramientas](../../../../docs/framework/wpf/controls/how-to-position-a-tooltip.md).  
  
<a name="StylingToolTip"></a>   
## <a name="styling-a-tooltip"></a>Aplicar estilos a una información sobre herramientas  
 Puedes aplicar estilo a un <xref:System.Windows.Controls.ToolTip> definiendo un personalizado <xref:System.Windows.Style>. En el ejemplo siguiente se define un <xref:System.Windows.Style> llama `Simple` que muestra cómo desplazar la colocación de la <xref:System.Windows.Controls.ToolTip> y cambiar su apariencia estableciendo la <xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>, <xref:System.Windows.Controls.Control.FontSize%2A>, y <xref:System.Windows.Controls.Control.FontWeight%2A>.  
  
 [!code-xaml[ToolTipSimple#Style](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipSimple/CSharp/Pane1.xaml#style)]  
  
<a name="UsingtheToolTipServiceTimeIntervalProperties"></a>   
## <a name="using-the-time-interval-properties-of-tooltipservice"></a>Uso de las propiedades de intervalo de tiempo de ToolTipService  
 El <xref:System.Windows.Controls.ToolTipService> clase proporciona las siguientes propiedades para establecer información sobre herramientas muestran horas: <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A>, <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A>, y <xref:System.Windows.Controls.ToolTipService.ShowDuration%2A>.  
  
 Use la <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> y <xref:System.Windows.Controls.ToolTipService.ShowDuration%2A> propiedades para especificar un retraso, por lo general breve, antes un <xref:System.Windows.Controls.ToolTip> aparece y también para especificar cuánto tiempo un <xref:System.Windows.Controls.ToolTip> permanece visible. Para obtener más información, consulte [How to: Delay the Display of a ToolTip](http://msdn.microsoft.com/library/618e05ef-f2bf-4a53-a0f4-aacb49918bd7) (Cómo: Retrasar la visualización de una información sobre herramientas).  
  
 El <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> propiedad determina si aparece información sobre herramientas para controles diferentes sin retraso inicial cuando se mueve el puntero del mouse rápidamente entre ellos. Para obtener más información sobre la <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> propiedad, vea [usar la propiedad BetweenShowDelay](../../../../docs/framework/wpf/controls/how-to-use-the-betweenshowdelay-property.md).  
  
 En el ejemplo siguiente se muestra cómo establecer estas propiedades para una información sobre herramientas.  
  
 [!code-xaml[ToolTipService#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Controls.ToolTipService>  
 <xref:System.Windows.Controls.ToolTip>  
 <xref:System.Windows.Controls.ToolTipEventArgs>  
 <xref:System.Windows.Controls.ToolTipEventHandler>  
 [Temas "Cómo..."](../../../../docs/framework/wpf/controls/tooltip-how-to-topics.md)
