---
title: "Ответственность разработчика при переопределении поведения по умолчанию"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c6909ddd-e053-46a8-980c-0e12a9797be1
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 7de5dbcad14ebfd253ba99f03a8d77e768f29941
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="responsibilities-of-the-developer-in-overriding-default-behavior"></a>Ответственность разработчика при переопределении поведения по умолчанию
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]не обеспечивают следующие требования, но поведение не определено, если эти требования не выполнены.  
  
-   Метод переопределения не должен вызывать методы <xref:System.Data.Linq.DataContext.SubmitChanges%2A> и <xref:System.Data.Linq.Table%601.Attach%2A>. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]вызывает исключение, если эти методы вызываются в методе переопределения.  
  
-   Методы переопределения нельзя использовать для начала, фиксации или остановки транзакции. Операция <xref:System.Data.Linq.DataContext.SubmitChanges%2A> выполняется в составе транзакции. Внутренняя вложенная транзакция может помешать выполнения внешней транзакции. Методы переопределения загрузки могут начать транзакцию, лишь определив, что операция не выполняется в рамках <xref:System.Transactions.Transaction>.  
  
-   Ожидается, что методы переопределения соответствуют применимому сопоставлению оптимистического параллелизма. Ожидается, что при возникновении конфликта оптимистичного параллелизма метод переопределения вызывает исключение <xref:System.Data.Linq.ChangeConflictException>. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]перехватывает это исключение, чтобы возможность правильно обработать <xref:System.Data.Linq.DataContext.SubmitChanges%2A> переданный методу <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.  
  
-   Ожидается, что методы переопределения операций создания (`Insert`) и обновления (`Update`) отправляют значения созданных базой данных столбцов обратно соответствующим членам объекта при успешном завершении операции.  
  
     Например если `Order.OrderID` сопоставляется со столбцом идентификаторов (*autoincrement* первичный ключ), то `InsertOrder()` переопределяющий метод должен получить идентификатор генерируемые базой данных и задать `Order.OrderID` член с этим идентификатором. Аналогичным образом, чтобы гарантировать согласованность обновленных объектов, члены меток времени должны обновляться значениями меток времени, созданными базой данных. Если не распространить созданные базой данных значения на члены, может возникнуть несогласованность между базой данных и объектами, отслеживаемыми классом <xref:System.Data.Linq.DataContext>.  
  
-   Пользователь обязан вызвать правильный динамический API-интерфейс. Например, в методе переопределения обновления может быть вызван только метод <xref:System.Data.Linq.DataContext.ExecuteDynamicUpdate%2A>. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] не обнаруживает и не проверяет вызванный динамический метод на предмет соответствия применяемой операции. Если вызывается неприменимый метод (например, метод <xref:System.Data.Linq.DataContext.ExecuteDynamicDelete%2A> для обновления объекта), результаты не определены.  
  
-   Наконец, ожидается, что метод переопределения выполняет объявленную операцию. Семантика операций [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], таких как безотложная загрузка, отложенная загрузка и <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, требует, чтобы переопределения предоставляли объявленные службы. Например, переопределение загрузки, которое лишь возвращает пустую коллекцию без проверки содержимого в базе данных, скорее всего, приведет к несогласованности данных.  
  
## <a name="see-also"></a>См. также  
 [Настройка операций вставки, обновления и удаления](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)
