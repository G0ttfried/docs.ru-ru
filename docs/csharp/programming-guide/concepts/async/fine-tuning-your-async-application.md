---
title: "Настройка асинхронного приложения (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
ms.assetid: 97696eb9-81fc-4940-9655-84daa8eb4d5c
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 8d8e655845f2d71e35ac72ba4f5a5b12027e2e1b
ms.sourcegitcommit: cec0525b2121c36198379525e69aa5388266db5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="fine-tuning-your-async-application-c"></a>Настройка асинхронного приложения (C#)
Методы и свойства, доступные при использовании типа <xref:System.Threading.Tasks.Task>, позволяют сделать приложение более точным и гибким. В подразделах этого раздела приводятся примеры, в которых используются <xref:System.Threading.CancellationToken> и важные методы `Task`, такие как <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> и <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>.  
  
 С помощью `WhenAny` и `WhenAll` можно легко запускать несколько задач и ожидать их завершения путем наблюдения за одной из них.  
  
-   `WhenAny` возвращает задачу, которая завершается после завершения любой задачи в коллекции.  
  
     Примеры использования `WhenAny` см. в разделах [Отмена оставшихся асинхронных задач после завершения одной из них (C#)](../../../../csharp/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md) и [Запуск нескольких асинхронных задач и их обработка по мере завершения (C#)](../../../../csharp/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md).  
  
-   `WhenAll` возвращает задачу, которая завершается после завершения всех задач в коллекции.  
  
     Дополнительные сведения и пример, использующий метод `WhenAll`, см. в разделе [Практическое руководство. Расширение пошагового руководства по асинхронным процедурам с использованием метода Task.WhenAll (C#)](../../../../csharp/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).  
  
 Этот раздел содержит следующие примеры.  
  
-   [Отмена асинхронной задачи или списка задач (C#)](../../../../csharp/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md)  
  
-   [Отмена асинхронных задач после определенного периода времени (C#)](../../../../csharp/programming-guide/concepts/async/cancel-async-tasks-after-a-period-of-time.md)  
  
-   [Отмена оставшихся асинхронных задач после завершения одной из них (C#)](../../../../csharp/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md)  
  
-   [Запуск нескольких асинхронных задач и их обработка по мере завершения (C#)](../../../../csharp/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md)  
  
> [!NOTE]
>  Для выполнения примеров необходимо, чтобы на компьютере были установлены Visual Studio 2012 или более поздняя версия и .NET Framework 4.5 или более поздняя версия.  
  
 Проекты создают пользовательский интерфейс, содержащий кнопку, которая запускает процесс, и кнопку, которая его отменяет, как показано на следующем рисунке. Кнопки называются `startButton` и `cancelButton`.  
  
 ![Окно WPF с кнопкой "Отмена"](../../../../csharp/programming-guide/concepts/async/media/cancellation.png "Cancellation")  
  
 Скачать полный проект Windows Presentation Foundation (WPF) можно со страницы [Пример асинхронности. Тонкая настройка приложения](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea).  
  
## <a name="see-also"></a>См. также  
 [Асинхронное программирование с использованием ключевых слов Async и Await (C#)](../../../../csharp/programming-guide/concepts/async/index.md)
