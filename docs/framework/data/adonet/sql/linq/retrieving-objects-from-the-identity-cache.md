---
title: "Recuperar objetos de la memoria caché de identidades"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 96c13903-ccb6-4a0e-ab6a-8ca955ca314d
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: e7677f2fcfe854aad5d01c0e024955da2480c375
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="retrieving-objects-from-the-identity-cache"></a>Recuperar objetos de la memoria caché de identidades
En este tema se describen los tipos de consultas LINQ to SQL que devuelven un objeto desde la memoria caché de identidad que está administrado por el <xref:System.Data.Linq.DataContext>.  
  
 En LINQ to SQL, una de las formas en que <xref:System.Data.Linq.DataContext> administra los objetos consiste en registrar identidades de objetos en una memoria caché de identidad a medida que se ejecutan consultas. En algunos casos, LINQ to SQL intentará recuperar un objeto desde la memoria caché de identidad antes de ejecutar una consulta en la base de datos.  
  
 En general, para que una consulta LINQ to SQL devuelva un objeto desde la memoria caché de identidad, la consulta debe estar basada en la clave principal de un objeto y debe devolver un único objeto. En particular, la consulta debe estar en uno de los formatos generales indicados a continuación.  
  
> [!NOTE]
>  Las consultas precompiladas no devolverán objetos desde la memoria caché de identidad. Para obtener más información acerca de las consultas precompiladas, consulte <xref:System.Data.Linq.CompiledQuery> y [Cómo: almacén y reutilizar consultas](../../../../../../docs/framework/data/adonet/sql/linq/how-to-store-and-reuse-queries.md).  
  
 Para recuperar un objeto de la memoria caché de identidad, una consulta debe tener uno de los formatos generales siguientes:  
  
-   <xref:System.Data.Linq.Table%601> `.Function1(` `predicate` `)`  
  
-   <xref:System.Data.Linq.Table%601> `.Function1(` `predicate` `).Function2()`  
  
 En estos formatos generales, `Function1`, `Function2` y `predicate` se definen como se indica a continuación.  
  
 `Function1` puede ser de cualquiera de las funciones siguientes:  
  
-   <xref:System.Linq.Queryable.Where%2A>  
  
-   <xref:System.Linq.Queryable.First%2A>  
  
-   <xref:System.Linq.Queryable.FirstOrDefault%2A>  
  
-   <xref:System.Linq.Queryable.Single%2A>  
  
-   <xref:System.Linq.Queryable.SingleOrDefault%2A>  
  
 `Function2` puede ser de cualquiera de las funciones siguientes:  
  
-   <xref:System.Linq.Queryable.First%2A>  
  
-   <xref:System.Linq.Queryable.FirstOrDefault%2A>  
  
-   <xref:System.Linq.Queryable.Single%2A>  
  
-   <xref:System.Linq.Queryable.SingleOrDefault%2A>  
  
 `predicate` debe ser una expresión en la que la propiedad de la clave principal del objeto está establecida en un valor constante. Si un objeto tiene una clave principal definida mediante más de una propiedad, cada una de estas propiedades debe estar establecida en un valor constante. A continuación, se ofrecen ejemplos del formato que debe tener `predicate`:  
  
-   `c => c.PK == constant_value`  
  
-   `c => c.PK1 == constant_value1 && c=> c.PK2 == constant_value2`  
  
## <a name="example"></a>Ejemplo  
 El código siguiente proporciona ejemplos de los tipos de consultas LINQ to SQL que recuperan un objeto desde la memoria caché de identidad.  
  
 [!code-csharp[L2S_QueryCache#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/l2s_querycache/cs/program.cs#1)]
 [!code-vb[L2S_QueryCache#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/l2s_querycache/vb/module1.vb#1)]  
  
## <a name="see-also"></a>Vea también  
 [Conceptos sobre consultas](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)  
 [Identidad de objetos](../../../../../../docs/framework/data/adonet/sql/linq/object-identity.md)  
 [Información general](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)  
 [Identidad de objetos](../../../../../../docs/framework/data/adonet/sql/linq/object-identity.md)
