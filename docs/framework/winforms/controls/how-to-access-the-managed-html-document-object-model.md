---
title: "Практическое руководство. Доступ к управляемой объектной модели HTML-документов"
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
helpviewer_keywords:
- HTML DOM [Windows Forms], accessing
- managed HTML DOM [Windows Forms], accessing
ms.assetid: 40fa5cd5-1ed8-42f6-a93f-9ac01608bbeb
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 83ee8c5e0cd578a0eb821a35a27c5ff0072e5533
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-access-the-managed-html-document-object-model"></a>Практическое руководство. Доступ к управляемой объектной модели HTML-документов
Получить доступ к управляемой объектной модели HTML-документа (DOM) можно из двух типов приложений.  
  
-   Приложение Windows Forms (.EXE), в котором размещен управляемый элемент управления <xref:System.Windows.Forms.WebBrowser>. Эти две технологии дополняют друг друга: элемент управления <xref:System.Windows.Forms.WebBrowser> отображает страницу пользователю, а HTML DOM представляет логическую структуру документа.  
  
-   Windows Forms <xref:System.Windows.Forms.UserControl> размещается в Internet Explorer. Вы можете открыть HTML DOM, который показывает страницу, где находится элемент управления <xref:System.Windows.Forms.UserControl>, и изменить структуру документа, открыть модальные диалоговые окна и т. д.  
  
### <a name="to-access-dom-from-a-windows-forms-application"></a>Доступ к DOM из приложения Windows Forms  
  
1.  Разместите элемент управления <xref:System.Windows.Forms.WebBrowser> в приложении Windows Forms и наблюдайте за событием <xref:System.Windows.Forms.WebBrowser.DocumentCompleted>. Дополнительные сведения о размещении элементов управления и наблюдении за событиями см. в разделе [События](../../../../docs/standard/events/index.md).  
  
2.  Получите <xref:System.Windows.Forms.HtmlDocument> для текущей страницы, открыв свойство <xref:System.Windows.Forms.WebBrowser.Document%2A> элемента управления <xref:System.Windows.Forms.WebBrowser>.  

### <a name="to-access-dom-from-a-usercontrol-hosted-in-internet-explorer"></a>Доступ к DOM из элемента управления UserControl, размещенного в Internet Explorer  
  
1.  Создайте собственный пользовательский класс, производный от класса <xref:System.Windows.Forms.UserControl>. Дополнительные сведения см. в разделе [Практическое руководство. Создание составных элементов управления](../../../../docs/framework/winforms/controls/how-to-author-composite-controls.md).  
  
2.  Поместите в обработчик события загрузки для <xref:System.Windows.Forms.UserControl> следующий код:  
  
 [!code-csharp[AccessHTMLDOMControl#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/AccessHTMLDOMControl/cs/UserControl1.cs#1)]
 [!code-vb[AccessHTMLDOMControl#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/AccessHTMLDOMControl/vb/UserControl1.vb#1)]  
  
## <a name="robust-programming"></a>Отказоустойчивость  
  
1.  При использовании DOM через элемент управления <xref:System.Windows.Forms.WebBrowser> необходимо подождать, пока появится событие <xref:System.Windows.Forms.WebBrowser.DocumentCompleted>, и только после этого запрашивать доступ к свойству <xref:System.Windows.Forms.WebBrowser.Document%2A> элемента управления <xref:System.Windows.Forms.WebBrowser>. Событие <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> порождается после загрузки всего документа. Если использовать DOM до того, как это произойдет, во время выполнения в приложении может возникнуть исключение.  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
  
1.  Для получения доступа к управляемому HTML DOM приложение или <xref:System.Windows.Forms.UserControl> потребуют полного доверия. Если приложение Windows Forms развертывается с помощью [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)], можно запросить полное доверие, используя повышение уровня разрешения или развертывание доверенных приложений (см. раздел [Защита приложений ClickOnce](/visualstudio/deployment/securing-clickonce-applications)).  
  
## <a name="see-also"></a>См. также  
 [Использование управляемой объектной модели HTML-документов](../../../../docs/framework/winforms/controls/using-the-managed-html-document-object-model.md)
