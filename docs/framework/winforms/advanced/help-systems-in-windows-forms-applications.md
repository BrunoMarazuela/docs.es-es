---
title: Sistemas de ayuda en aplicaciones de Windows Forms
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Help [Windows Forms], adding to Windows applications
- Windows applications [Windows Forms], providing Help systems
- What's This? Help
- Help [Windows Forms], Windows Forms
- HelpProvider component [Windows Forms], providing Help in Windows applications
ms.assetid: 2a96a278-432c-41fc-9e3c-5bfedf5e1267
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1b2f5d067d487bbd5b91576927aee21a9a44fde0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="help-systems-in-windows-forms-applications"></a>Sistemas de ayuda en aplicaciones de Windows Forms
Una de las ventajas más importantes, como un desarrollador de aplicaciones, puede ofrecer a los usuarios es un sistema de ayuda eficaz. Esto es donde mostrará en color cuando estén confundidos o desorientados. Proporcionar un sistema de ayuda en una aplicación basada en Windows se realiza fácilmente mediante la [HelpProvider (componente)](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md).  
  
## <a name="different-types-of-help"></a>Diferentes tipos de ayuda  
 El componente <xref:System.Windows.Forms.HelpProvider> de Windows Forms se utiliza para asociar un archivo de Ayuda HTML Help 1.x (ya sea un archivo .chm generado con HTML Help Workshop o un archivo .htm) con una aplicación basada en Windows. El <xref:System.Windows.Forms.HelpProvider> componente puede utilizarse para proporcionar ayuda contextual para los controles en formularios Windows Forms o controles específicos. Además, la <xref:System.Windows.Forms.HelpProvider> componente puede abrir un archivo de ayuda en áreas específicas, como la página principal de una tabla de contenido, un índice o una función de búsqueda. Para obtener información general sobre la <xref:System.Windows.Forms.HelpProvider> componente, vea [general sobre el componente HelpProvider](../../../../docs/framework/winforms/controls/helpprovider-component-overview-windows-forms.md). Para obtener información sobre cómo usar el <xref:System.Windows.Forms.HelpProvider> componente para mostrar Ayuda emergente en formularios Windows Forms, vea [Cómo: mostrar Ayuda emergente](../../../../docs/framework/winforms/advanced/how-to-display-pop-up-help.md). Para obtener información sobre el uso de la <xref:System.Windows.Forms.ToolTip> componente para mostrar ayuda específica del control, vea [Control ayuda mediante información sobre herramientas](../../../../docs/framework/winforms/advanced/control-help-using-tooltips.md).  
  
 Puede generar archivos HTML Help 1.x con HTML Help Workshop. Para obtener más información sobre la Ayuda HTML, vea "HTML Help Workshop" o los otros temas de "Ayuda HTML" en MSDN.  
  
## <a name="see-also"></a>Vea también  
 [Integrar la Ayuda de usuario en Windows Forms](../../../../docs/framework/winforms/advanced/integrating-user-help-in-windows-forms.md)  
 [HelpProvider (componente)](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md)  
 [ToolTip (componente)](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md)  
 [Información general sobre formularios Windows Forms](../../../../docs/framework/winforms/windows-forms-overview.md)  
 [Windows Forms](../../../../docs/framework/winforms/index.md)
