---
title: "Неявное преобразование из &#39; &lt;Имя_типа1&gt;&#39; к &#39;&lt; имя_типа2&gt;&#39; при копировании значение &#39; ByRef &#39; параметр &#39; &lt;имя_параметра&gt;&#39; обратно в соответствующий аргумент."
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc41999
- bc41999
helpviewer_keywords: BC41999
ms.assetid: ae48c738-dff8-4c0f-8931-bbb70b2c8b03
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9e858b475a816a35d18822643de5a273abe28562
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="implicit-conversion-from-39lttypename1gt39-to-39lttypename2gt39-in-copying-the-value-of-39byref39-parameter-39ltparameternamegt39-back-to-the-matching-argument"></a>Неявное преобразование из &#39; &lt;Имя_типа1&gt;&#39; к &#39;&lt; имя_типа2&gt;&#39; при копировании значение &#39; ByRef &#39; параметр &#39; &lt;имя_параметра&gt;&#39; обратно в соответствующий аргумент.
Процедура вызывается с [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) аргумент типа, отличного от соответствующего параметра.  
  
 Если передается аргумент `ByRef`, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] иногда копирует его значение в локальную переменную в процедуре вместо передачи ссылки. В случае когда процедура возвращает результат, среда [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] должна скопировать значение локальной переменной обратно в аргумент в вызывающем коде.  
  
 Если значение аргумента `ByRef` копируется в процедуру, а аргумент и параметр имеют один и тот же тип, то преобразование не требуется. Но если типы различны, среда [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] должна выполнить преобразование в обоих направлениях. Так как нельзя использовать `CType` или любые другие преобразования ключевые слова в аргумент процедуры или параметра, такое преобразование всегда является неявным.  
  
 По умолчанию данное сообщение является предупреждением. Сведения о сокрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC41999  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   По возможности используйте аргумент вызова того же типа, что и параметр процедуры, чтобы среде [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] не нужно было выполнять никаких преобразований.  
  
-   Если необходимо вызвать процедуру с аргументом, тип которого отличается от типа параметра, но не обязательно должны возвращать значение в аргумент вызова, то определите параметр как [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) вместо `ByRef`.  
  
## <a name="see-also"></a>См. также  
 [Процедуры](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [Параметры и аргументы процедуры](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)  
 [Передача аргументов по значению и по ссылке](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)  
 [Явные и неявные преобразования](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
