---
title: "Таймеры потоков (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 52ed71e8-4fd9-43a4-ae40-04cce7cff23f
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 9702360408340b28fcdcc8f197467a002f77ee51
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="thread-timers-c"></a>Таймеры потоков (C#)
Класс <xref:System.Threading.Timer?displayProperty=nameWithType> полезно использовать для периодического выполнения задачи в отдельном потоке. Например, можно использовать таймер потока для проверки состояния и целостности базы данных или для создания резервных копий важных файлов.  
  
## <a name="thread-timer-example"></a>Пример таймера потока  
 В следующем примере задача запускается каждые две секунды и использует флаг для инициализации метода <xref:System.IDisposable.Dispose%2A>, который останавливает таймер. В этом примере сведения о состояния отображаются в окне вывода.  
  
```csharp  
private class StateObjClass  
{  
    // Used to hold parameters for calls to TimerTask.  
    public int SomeValue;  
    public System.Threading.Timer TimerReference;  
    public bool TimerCanceled;  
}  
  
public void RunTimer()  
{  
    StateObjClass StateObj = new StateObjClass();  
    StateObj.TimerCanceled = false;  
    StateObj.SomeValue = 1;  
    System.Threading.TimerCallback TimerDelegate =  
        new System.Threading.TimerCallback(TimerTask);  
  
    // Create a timer that calls a procedure every 2 seconds.  
    // Note: There is no Start method; the timer starts running as soon as   
    // the instance is created.  
    System.Threading.Timer TimerItem =  
        new System.Threading.Timer(TimerDelegate, StateObj, 2000, 2000);  
  
    // Save a reference for Dispose.  
    StateObj.TimerReference = TimerItem;    
  
    // Run for ten loops.  
    while (StateObj.SomeValue < 10)   
    {  
        // Wait one second.  
        System.Threading.Thread.Sleep(1000);    
    }  
  
    // Request Dispose of the timer object.  
    StateObj.TimerCanceled = true;    
}  
  
private void TimerTask(object StateObj)  
{  
    StateObjClass State = (StateObjClass)StateObj;  
    // Use the interlocked class to increment the counter variable.  
    System.Threading.Interlocked.Increment(ref State.SomeValue);  
    System.Diagnostics.Debug.WriteLine("Launched new thread  " + DateTime.Now.ToString());  
    if (State.TimerCanceled)      
    // Dispose Requested.  
    {  
        State.TimerReference.Dispose();  
        System.Diagnostics.Debug.WriteLine("Done  " + DateTime.Now.ToString());  
    }  
}  
```  
  
 Таймеры потоков особенно полезны в случае отсутствия доступа к объекту <xref:System.Windows.Forms.Timer?displayProperty=nameWithType>, например при разработке консольных приложений.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Threading>  
 [Многопоточные приложения(C#)](../../../../csharp/programming-guide/concepts/threading/multithreaded-applications.md)
