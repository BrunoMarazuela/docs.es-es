---
title: Consultas de LINQ to SQL
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f4897aaa-7f44-4c20-a471-b948c2971aae
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 8c32ff4040213ce73b78f7ea0f6d56e222d55b25
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="linq-to-sql-queries"></a>Consultas de LINQ to SQL
Las consultas [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] se definen utilizando la misma sintaxis que utilizaría en [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)]. La única diferencia es que los objetos a los que se hace referencia en las consultas se asignan a elementos de una base de datos. Para obtener más información, vea [Introduction to LINQ queries (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md) [Introducción a las consultas LINQ (C#)].  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] convierte las consultas que se escriben en consultas SQL equivalentes y las envía al servidor para su procesamiento. Más específicamente, la aplicación utiliza la API de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] para solicitar la ejecución de la consulta. Después, el proveedor [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] transforma la consulta en texto SQL y delega la ejecución al proveedor ADO. El proveedor ADO devuelve los resultados de la consulta como `DataReader`. El [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] proveedor convierte los resultados de ADO en una <xref:System.Linq.IQueryable> colección de objetos de usuario.  
  
> [!NOTE]
>  La mayoría de los métodos y operadores de los tipos integrados de [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] tienen equivalentes directos en SQL. Los que [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] no puede convertir generan excepciones en tiempo de ejecución. Para obtener más información, consulte [asignación de tipo de CLR de SQL](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md).  
  
 La tabla siguiente muestra las similitudes y diferencias entre los elementos de las consultas [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] y [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
|Item|Consulta LINQ|Consulta [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]|  
|----------|----------------|----------------------------------------------------------------------|  
|Tipo de valor devuelto de la variable local que contiene la consulta (para las consultas que devuelven secuencias)|`IEnumerable` genérico|`IQueryable` genérico|  
|Especificar el origen de datos|Usa el `From` ([!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) o `from` cláusula (C#)|Igual|  
|Filtrado|Usa el `Where` / `where` cláusula|Igual|  
|Agrupar|Usa el `Group…By` / `groupby` cláusula|Igual|  
|Seleccionar (proyectar)|Usa el `Select` / `select` cláusula|Igual|  
|Ejecución diferida frente a ejecución inmediata|Vea [Introducción a las consultas LINQ (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)|Igual|  
|Implementar combinaciones|Usa el `Join` / `join` cláusula|Puede usar el `Join` / `join` cláusula, pero más eficazmente usa el <xref:System.Data.Linq.Mapping.AssociationAttribute> atributo. Para obtener más información, consulte [consultas en varias relaciones](../../../../../../docs/framework/data/adonet/sql/linq/querying-across-relationships.md).|  
|Ejecución remota frente a ejecución local||Para obtener más información, vea [vs remotos. Ejecución local](../../../../../../docs/framework/data/adonet/sql/linq/remote-vs-local-execution.md).|  
|Consultas con transmisión por frecuencias frente a consultas con almacenamiento en caché|No aplicable en un escenario de memoria local||  
  
## <a name="see-also"></a>Vea también  
 [Introducción a las consultas LINQ (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)  
 [Operaciones básicas de consulta LINQ](~/docs/csharp/programming-guide/concepts/linq/basic-linq-query-operations.md)  
 [Relaciones entre tipos en las operaciones de consulta LINQ](~/docs/csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md)  
 [Conceptos sobre consultas](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
