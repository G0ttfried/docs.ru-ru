---
title: "Отключение объекта RealTimeStylus для WPF-приложений"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e0525309-5ede-4782-837d-dbf6e5554859
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 71fc4ec888419e385a57216f078387f731c0ab8e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="disable-the-realtimestylus-for-wpf-applications"></a>Отключение объекта RealTimeStylus для WPF-приложений
Windows Presentation Foundation (WPF) содержит встроенную поддержку Windows 7 сенсорный ввод. Поддержка проходит по ввод от пера в режиме реального времени платформы планшета как <xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, и <xref:System.Windows.UIElement.OnStylusMove%2A> события. Windows 7 также предоставляет мультисенсорный ввод как окна WM_TOUCH Win32. Эти два API являются взаимоисключающими для того же HWND. Включение сенсорного ввода с помощью платформы планшета (по умолчанию для приложений WPF) отключает сообщения WM_TOUCH. В результате Чтобы использовать WM_TOUCH для получения сенсорных сообщений от окна WPF, необходимо отключить встроенную поддержку пера в WPF. Это применимо в сценарии, например компонент, который использует WM_TOUCH окна WPF.  
  
 Чтобы отключить прослушивание ввод от пера WPF, удалите всю поддержку планшета, добавленные в окне WPF.  
  
## <a name="example"></a>Пример  
 В следующем примере кода показано, как удалить поддержку платформы планшета по умолчанию с помощью отражения.  
  
```  
public static void DisableWPFTabletSupport()  
{  
    // Get a collection of the tablet devices for this window.    
    TabletDeviceCollection devices = System.Windows.Input.Tablet.TabletDevices;  
  
    if (devices.Count > 0)  
    {     
        // Get the Type of InputManager.  
        Type inputManagerType = typeof(System.Windows.Input.InputManager);  
  
        // Call the StylusLogic method on the InputManager.Current instance.  
        object stylusLogic = inputManagerType.InvokeMember("StylusLogic",  
                    BindingFlags.GetProperty | BindingFlags.Instance | BindingFlags.NonPublic,  
                    null, InputManager.Current, null);  
  
        if (stylusLogic != null)  
        {  
            //  Get the type of the stylusLogic returned from the call to StylusLogic.  
            Type stylusLogicType = stylusLogic.GetType();  
  
            // Loop until there are no more devices to remove.  
            while (devices.Count > 0)  
            {  
                // Remove the first tablet device in the devices collection.  
                stylusLogicType.InvokeMember("OnTabletRemoved",  
                        BindingFlags.InvokeMethod | BindingFlags.Instance | BindingFlags.NonPublic,  
                        null, stylusLogic, new object[] { (uint)0 });  
            }                  
        }  
  
    }  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Перехват ввода, осуществляемого пером](../../../../docs/framework/wpf/advanced/intercepting-input-from-the-stylus.md)
