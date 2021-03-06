---
title: Atributos ServiceModel y referencia ServiceDescription
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4ab86b17-eab9-4846-a881-0099f9a7cc64
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 61a0811176a5db17e040073d031fa50865a09857
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="servicemodel-attributes-and-servicedescription-reference"></a>Atributos ServiceModel y referencia ServiceDescription
El *árbol de descripción* es la jerarquía de tipos (comenzando por el <xref:System.ServiceModel.Description.ServiceDescription?displayProperty=nameWithType> clase) que juntos describen cada aspecto de un servicio. [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] usa un árbol de descripción para compilar un tiempo de ejecución válido del servicio, para publicar el Lenguaje de descripción de servicios web (WSDL), el Lenguaje de definición de esquemas XML (XSD) y las aserciones de directiva (metadatos) sobre el servicio que los clientes pueden usar para conectar y usar el servicio, y para generar las diferentes representaciones de código y del archivo de configuración de los valores del árbol de descripción.  
  
 En este tema se describe cómo las propiedades relacionadas con contrato se obtienen del contrato de servicios, y cómo se implementan y agregan al árbol de descripción. En algunos casos, los valores de atributo se convierten en propiedades del comportamiento y el comportamiento se inserta en el árbol de descripción. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]cómo se convierten los valores del árbol de descripción en metadatos, vea [ServiceDescription y referencias WSDL](../../../../docs/framework/wcf/feature-details/servicedescription-and-wsdl-reference.md).  
  
## <a name="mapping-operations-to-the-description-tree"></a>Asignación de operaciones al árbol de descripción  
 En las aplicaciones de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], los contratos de servicios son modelados mediante interfaces (o clases) que utilizan atributos para marcar la interfaz o clase y sus métodos como un agrupamiento de operaciones. Cuando se abre una clase <xref:System.ServiceModel.ServiceHost>, las implementaciones y contratos de servicios se reflejan y combinan con información de configuración en un árbol de descripción.  
  
 Hay dos tipos de modelos de operaciones: el *parámetro* modelo y la *contrato de mensaje* modelo. El modelo de parámetro usa métodos administrados que no tienen un parámetro o tipo de valor devuelto que esté marcado por la clase <xref:System.ServiceModel.MessageContractAttribute?displayProperty=nameWithType>. En este modelo, los desarrolladores controlan la serialización de parámetros y valores devueltos, pero [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera los valores que se utilizan para rellenar el árbol de descripción para el servicio y su contrato.  
  
 Los enlaces especificados en archivos de configuración se cargan directamente en la propiedad <xref:System.ServiceModel.Description.ServiceEndpoint.Binding%2A?displayProperty=nameWithType>.  
  
|Propiedad ServiceBehaviorAttribute|Valor del árbol de descripción afectado|  
|---------------------------------------|-------------------------------------|  
|nombre|<xref:System.ServiceModel.Description.ServiceDescription.Name%2A>|  
|Espacio de nombres|<xref:System.ServiceModel.Description.ServiceDescription.Namespace%2A>|  
|ConfigurationName|<xref:System.ServiceModel.Description.ServiceDescription.ConfigurationName%2A>|  
|IgnoreExtensionDataObject|Establece la propiedad <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior.IgnoreExtensionDataObject%2A> para todas las operaciones.|  
|MaxItemsInObjectGraph|Establece la propiedad <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior.MaxItemsInObjectGraph%2A> para todas las operaciones.|  
  
|Propiedad ServiceContractAttribute|Valor del árbol de descripción afectado|  
|---------------------------------------|-------------------------------------|  
|CallbackContract|<xref:System.ServiceModel.Description.ContractDescription.CallbackContractType%2A>, <xref:System.ServiceModel.Description.MessageDescription> agregó a todas las operaciones <xref:System.ServiceModel.Description.OperationDescription.Messages%2A>.|  
|ConfigurationName|<xref:System.ServiceModel.Description.ContractDescription.ConfigurationName%2A>|  
|ProtectionLevel|<xref:System.ServiceModel.Description.ContractDescription.ProtectionLevel%2A> y posiblemente niveles secundarios de protección. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]la jerarquía de nivel de protección, consulte [nivel de protección descripción](../../../../docs/framework/wcf/understanding-protection-level.md).|  
|SessionMode|<xref:System.ServiceModel.Description.ContractDescription.SessionMode%2A>|  
  
|Valor ServiceKnownTypesAttribute|Valor del árbol de descripción afectado|  
|--------------------------------------|-------------------------------------|  
|MethodName|<xref:System.ServiceModel.Description.OperationDescription.KnownTypes%2A>|  
  
|Valor OperationContractAttribute|Valor del árbol de descripción afectado|  
|--------------------------------------|-------------------------------------|  
|Acción|<xref:System.ServiceModel.Description.MessageDescription.Action%2A> para el mensaje de salida o de entrada, dependiendo del contrato/contrato de devolución de llamada.|  
|AsyncPattern|Si es true, <xref:System.ServiceModel.Description.OperationDescription.BeginMethod%2A> y <xref:System.ServiceModel.Description.OperationDescription.EndMethod%2A>|  
|IsOneWay|Se asigna a una sola <xref:System.ServiceModel.Description.MessageDescription> en <xref:System.ServiceModel.Description.OperationDescription.Messages%2A>|  
|IsInitiating|<xref:System.ServiceModel.Description.OperationDescription.IsInitiating%2A>|  
|IsTerminating|<xref:System.ServiceModel.Description.OperationDescription.IsTerminating%2A>|  
|nombre|<xref:System.ServiceModel.Description.OperationDescription.Name%2A>|  
|ProtectionLevel|<xref:System.ServiceModel.Description.OperationDescription.ProtectionLevel%2A> y posiblemente niveles secundarios de protección. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]la jerarquía de nivel de protección, consulte [nivel de protección descripción](../../../../docs/framework/wcf/understanding-protection-level.md).|  
|ReplyAction|<xref:System.ServiceModel.Description.MessageDescription.Action%2A> para el mensaje de salida o de entrada, dependiendo del contrato/contrato de devolución de llamada.|  
  
|Valor FaultContractAttribute|Valor del árbol de descripción afectado|  
|----------------------------------|-------------------------------------|  
|Acción|<xref:System.ServiceModel.Description.FaultDescription.Action%2A> dependiendo del contrato/contrato de devolución de llamada.|  
|DetailType|<xref:System.ServiceModel.Description.FaultDescription.DetailType%2A>|  
|nombre|<xref:System.ServiceModel.Description.FaultDescription.Name%2A>|  
|Espacio de nombres|<xref:System.ServiceModel.Description.FaultDescription.Namespace%2A>|  
|ProtectionLevel|<xref:System.ServiceModel.Description.FaultDescription.ProtectionLevel%2A>|  
  
|Valor DataContractFormatAttribute|Valor del árbol de descripción afectado|  
|---------------------------------------|-------------------------------------|  
|Usar|El valor <xref:System.ServiceModel.DataContractFormatAttribute.Style%2A> está definido en el <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior> de la operación.|  
  
|Valor XmlSerializerFormatAttribute|Valor del árbol de descripción afectado|  
|----------------------------------------|-------------------------------------|  
|Estilo|Esta propiedad <xref:System.ServiceModel.XmlSerializerFormatAttribute> está definida en el <xref:System.ServiceModel.Description.XmlSerializerOperationBehavior> de la operación.|  
|Usar|El <xref:System.ServiceModel.XmlSerializerFormatAttribute> está definido en el <xref:System.ServiceModel.Description.XmlSerializerOperationBehavior> de la operación.|  
  
|Valor TransactionFlowAttribute|Valor del árbol de descripción afectado|  
|------------------------------------|-------------------------------------|  
|TransactionFlowOption|El <xref:System.ServiceModel.TransactionFlowAttribute> se agrega como un comportamiento de operación para la propiedad <xref:System.ServiceModel.Description.OperationDescription.Behaviors%2A>.|  
  
|Valor MessageContractAttribute|Valor del árbol de descripción afectado|  
|------------------------------------|-------------------------------------|  
|ProtectionLevel|<xref:System.ServiceModel.Description.MessageDescription.ProtectionLevel%2A>|  
|WrapperName|<xref:System.ServiceModel.Description.MessageBodyDescription.WrapperName%2A>|  
|WrapperNamespace|<xref:System.ServiceModel.Description.MessageBodyDescription.WrapperNamespace%2A>|  
  
|Valor MessageHeaderAttribute|Valor del árbol de descripción afectado|  
|----------------------------------|-------------------------------------|  
|Actor|<xref:System.ServiceModel.Description.MessageHeaderDescription.Actor%2A>para el encabezado correspondiente en<xref:System.ServiceModel.Description.MessageDescription.Headers%2A>|  
|MustUnderstand|<xref:System.ServiceModel.Description.MessageHeaderDescription.MustUnderstand%2A>para el encabezado correspondiente en<xref:System.ServiceModel.Description.MessageDescription.Headers%2A>|  
|nombre|<xref:System.ServiceModel.Description.MessagePartDescription.Name%2A>para el encabezado correspondiente en<xref:System.ServiceModel.Description.MessageDescription.Headers%2A>|  
|Espacio de nombres|<xref:System.ServiceModel.Description.MessagePartDescription.Namespace%2A>para el encabezado correspondiente en<xref:System.ServiceModel.Description.MessageDescription.Headers%2A>|  
|ProtectionLevel|<xref:System.ServiceModel.Description.MessagePartDescription.ProtectionLevel%2A>para el encabezado correspondiente en<xref:System.ServiceModel.Description.MessageDescription.Headers%2A>|  
|Relé|<xref:System.ServiceModel.Description.MessageHeaderDescription.Relay%2A>para el encabezado correspondiente en<xref:System.ServiceModel.Description.MessageDescription.Headers%2A>|  
  
|Valor MessageBodyMemberAttribute|Valor del árbol de descripción afectado|  
|--------------------------------------|-------------------------------------|  
|nombre|<xref:System.ServiceModel.Description.MessagePartDescription.Name%2A>para el elemento correspondiente en<xref:System.ServiceModel.Description.MessageBodyDescription.Parts%2A>|  
|Espacio de nombres|<xref:System.ServiceModel.Description.MessagePartDescription.Namespace%2A>para el elemento correspondiente en<xref:System.ServiceModel.Description.MessageBodyDescription.Parts%2A>|  
|Ordenar|<xref:System.ServiceModel.Description.MessagePartDescription.Index%2A>para el elemento correspondiente en<xref:System.ServiceModel.Description.MessageBodyDescription.Parts%2A>|  
|ProtectionLevel|<xref:System.ServiceModel.Description.MessagePartDescription.ProtectionLevel%2A>para el elemento correspondiente en<xref:System.ServiceModel.Description.MessageBodyDescription.Parts%2A>|  
  
|Valor MessageHeaderArrayAttribute|Valor del árbol de descripción afectado|  
|---------------------------------------|-------------------------------------|  
|Actor|<xref:System.ServiceModel.Description.MessageHeaderDescription.Actor%2A>|  
|MustUnderstand|<xref:System.ServiceModel.Description.MessageHeaderDescription.MustUnderstand%2A>|  
|nombre|<xref:System.ServiceModel.Description.MessagePartDescription.Name%2A>|  
|Espacio de nombres|<xref:System.ServiceModel.Description.MessagePartDescription.Namespace%2A>|  
|ProtectionLevel|<xref:System.ServiceModel.Description.MessagePartDescription.ProtectionLevel%2A>|  
|Relé|<xref:System.ServiceModel.Description.MessageHeaderDescription.Relay%2A>|  
  
|Valor MessagePropertyAttribute|Valor del árbol de descripción afectado|  
|------------------------------------|-------------------------------------|  
|nombre|<xref:System.ServiceModel.Description.MessagePartDescription.Name%2A>|  
  
|Valor MessageParameterAttribute|Valor del árbol de descripción afectado|  
|-------------------------------------|-------------------------------------|  
|nombre|<xref:System.ServiceModel.Description.MessagePartDescription.Name%2A>para el elemento correspondiente en<xref:System.ServiceModel.Description.MessageBodyDescription.Parts%2A>|  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]cómo se convierten los valores del árbol de descripción en metadatos, vea [ServiceDescription y referencias WSDL](../../../../docs/framework/wcf/feature-details/servicedescription-and-wsdl-reference.md).  
  
## <a name="see-also"></a>Vea también  
 [ServiceDescription y referencias WSDL](../../../../docs/framework/wcf/feature-details/servicedescription-and-wsdl-reference.md)
