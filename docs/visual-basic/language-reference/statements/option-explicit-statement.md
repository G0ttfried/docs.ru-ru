---
title: "Оператор Option Explicit (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Explicit
- vb.OptionExplicit
helpviewer_keywords:
- declaring variables [Visual Basic], explicit
- forced variable declaration in Option Explicit statement [Visual Basic]
- Explicit keyword
- explicit variable declaration
- Option Explicit statement [Visual Basic]
ms.assetid: e82ac1ad-2cd3-49b2-b985-8bcf016f3fcc
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f3d4c9cd3310e0ec3943c4e2b5e28be5b9a393db
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="option-explicit-statement-visual-basic"></a>Оператор Option Explicit (Visual Basic)
Принудительное явное объявление всех переменных в файле, либо разрешает неявные объявления переменных.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Option Explicit { On | Off }  
```  
  
## <a name="parts"></a>Части  
 `On`  
 Необязательный. Позволяет `Option Explicit` проверки. Если `On` или `Off` не указан, значение по умолчанию — `On`.  
  
 `Off`  
 Необязательный. Отключает `Option Explicit` проверки.  
  
## <a name="remarks"></a>Примечания  
 Когда `Option Explicit On` или `Option Explicit` появится в файле, все переменные должны быть объявлены явно с помощью `Dim` или `ReDim` инструкции. При попытке использовать необъявленное имя переменной, произошла ошибка во время компиляции. `Option Explicit Off` Оператор разрешает неявное объявление переменных.  
  
 Если используется оператор `Option Explicit`, он должен быть указан в файле до всех прочих операторов.  
  
> [!NOTE]
>  Установка `Option Explicit` для `Off` обычно это не рекомендуется. Вы можете допустить ошибку при вводе имени переменной в одном или нескольких местах, что приведет к непредвиденным результатам при выполнении программы.  
  
## <a name="when-an-option-explicit-statement-is-not-present"></a>Если оператор Option Explicit отсутствует  
 Если исходный код не содержит `Option Explicit` инструкции **Option Explicit** на [компиляция, конструктора проектов (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) используется. При использовании компилятора командной строки [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) используется параметр компилятора.  
  
#### <a name="to-set-option-explicit-in-the-ide"></a>Чтобы задать Option Explicit в Интегрированной среде разработки  
  
1.  Выберите проект в **обозревателе решений**. В меню **Проект** выберите пункт **Свойства**.  
  
2.  Откройте вкладку **Компиляция**.  
  
3.  Задайте значение в **Option Explicit** поле.  
  
 При создании нового проекта **Option Explicit** на **компиляции** набор вкладок **Option Explicit** в **VB по умолчанию**диалоговое окно. Чтобы получить доступ к **VB по умолчанию** в диалоговом **средства** меню, нажмите кнопку **параметры**. В диалоговом окне **Параметры** разверните узел **Проекты и решения** и выберите пункт **Параметры Visual Basic по умолчанию**. Начальный параметр по умолчанию в **VB значения по умолчанию** — `On`.  
  
#### <a name="to-set-option-explicit-on-the-command-line"></a>Чтобы задать Option Explicit в командной строке  
  
-   Включить [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) параметра компилятора в **vbc** команды.  
  
## <a name="example"></a>Пример  
 В следующем примере используется `Option Explicit` инструкцию, чтобы обеспечить явное объявление всех переменных. Попытка использования необъявленных переменных приводит к ошибке во время компиляции.  
  
 [!code-vb[VbVbalrStatements#47](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-explicit-statement_1.vb)]  
  
 [!code-vb[VbVbalrStatements#48](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-explicit-statement_2.vb)]  
  
## <a name="see-also"></a>См. также  
 [Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md)  
 [Оператор reDim](../../../visual-basic/language-reference/statements/redim-statement.md)  
 [Оператор Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md)  
 [Оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)  
 [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)  
 [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)  
 [Страница "Параметры Visual Basic по умолчанию", папка "Проекты", диалоговое окно "Параметры"](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
