---
title: "Пошаговое руководство. Выполнение типичных задач с помощью смарт-тегов в элементах управления Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DesignerAction object model
- smart tags
- designer actions
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e2fb4e8bf710e55be0a817a4154dfbce114db191
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="walkthrough-performing-common-tasks-using-smart-tags-on-windows-forms-controls"></a>Пошаговое руководство. Выполнение типичных задач с помощью смарт-тегов в элементах управления Windows Forms
При разработке форм и элементов управления для приложения Windows Forms, существует много задач, которые выполняются несколько раз. Ниже приведено несколько наиболее типичных задач, которые указываются:  
  
-   Добавление или удаление вкладки <xref:System.Windows.Forms.TabControl>.  
  
-   Закрепление элемента управления своему родителю.  
  
-   Изменение ориентации элемента <xref:System.Windows.Forms.SplitContainer> элемента управления.  
  
 Для ускорения разработки, многие элементы управления обладают смарт-тегов, которые находятся в контекстных меню, которые позволяют выполнять общие задачи, такие как их в одном жест во время разработки. Эти задачи называются *командами смарт тегов*.  
  
 Смарт-теги остаются прикрепленными к экземпляру элемента управления для существования в конструкторе и всегда доступны.  
  
 В данном пошаговом руководстве представлены следующие задачи.  
  
-   Создание проекта Windows Forms  
  
-   С помощью смарт-тегов  
  
-   Включение и отключение смарт-тегов  
  
 После завершения вы будете понимать роль, которую играют эти важные функции макета.  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="creating-the-project"></a>Создание проекта  
 Первым шагом является создание проекта и настройка формы.  
  
#### <a name="to-create-the-project"></a>Создание проекта  
  
1.  Создайте проект приложения Windows с названием «SmartTagsExample». Дополнительные сведения см. в разделе [Практическое руководство. Создание проекта приложения Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  Выберите форму в **конструктор Windows Forms**.  
  
## <a name="using-smart-tags"></a>С помощью смарт-тегов  
 Смарт-теги всегда доступны во время разработки для элементов управления, которые их содержат.  
  
#### <a name="to-use-smart-tags"></a>Использование смарт-тегов  
  
1.  Перетащите <xref:System.Windows.Forms.TabControl> из **элементов** на форму. Обратите внимание, глиф смарт тега (![глиф смарт-тега](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")), которая отображается на краю <xref:System.Windows.Forms.TabControl>.  
  
2.  Щелкните глиф смарт тега. Выберите в контекстном меню рядом с глифом, **добавить вкладку** элемента. Обратите внимание, что добавляется новую страницу вкладки <xref:System.Windows.Forms.TabControl>.  
  
3.  Перетащите <xref:System.Windows.Forms.TableLayoutPanel> управления из **элементов** на форму.  
  
4.  Щелкните глиф смарт тега. Выберите в контекстном меню рядом с глифом, **добавить столбец** элемента. Обратите внимание, что новый столбец будет добавлен <xref:System.Windows.Forms.TableLayoutPanel> элемента управления.  
  
5.  Перетащите <xref:System.Windows.Forms.SplitContainer> управления из **элементов** на форму.  
  
6.  Щелкните глиф смарт тега. Выберите в контекстном меню рядом с глифом, **Ориентация горизонтального разделителя** элемента. Обратите внимание, что <xref:System.Windows.Forms.SplitContainer> элемента управления разделителя — теперь имеет горизонтальную ориентацию.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.TextBox>  
 <xref:System.Windows.Forms.TabControl>  
 <xref:System.Windows.Forms.SplitContainer>  
 <xref:System.ComponentModel.Design.DesignerActionList>  
 [Пошаговое руководство: Добавление смарт-тегов в компонент Windows Forms](http://msdn.microsoft.com/library/a6814169-fa7d-4527-808c-637ca5c95f63)
