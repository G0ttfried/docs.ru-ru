---
title: "Dynamic Language Runtime Overview | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "dynamic language runtime"
  - "IronPython"
  - "DLR"
  - "IronRuby"
ms.assetid: f769a271-8aff-4bea-bfab-6160217ce23d
caps.latest.revision: 26
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 26
---
# Dynamic Language Runtime Overview
*Среда DLR* представляет собой среду выполнения, которая добавляет набор служб для динамических языков в среду CLR.  Среда DLR упрощает разработку динамических языков, используемых в .NET Framework и добавляет динамические функции в языки со статической типизацией.  
  
 Динамические языки могут определить тип объекта во время выполнения, тогда как для языков со статической типизацией, например C\# и Visual Basic \(при использовании `Option Explicit On`\), во время разработки следует указать типы объектов.  Примерами динамических языков могут служить Lisp, Smalltalk, JavaScript, PHP, Ruby, Python, ColdFusion, Lua, Cobra и Groovy.  
  
 Большинство динамических языков предоставляют разработчикам следующие преимущества.  
  
-   Возможность использования цикла быстрой обратной связи \(REPL, или цикл "read\-evaluate\-print"\).  Он позволяет вводить несколько операторов и сразу же выполнять их для просмотра результатов.  
  
-   Поддержка разработки "сверху вниз" и более традиционной — "снизу вверх".  Например, при использовании метода "сверху вниз" можно вызвать все еще не реализованные функции, а затем добавить базовые реализации по мере необходимости.  
  
-   Более простой рефакторинг и изменение кода, поскольку нет необходимости изменять объявления статических типов в коде.  
  
 Динамические языки позволяют создавать качественные скриптовые языки.  Пользователи могут легко расширить приложения, созданные с использованием динамических языков, с помощью новых команд и функциональных возможностей.  Динамические языки также часто используются для создания веб\-сайтов и окружений тестов, обслуживания ферм серверов, разработки различных служебных программ и выполнения преобразования данных.  
  
 Назначение среды DLR — обеспечение работы систем динамических языков в .NET Framework и взаимодействия в .NET.  Среда DLR предоставляет объекты для C\# и Visual Basic в Visual Studio 2010 для поддержки динамического поведения в этих языках и обеспечения взаимодействия с динамическими языками.  
  
 Среда DLR также упрощает создание библиотек, поддерживающих динамические операции.  Например, если имеется библиотека, использующая объекты XML или нотации объектов JavaScript \(JSON\), эти объекты могут отображаться в качестве динамических для языков, использующих среду DLR.  Это позволяет пользователям библиотек создавать синтаксически более простой и более естественный код для работы с объектами и доступа к членам объектов.  
  
 Например, для увеличения значения счетчика в формате XML в C\# можно использовать следующий код.  
  
 `Scriptobj.SetProperty("Count", ((int)GetProperty("Count")) + 1);`  
  
 Вместо него для этой же операции можно использовать следующий код С помощью среды DLR.  
  
 `scriptobj.Count += 1;`  
  
 Как и CLR, среда DLR является частью .NET Framework и поставляется в установочных пакетах .NET Framework и Visual Studio.  Версия с открытым исходным кодом среды DLR также доступна для загрузки на веб\-сайте [CodePlex](http://go.microsoft.com/fwlink/?LinkId=141028).  
  
> [!NOTE]
>  Версия среды DLR с открытым исходным кодом обладает той же функциональностью, что и среда DLR, входящая в Visual Studio и .NET Framework.  Она также обеспечивает дополнительную поддержку для разработчиков языков.  Дополнительные сведения см. в документации на веб\-сайте [CodePlex](http://go.microsoft.com/fwlink/?LinkId=141028).  
  
 Примеры языков, разработанных с помощью среды DLR, включают следующие.  
  
-   IronPython.  Доступны в качестве программного обеспечения с открытым исходным кодом на веб\-сайте [CodePlex](http://go.microsoft.com/fwlink/?LinkId=141040).  
  
-   IronRuby.  Доступны в качестве программного обеспечения с открытым исходным кодом на веб\-сайте [RubyForge](http://go.microsoft.com/fwlink/?LinkId=141044).  
  
## Основные преимущества среды DLR  
 Среда DLR обеспечивает следующие преимущества.  
  
### Упрощает перенос динамических языков в .NET Framework  
 Среда DLR позволяет разработчикам языков избежать создания лексических анализаторов, средств синтаксического анализа, семантических анализаторов, генераторов кода и других средств, которые обычно приходится создавать самостоятельно.  Для использования среды DLR язык должен создать *деревья выражений*, которые представляют код на уровне языка в виде древовидной структуры, вспомогательные процедуры среды выполнения и необязательные динамические объекты, реализующие интерфейс <xref:System.Dynamic.IDynamicMetaObjectProvider>.  Среда DLR и .NET Framework автоматизируют значительное количество задач анализа и генерации кода.  Это позволяет разработчикам языков сконцентрировать свои усилия на уникальных функциях языка.  
  
### Обеспечивает динамические функции в языках со статической типизацией  
 Существующие языки .NET Framework \(C\# и Visual Basic\) могут создавать динамические объекты и использовать их совместно с объектами со статической типизацией.  Например, в C\# и Visual Basic могут использоваться динамические объекты для HTML, Document Object Model \(DOM\) и отражение .NET.  
  
### Обеспечивает будущие преимущества среды DLR и .NET Framework  
 Языки, реализованные с использованием среды DLR, могут быть улучшены в будущем за счет усовершенствований среды DLR и .NET Framework.  Например, если .NET Framework выпускает новую версию с усовершенствованным сборщиком мусора или меньшим временем загрузки сборки, языки, реализованные с использованием среды DLR, сразу же получат те же преимущества.  Если в среде DLR усовершенствуется оптимизация \(например более эффективная компиляция\), производительность повысится и для всех языков, реализованных с использованием среды DLR.  
  
### Обеспечивает общий доступ к библиотекам и объектам  
 Объекты и библиотеки, реализованные на одном языке, могут использоваться другими языками.  Среда DLR также обеспечивает взаимодействие языков со статической и динамической типизацией.  Например, в C\# может быть объявлен динамический объект, использующий библиотеку, написанную на динамическом языке.  Вместе с этим динамические языки могут использовать библиотеки из .NET Framework.  
  
### Обеспечивает быструю динамическую отправку и вызов  
 Среда DLR обеспечивает быстрое выполнение динамических операций за счет поддержки усовершенствованного полиморфного кэширования.  Среда DLR создает правила для операций привязки, использующих объекты для необходимых реализаций среды выполнения, а затем кэширует эти правила, чтобы избежать ресурсоемких вычислений привязок во время последовательного выполнения того же кода, с теми же типами объектов.  
  
## Архитектура DLR  
 Ниже показана архитектура среды выполнения динамического языка.  
  
 ![Общие сведения об архитектуре среды DLR](../../../docs/framework/reflection-and-codedom/media/dlr-archoverview.png "DLR\_ArchOverview")  
Архитектура среды DLR  
  
 Среда DLR добавляет в среду CLR ряд служб для лучшей поддержки динамических языков.  К этим службам относятся следующие.  
  
-   Деревья выражений.  Среда DLR использует деревья выражений для представления семантики языка.  С этой целью в среде DLR имеются расширенные деревья выражений LINQ, включающие в себя поток управления, назначение и другие узлы моделирования языков.  Для получения дополнительной информации см. [Деревья выражений](../Topic/Expression%20Trees%20\(C%23%20and%20Visual%20Basic\).md).  
  
-   Кэширование места вызова.  *Динамическое место вызова* — это часть кода, которая выполняет для динамических объектов такую операцию, как `a + b` или `a.b()`.  Среда DLR кэширует характеристики `a` и `b` \(как правило, типы этих объектов\) и сведения об операции.  Если такая операция выполнялась ранее, среда DLR запрашивает всю необходимую информацию из кэша для быстрой отправки.  
  
-   Взаимодействие динамических объектов.  Среда DLR обеспечивает набор классов интерфейсов, представляющих динамические объекты и операции, которые могут использовать разработчики языков и динамических библиотек.  Эти классы и интерфейсы включают в себя <xref:System.Dynamic.IDynamicMetaObjectProvider>, <xref:System.Dynamic.DynamicMetaObject>, <xref:System.Dynamic.DynamicObject> и <xref:System.Dynamic.ExpandoObject>.  
  
 Среда DLR использует связыватели во всех местах вызова для связи не только с .NET Framework, но и с другими инфраструктурами и службами, включая Silverlight и COM.  Связыватели инкапсулируют семантику языка и указывают способ выполнения операций в месте вызова с помощью деревьев выражений.  Это обеспечивает для языков с динамической и статической типизацией, использующим среду DLR, совместный доступ к библиотекам и всем технологиям, поддерживаемым средой DLR.  
  
## DLR\-документация  
 Дополнительные сведения о том, как с помощью версии среды DLR с открытым исходным кодом добавить динамические функции в язык или как обеспечить использование динамического языка в .NET Framework, см. в документации по адресу [CodePlex](http://go.microsoft.com/fwlink/?LinkId=141028).  
  
## См. также  
 <xref:System.Dynamic.ExpandoObject>   
 <xref:System.Dynamic.DynamicObject>   
 [Среда CLR](../../../docs/standard/clr.md)   
 [Деревья выражений](../Topic/Expression%20Trees%20\(C%23%20and%20Visual%20Basic\).md)   
 [Пошаговое руководство. Создание и использование динамических объектов](../Topic/Walkthrough:%20Creating%20and%20Using%20Dynamic%20Objects%20\(C%23%20and%20Visual%20Basic\).md)