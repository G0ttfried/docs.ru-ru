---
title: "Практическое руководство. Отображение даты в пользовательском формате с помощью элемента управления DateTimePicker в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DateTimePicker control [Windows Forms], display styles
- examples [Windows Forms], DateTimePicker control
- dates [Windows Forms], displaying in DateTimePicker control
ms.assetid: 39767691-2d2b-46b6-a663-b7901e581a6e
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a5f5c7d856991ae8e0bf7caff656bf7010255628
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-display-a-date-in-a-custom-format-with-the-windows-forms-datetimepicker-control"></a>Практическое руководство. Отображение даты в пользовательском формате с помощью элемента управления DateTimePicker в Windows Forms
Windows Forms <xref:System.Windows.Forms.DateTimePicker> управления обеспечивает гибкие возможности форматирования отображаемых данных даты и времени в элементе управления. <xref:System.Windows.Forms.DateTimePicker.Format%2A> Свойства можно выбрать из стандартных форматов, перечисленных в <xref:System.Windows.Forms.DateTimePickerFormat>. Если ни один из них не подходит для ваших целей, можно создать собственный стиль формата, с помощью символов формата, перечисленные в <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A>.  
  
### <a name="to-display-a-custom-format"></a>Чтобы отобразить пользовательский формат  
  
1.  Задайте для свойства <xref:System.Windows.Forms.DateTimePicker.Format%2A> значение `DateTimePickerFormat.Custom`.  
  
2.  Задать <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> свойства в строке формата.  
  
    ```vb  
    DateTimePicker1.Format = DateTimePickerFormat.Custom  
    ' Display the date as "Mon 27 Feb 2012".  
    DateTimePicker1.CustomFormat = "ddd dd MMM yyyy"  
    ```  
  
    ```csharp  
    dateTimePicker1.Format = DateTimePickerFormat.Custom;  
    // Display the date as "Mon 27 Feb 2012".  
    dateTimePicker1.CustomFormat = "ddd dd MMM yyyy";  
    ```  
  
    ```cpp  
    dateTimePicker1->Format = DateTimePickerFormat::Custom;  
    // Display the date as "Mon 27 Feb 2012".  
    dateTimePicker1->CustomFormat = "ddd dd MMM yyyy";  
    ```  
  
### <a name="to-add-text-to-the-formatted-value"></a>Добавление текста в форматированное значение  
  
1.  Использовать одинарные кавычки для заключения знаков, которые не являются знаками формата, например «M» или разделителями, например «:». Например, строка формата отображает текущую дату в формате «сегодня: 05:30:31 пятница 02 марта 2012 г.» Английский (США) язык и региональные параметры.  
  
    ```vb  
    DateTimePicker1.CustomFormat = "'Today is:' hh:mm:ss dddd MMMM dd, yyyy"  
    ```  
  
    ```csharp  
    dateTimePicker1.CustomFormat = "'Today is:' hh:mm:ss dddd MMMM dd, yyyy";  
    ```  
  
    ```cpp  
    dateTimePicker1->CustomFormat =  
       "'Today is:' hh:mm:ss dddd MMMM dd, yyyy";  
    ```  
  
     В зависимости от языка и региональных параметров, можно изменить любые символы, которые не заключаются в одинарные кавычки. Например, строка формата отображает текущую дату в формате «сегодня: 05:30:31 пятница 02 марта 2012 г.» Английский (США) язык и региональные параметры. Обратите внимание, что первое двоеточие заключено в одинарные кавычки, поскольку он не предназначен для символа-разделителя, как в «чч». В другой язык и региональные параметры, формат может быть как «сегодня: 05.30.31 пятница 02 марта 2012 г.».  
  
## <a name="see-also"></a>См. также  
 [Элемент управления DateTimePicker](../../../../docs/framework/winforms/controls/datetimepicker-control-windows-forms.md)  
 [Практическое руководство. Отображение и ввод дат с помощью элемента управления DateTimePicker в Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)
