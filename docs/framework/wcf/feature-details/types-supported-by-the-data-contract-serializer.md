---
title: Tipos admitidos por el serializador de contrato de datos
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- serialization [WCF], supported types
ms.assetid: 7381b200-437a-4506-9556-d77bf1bc3f34
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 98eb46e0f31995efe7db177d90691a9f59288590
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="types-supported-by-the-data-contract-serializer"></a>Tipos admitidos por el serializador de contrato de datos
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] utiliza <xref:System.Runtime.Serialization.DataContractSerializer> como su motor de serialización predeterminado para convertir los datos en XML y viceversa. <xref:System.Runtime.Serialization.DataContractSerializer> está diseñado para serializar los tipos de *contrato de datos* . Sin embargo, admite muchos otros tipos, de los que se puede pensar que tienen un contrato de datos implícito. A continuación, se muestra una lista completa de los tipos que se pueden serializar:  
  
-   Todos los tipos públicamente visibles que tienen un constructor que no tiene parámetros.  
  
-   Tipo de contrato de datos Éstos son tipos a los que se ha aplicado el atributo <xref:System.Runtime.Serialization.DataContractAttribute> . Normalmente, los tipos personalizados que representan objetos de negocio se deberían crear como tipos de contrato de datos. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Usar contratos de datos](../../../../docs/framework/wcf/feature-details/using-data-contracts.md) y [tipos serializables](../../../../docs/framework/wcf/feature-details/serializable-types.md).  
  
-   Tipos de colección. Éstos son tipos que representan listas de datos. Éstas pueden ser matrices normales de tipos o tipos de colección, como <xref:System.Collections.ArrayList> y <xref:System.Collections.Generic.Dictionary%602>. El atributo <xref:System.Runtime.Serialization.CollectionDataContractAttribute> se puede utilizar para personalizar la serialización de estos tipos, pero no se requiere. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Tipos de colección en contratos de datos](../../../../docs/framework/wcf/feature-details/collection-types-in-data-contracts.md).  
  
-   Tipos de enumeración. Las enumeraciones, incluidas las de marcas, son serializables. Opcionalmente, los tipos de enumeración se pueden marcar con el atributo <xref:System.Runtime.Serialization.DataContractAttribute> , en cuyo caso cada miembro que participe en la serialización se debe marcar con el atributo <xref:System.Runtime.Serialization.EnumMemberAttribute> . No se serializan los miembros que no están marcados. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Tipos de enumeración en contratos de datos](../../../../docs/framework/wcf/feature-details/enumeration-types-in-data-contracts.md).  
  
-   Tipos primitivos de .NET Framework. Los tipos siguientes integrados en .NET Framework pueden serializarse y se consideran como tipos primitivos: <xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.Int32>, <xref:System.Int64>, <xref:System.UInt16>, <xref:System.UInt32>, <xref:System.UInt64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Boolean>, <xref:System.Char>, <xref:System.Decimal>, <xref:System.Object>y <xref:System.String>.  
  
-   Otros tipos primitivos. Estos tipos no son primitivos en .NET Framework, pero se tratan como primitivos en forma de XML serializado. Estos tipos son <xref:System.DateTime>, <xref:System.DateTimeOffset>, <xref:System.TimeSpan>, <xref:System.Guid>, <xref:System.Uri>, <xref:System.Xml.XmlQualifiedName>y matrices de <xref:System.Byte>.  
  
    > [!NOTE]
    >  A diferencia de otros tipos primitivos, <xref:System.DateTimeOffset> no es de un tipo conocido de forma predeterminada. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Tipos conocidos de contrato de datos](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)).  
  
-   Tipos marcados con el atributo <xref:System.SerializableAttribute> . Muchos tipos incluidos en la biblioteca de clases base de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] se clasifican en esta categoría. <xref:System.Runtime.Serialization.DataContractSerializer> admite totalmente este modelo de programación de serialización que fue utilizado por la comunicación remota de .NET Framework, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>y <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>, incluida la compatibilidad para la interfaz <xref:System.Runtime.Serialization.ISerializable> .  
  
-   Tipos que representan XML sin formato o tipos que representan datos relacionales [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] . <xref:System.Xml.XmlElement> y la matriz de tipos <xref:System.Xml.XmlNode> se admiten como una manera de representar XML directamente. De manera adicional, se admiten los tipos que implementan la interfaz <xref:System.Xml.Serialization.IXmlSerializable> , incluido el atributo relacionado <xref:System.Xml.Serialization.XmlSchemaProviderAttribute> y los tipos <xref:System.Xml.Linq.XDocument> y <xref:System.Xml.Linq.XElement> . El atributo [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]<xref:System.Data.DataTable> y <xref:System.Data.DataSet> , así como sus clases derivadas de tipo, implementan la interfaz <xref:System.Xml.Serialization.IXmlSerializable> y, por consiguiente, entran dentro de esta categoría. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Tipos XML y ADO.NET en contratos de datos](../../../../docs/framework/wcf/feature-details/xml-and-ado-net-types-in-data-contracts.md).  
  
## <a name="limitations-of-using-certain-types-in-partial-trust-mode"></a>Limitaciones del uso de ciertos tipos en modo de confianza parcial  
 A continuación, se enumeran las limitaciones que existen al utilizar ciertos tipos en escenarios de modo de confianza parcial:  
  
-   Para serializar o deserializar un tipo que implementa <xref:System.Runtime.Serialization.ISerializable> en código de confianza parcial mediante el uso de <xref:System.Runtime.Serialization.DataContractSerializer> se requieren los permisos <xref:System.Security.Permissions.SecurityPermissionAttribute.SerializationFormatter%2A> y <xref:System.Security.Permissions.SecurityPermissionAttribute.UnmanagedCode%2A> .  
  
-   Al ejecutar el código [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] en el modo [Partial Trust](../../../../docs/framework/wcf/feature-details/partial-trust.md) , la serialización y deserialización de los campos `readonly` (tanto `public` y `private`) no es compatible. Esto se debe a que el IL generado no se puede comprobar y, por consiguiente, requiere permisos elevados.  
  
-   Tanto <xref:System.Runtime.Serialization.DataContractSerializer> como <xref:System.Xml.Serialization.XmlSerializer> se admiten en un entorno de confianza parcial. Sin embargo, el uso de <xref:System.Runtime.Serialization.DataContractSerializer> está sujeto a las condiciones siguientes:  
  
    -   Todos los tipos `[DataContract]` serializables deben ser públicos.  
  
    -   Todos los campos `[DataMember]` serializables o propiedades en un tipo `[DataContract]` deben ser públicos y de lectura/escritura. No se admite la serialización y deserialización de los campos `readonly` al ejecutar [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] en una aplicación de confianza parcial.  
  
    -   El atributo `[Serializable]`/`ISerializable]` no se admite en un entorno de confianza parcial.  
  
    -   Los tipos conocidos se deben especificar mediante código o configuración del nivel de equipo (`Machine.config`). Los tipos conocidos no se pueden especificar en la configuración del nivel de de aplicación por razones de seguridad.  
  
-   Los tipos que implementan <xref:System.Runtime.Serialization.IObjectReference> producirán una excepción en un entorno de confianza parcial porque el método <xref:System.Runtime.Serialization.IObjectReference.GetRealObject%2A> requiere el permiso de seguridad `[SecurityPermission(SecurityAction.LinkDemand, Flags=SecurityPermissionFlag.SerializationFormatter)]`.  
  
## <a name="additional-notes-on-serialization"></a>Notas adicionales sobre serialización  
 Las reglas siguientes también se aplican a los tipos admitidos por el serializador de contrato de datos:  
  
-   El serializador del contrato de datos admite totalmente los tipos genéricos.  
  
-   El serializador del contrato de datos admite totalmente los tipos NULL.  
  
-   Los tipos de interfaz se tratan como <xref:System.Object> o, en el caso de interfaces de colección, como tipos de colección.  
  
-   Se admiten tanto las estructuras como las clases.  
  
-   <xref:System.Runtime.Serialization.DataContractSerializer> no admite el modelo de programación utilizado por los servicio web <xref:System.Xml.Serialization.XmlSerializer> y [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] . En particular, no admite atributos como <xref:System.Xml.Serialization.XmlElementAttribute> y <xref:System.Xml.Serialization.XmlAttributeAttribute>. Para habilitar la compatibilidad de este modelo de programación, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se deben cambiar para que use <xref:System.Xml.Serialization.XmlSerializer> en lugar de <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
-   El tipo <xref:System.DBNull> se trata de una manera especial. Es un tipo singleton y tras la deserialización, el deserializador respeta la restricción de singleton y señala todas las referencias `DBNull` a la instancia de singleton. Dado que `DBNull` es un tipo serializable, exige permiso <xref:System.Security.Permissions.SecurityPermissionAttribute.SerializationFormatter%2A> .  
  
## <a name="see-also"></a>Vea también  
 [Tipos de XML y ADO.NET en contratos de datos](../../../../docs/framework/wcf/feature-details/xml-and-ado-net-types-in-data-contracts.md)  
 [Utilización de contratos de datos](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)  
 [Tipos serializables](../../../../docs/framework/wcf/feature-details/serializable-types.md)  
 [Tipos de colección en contratos de datos](../../../../docs/framework/wcf/feature-details/collection-types-in-data-contracts.md)  
 [Tipos de enumeración en contratos de datos](../../../../docs/framework/wcf/feature-details/enumeration-types-in-data-contracts.md)
