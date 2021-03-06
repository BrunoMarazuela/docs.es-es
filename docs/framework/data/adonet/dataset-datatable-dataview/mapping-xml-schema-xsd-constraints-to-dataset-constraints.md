---
title: Asignar restricciones de un esquema XML (XSD) a restricciones de conjuntos de datos
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3d0d1a4b-9104-434f-ac04-6c01ab5716b5
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: f403dc974e4fe67d239688f587061cd23a8deff6
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="mapping-xml-schema-xsd-constraints-to-dataset-constraints"></a>Asignar restricciones de un esquema XML (XSD) a restricciones de conjuntos de datos
El lenguaje de definición de esquemas XML (XSD) permite especificar restricciones para los elementos y atributos que define. Al asignar un esquema XML al esquema relacional de un <xref:System.Data.DataSet>, restricciones de esquema XML se asignan a las restricciones relacionales apropiadas en las tablas y columnas dentro de la **conjunto de datos**.  
  
 En esta sección se describe la asignación de las siguientes restricciones de esquema XML:  
  
-   La restricción de unicidad especificada mediante el **único** elemento.  
  
-   La restricción de clave especificada mediante la **clave** elemento.  
  
-   La restricción keyref especificada mediante el **keyref** elemento.  
  
 El uso de una restricción sobre un elemento o un atributo permite especificar ciertas restricciones para los valores del elemento en cualquier instancia del documento. Por ejemplo, una restricción de clave en un **CustomerID** elemento secundario de un **cliente** elemento en el esquema indica que los valores de la **CustomerID** debe ser el elemento secundario único en cualquier instancia del documento, y que no se permiten valores null.  
  
 También se pueden especificar restricciones entre los elementos y atributos de un documento para establecer una relación dentro del documento. Las restricciones key y keyref se utilizan en el esquema para especificar las restricciones dentro del documento, lo que da como resultado una relación entre los elementos y atributos del documento.  
  
 El proceso de asignación convierte estas restricciones del esquema en las restricciones apropiadas para las tablas creadas dentro de la **conjunto de datos**.  
  
## <a name="in-this-section"></a>En esta sección  
 [Asignación de restricciones UNIQUE de un esquema XML (XSD) a restricciones de conjuntos de datos](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-unique-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Describe los elementos de esquema XML utilizados para crear restricciones únicas en un **conjunto de datos**.  
  
 [Asignación de restricciones KEY de un esquema XML (XSD) a restricciones de conjuntos de datos](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-key-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Describe los elementos de esquema XML utilizados para crear restricciones de clave (restricciones únicas donde no se permiten valores null) en un **conjunto de datos**.  
  
 [Asignación de restricciones KEYREF de un esquema XML (XSD) a restricciones de conjuntos de datos](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-keyref-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Describe los elementos de esquema XML utilizados para crear restricciones (clave externa) en keyref un **conjunto de datos**.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Derivación de una estructura relacional de un conjunto de datos a partir de un esquema XML (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 Describe la estructura relacional, o esquema, de un **conjunto de datos** creado a partir de un esquema XSD.  
  
 [Generación de relaciones de objetos DataSet en un esquema XML (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 Describe los elementos de esquema XML utilizados para crear relaciones entre columnas de tabla en una **conjunto de datos**.  
  
## <a name="see-also"></a>Vea también  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
