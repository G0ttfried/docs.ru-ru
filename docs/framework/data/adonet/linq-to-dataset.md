---
title: LINQ to DataSet
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 743e3755-3ecb-45a2-8d9b-9ed41f0dcf17
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: cdd3f21d8b02c24db24d2efd08487ef1a290e022
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="linq-to-dataset"></a>LINQ to DataSet
[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] упрощает и ускоряет запросы к данным, кэшированным в объекте <xref:System.Data.DataSet>. В частности [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] упрощает создание запросов, позволяет разработчикам писать запросы на языке программирования, а не с помощью отдельный язык запросов. Это особенно полезно для [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] разработчиков, которые теперь могут воспользоваться преимуществами проверки синтаксиса во время компиляции, статическую типизацию и поддержку технологии IntelliSense, предоставляемые [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] в запросах.  
  
 Технология [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] также может использоваться для запросов к данным, находящимся в одном или нескольких источниках. Это удовлетворяет многим сценариям, требующим гибкости при представлении и обработке данных, таких как запросы к данным, прошедшим локальную агрегатную обработку, и кэширование на среднем уровне в веб-приложениях. В частности, этот метод обработки требуется для универсальных приложений отчетности, анализа и бизнес-аналитики.  
  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] Функциональные возможности представлены в основном через методы расширения в <xref:System.Data.DataRowExtensions> и <xref:System.Data.DataTableExtensions> классы. [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]выполняет построение на и использует ее [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] архитектуры и не предназначен для замены [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] в коде приложения. Существующий код ADO.NET 2.0 продолжит работать в приложении [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]. Связь между [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] и [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] и хранилищем данных показана на следующей схеме.  
  
 ![Технология LINQ to DataSet основан на поставщике ADO.NET](../../../../docs/framework/data/adonet/media/linqtodataset.gif "LINQtoDataSet")  
  
## <a name="in-this-section"></a>В этом разделе  
 [Начало работы](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)  
  
 [Руководство по программированию](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)  
  
## <a name="reference"></a>Ссылка  
 <xref:System.Data.DataTableExtensions>  
  
 <xref:System.Data.DataRowExtensions>  
  
 <xref:System.Data.DataRowComparer>  
  
## <a name="see-also"></a>См. также  
 [Встроенный язык запросов LINQ](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)  
 [LINQ и ADO.NET](../../../../docs/framework/data/adonet/linq-and-ado-net.md)  
 [ADO.NET](../../../../docs/framework/data/adonet/index.md)
