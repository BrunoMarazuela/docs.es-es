---
title: Buscar y resaltar texto mediante UI Automation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text, highlighting
- finding text
- text, finding
- UI automation, highlighting text
- UI automation, finding text
- highlighting text
ms.assetid: b77693f5-87bb-4b29-a297-05ff882e2044
caps.latest.revision: "15"
author: Xansky
ms.author: mhopkins
manager: markl
ms.workload: dotnet
ms.openlocfilehash: b6b734c6f6b033d7c327e94926584184ed8a76d0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="find-and-highlight-text-using-ui-automation"></a>Buscar y resaltar texto mediante UI Automation
> [!NOTE]
>  Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Este tema muestra cómo buscar y resaltar cada aparición de una cadena dentro del contenido de un control de texto mediante forma secuencial [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)].  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se obtiene un <xref:System.Windows.Automation.TextPattern> objeto de un control de texto. A <xref:System.Windows.Automation.Text.TextPatternRange> objeto, que representa el contenido textual de todo el documento, a continuación, se crea mediante la <xref:System.Windows.Automation.TextPattern.DocumentRange%2A> propiedad de este <xref:System.Windows.Automation.TextPattern>. Dos adicionales <xref:System.Windows.Automation.Text.TextPatternRange> objetos, a continuación, se crean para la búsqueda secuencial y resalte la funcionalidad.  
  
 [!code-csharp[FindText#StartApp](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#startapp)]
 [!code-vb[FindText#StartApp](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#startapp)]  
[!code-csharp[FindText#FindTextProvider](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#findtextprovider)]
[!code-vb[FindText#FindTextProvider](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#findtextprovider)]  
[!code-csharp[FindText#SearchTarget](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#searchtarget)]
[!code-vb[FindText#SearchTarget](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#searchtarget)]  
  
## <a name="see-also"></a>Vea también  
 [Búsqueda y resaltado de texto mediante Automatización de la interfaz de usuario](../../../docs/framework/ui-automation/find-and-highlight-text-using-ui-automation.md)
