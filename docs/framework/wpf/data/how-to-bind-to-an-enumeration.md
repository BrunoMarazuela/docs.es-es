---
title: "Cómo: Enlazar a una enumeración"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- binding data [WPF], enumeration
- data binding [WPF], enumeration
- enumeration [WPF]
ms.assetid: b9091eba-1119-424e-868b-d1a4168b3732
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 72439cdc1c1017378a5b6b3f6b4bf41a9eee2537
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-bind-to-an-enumeration"></a>Cómo: Enlazar a una enumeración
Este ejemplo muestra cómo enlazar a una enumeración enlazando al método GetValues de la enumeración.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, la <xref:System.Windows.Controls.ListBox> muestra la lista de <xref:System.Windows.HorizontalAlignment> valores de enumeración a través del enlace de datos. El <xref:System.Windows.Controls.ListBox> y <xref:System.Windows.Controls.Button> se enlazan de forma que pueda cambiar la <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> valor de propiedad de la <xref:System.Windows.Controls.Button> seleccionando un valor en el <xref:System.Windows.Controls.ListBox>.  
  
 [!code-xaml[BindToEnum#BindToEnum](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToEnum/CS/Window1.xaml#bindtoenum)]  
  
## <a name="see-also"></a>Vea también  
 [Enlazar a un método](../../../../docs/framework/wpf/data/how-to-bind-to-a-method.md)  
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Temas "Cómo..."](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
