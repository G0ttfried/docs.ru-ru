---
title: THEN (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 54222642-23c6-4f61-9861-67caca53ac5f
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: d7a669cc87c14e4213d702b639a1956f04cb485d
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="then-entity-sql"></a>THEN (Entity SQL)
Результат предложения WHEN, если оно оценивается как значение `true`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
WHEN when_expression THEN then_expression  
```  
  
## <a name="arguments"></a>Аргументы  
 `when_expression`  
 Любое допустимое выражение типа Boolean.  
  
 `then_expression`  
 Любое допустимое выражение запроса, возвращающее коллекцию.  
  
## <a name="remarks"></a>Примечания  
 Если аргумент `when_expression` оценивается как значение `true`, результатом является соответствующее значение `then-expression`. Если не выполнено ни одно из условий предложения WHEN, оценивается выражение `else-expression` . Однако, если выражение `else-expression`отсутствует, результат равен NULL.  
  
 Пример см. в разделе [случае](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md).  
  
## <a name="example"></a>Пример  
 В следующем запросе Entity SQL с помощью выражения CASE оценивается набор выражений типа `Boolean` . Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1.  Выполните процедуру, описанную в [как: выполнение запроса, возвращает результаты PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2.  Передайте следующий запрос в качестве аргумента методу `ExecutePrimitiveTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#CASE_WHEN_THEN_ELSE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#case_when_then_else)]  
  
## <a name="see-also"></a>См. также  
 [CASE](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md)  
 [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
