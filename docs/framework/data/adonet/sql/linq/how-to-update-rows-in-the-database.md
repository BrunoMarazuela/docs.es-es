---
title: "Cómo: Actualizar filas en la base de datos"
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
ms.assetid: a2b5c90f-6cc3-4128-bfab-1db488d5af26
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 62c1ac16ab2d8607c7dd505bf4cb68f475dc26a7
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-update-rows-in-the-database"></a>Cómo: Actualizar filas en la base de datos
Puede actualizar las filas en una base de datos mediante la modificación de valores de miembro de los objetos asociados a la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601> colección y, a continuación, enviar los cambios a la base de datos. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]Convierte los cambios en el código SQL apropiado `UPDATE` comandos.  
  
> [!NOTE]
>  Puede invalidar los métodos predeterminados de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] para las operaciones de base de datos `Insert`, `Update` y `Delete`. Para obtener más información, consulte [personalizar operaciones de inserción, actualización y eliminar](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).  
>   
>  Los desarrolladores de [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] pueden usar el [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] para desarrollar procedimientos almacenados con el mismo propósito.  
  
 En los pasos siguientes se asume que un objeto <xref:System.Data.Linq.DataContext> válido le conecta a la base de datos Northwind. Para obtener más información, consulte [Cómo: conectarse a una base de datos](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md).  
  
### <a name="to-update-a-row-in-the-database"></a>Para actualizar una fila de la base de datos  
  
1.  Consulte en la base de datos la fila que se va a actualizar.  
  
2.  Realice los cambios deseados en los valores de miembro en el objeto [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] resultante.  
  
3.  Envíe los cambios a la base de datos.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se consulta en la base de datos el pedido #11000 y, a continuación, se cambian los valores de `ShipName` y `ShipVia` en el objeto `Order` resultante. Finalmente, los cambios en estos valores de miembro se envían a la base de datos como cambios en las columnas `ShipName` y `ShipVia`.  
  
 [!code-csharp[System.Data.Linq.Table#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#2)]
 [!code-vb[System.Data.Linq.Table#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#2)]  
  
## <a name="see-also"></a>Vea también  
 [Administración de conflictos de cambios](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)  
 [Cómo: asignar procedimientos almacenados para realizar actualizaciones, inserciones y eliminaciones (Object Relational Designer)](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)  
 [Realización y envío de cambios de datos](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
