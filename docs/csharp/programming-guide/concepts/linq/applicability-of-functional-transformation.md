---
title: "Применимость функциональных преобразований (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: c78107bd-b006-4574-a3d4-bbf808388ff3
caps.latest.revision: "4"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c7196e128a6d61b2b28e955a79561db2b9a5e51b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="applicability-of-functional-transformation-c"></a>Применимость функциональных преобразований (C#)
Чисто функциональные преобразования применяются в самых разнообразных ситуациях.  
  
 Подход с использованием функциональных преобразований идеально подходит для запросов и управления структурированными данными, поэтому вполне соответствует технологиям LINQ. Но функциональные преобразования могут применяться гораздо шире, чем только в LINQ. Любой процесс, основной задачей которого является преобразование данных из одной формы в другую, может считаться применимым для функционального преобразования.  
  
 Этот подход можно использовать при решении многих задач, даже если на первый взгляд кажется, что он неприменим. Применение функциональных преобразований в сочетании с технологиями LINQ или без них должно рассматриваться при работе со следующими объектами.  
  
-   Документы на основе XML. Имеющие правильный формат данные на любом диалекте языка XML могут быть легко подвергнуты функциональным преобразованиям. Дополнительные сведения см. в разделе [Функциональное преобразование XML (C#)](../../../../csharp/programming-guide/concepts/linq/functional-transformation-of-xml.md).  
  
-   Другие структурированные форматы файлов. Большинство файлов, от Windows.ini до обычных текстовых документов, имеют определенную структуру, которую можно анализировать и преобразовывать.  
  
-   Протоколы потоковых данных. Кодирование и декодирование данных в коммуникационных протоколах часто можно представить в виде простого функционального преобразования.  
  
-   Данные RDBMS и OODBMS. Реляционные и объектно-ориентированные базы данных, как и XML, являются широко используемыми структурированными источниками данных.  
  
-   Математические, статистические и научные решения. В этих областях происходит обработка больших наборов данных, чтобы пользователь мог представлять визуально, оценивать или действительно решить нетривиальные задачи.  
  
 Как описано в разделе [Рефакторинг в чистые функции (C#)](../../../../csharp/programming-guide/concepts/linq/refactoring-into-pure-functions.md), использование чистых функций является примером функционального программирования. Кроме очевидных преимуществ чистых функций, их применение позволяет получить ценный опыт решения проблем с точки зрения применения функциональных преобразований. Такой подход может серьезно повлиять на стиль программирования и конструирования классов. Это особенно важно, если задача легко решается путем преобразования данных, как описано выше.  
  
 Безусловно, это не относится к теме данного учебника, но следует отметить, что проекты, разработанные с учетом возможностей функциональных преобразований, чаще всего бывают сосредоточены на применении в качестве действующих факторов процессов, а не объектов, а полученное в результате решение чаще всего бывает реализовано как ряд крупномасштабных преобразований, а не как изменения состояний отдельных объектов.  
  
 Следует также помнить, что C# поддерживает как императивный, так и функциональный подход, поэтому в приложении целесообразнее всего сочетать элементы обоих стилей программирования.  
  
## <a name="see-also"></a>См. также  
 [Введение в чистые функциональные преобразования (C#)](../../../../csharp/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)  
 [Функциональное преобразование XML (C#)](../../../../csharp/programming-guide/concepts/linq/functional-transformation-of-xml.md)  
 [Рефакторинг в чистые функции (C#)](../../../../csharp/programming-guide/concepts/linq/refactoring-into-pure-functions.md)
