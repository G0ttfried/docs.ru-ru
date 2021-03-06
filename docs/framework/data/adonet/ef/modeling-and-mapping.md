---
title: "Моделирование и сопоставление"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ec8a9515-3708-4cde-a688-4d8e6975f150
caps.latest.revision: "7"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 0782d75aa44557ef87f1d59757b0d60873d8a949
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="modeling-and-mapping"></a>Моделирование и сопоставление
Платформа [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] позволяет определить концептуальную модель, модель хранения и сопоставление между ними, которые оптимальным образом подходят для приложения. Средства модели EDM в [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)] позволяют создавать.[ EDMX-файла](http://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4) из базы данных или графической модели и обновите его при изменении модели или базы данных.  
  
 Начиная с версии 4.1 платформы Entity Framework модель можно также создавать программно с помощью шаблона разработки Code First. Шаблон разработки Code First имеет два различных сценария. В обоих случаях разработчик определяет модель, задавая в коде определения классов .NET Framework, а затем выборочно определяет дополнительные сопоставления или конфигурации с помощью заметок к данным или fluent API.  
  
 Дополнительные сведения см. в разделе [Создание и сопоставление концептуальной модели](http://go.microsoft.com/fwlink/?LinkId=235016).  
  
 Можно также использовать генератор модели EDM, который входит в состав [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)]. Программа EdmGen.exe формирует файлы языка CSDL, SSDL и MSL на основе существующего источника данных. Можно также вручную создать содержимое модели и сопоставления. Дополнительные сведения см. в разделе [генератор модели EDM (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md).
