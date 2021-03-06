---
title: "Проверка реестра имен поставщиков"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c4644dd1-dead-48ff-abeb-7bffae69a6ac
caps.latest.revision: "4"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5d131a032aa2747bda83874e8dd744588dfe07dd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="validating-issuer-name-registry"></a>Проверка реестра имен поставщиков
Проверка реестра имен эмитентов (VINR) для Windows Identity Foundation позволяет приложениям с большим числом владельцев убеждаться, что входящий токен создан доверенным клиентом и поставщиком удостоверений. Эта функция особенно полезна для приложений с несколькими владельцами, использующих Microsoft Azure Active Directory, поскольку все токены, выданные Microsoft Azure AD, подписываются с помощью одного сертификата. Чтобы различать запросы от нескольких клиентов, использующих один и тот же сертификат — и, следовательно, имеющих один и тот же отпечаток — приложение должно сохранять имя эмитента для каждого клиента, чтобы выполнить логику проверки. VINR предоставляет эту функцию, а также позволяет добавить логику проверки или сохранения сведений о регистрации эмитента не только в файле конфигурации. Данное расширение можно добавить в конвейер WIF приложения или использовать независимо.  
  
 VINR доступен как пакет NuGet. Дополнительные сведения см. в разделе [Загрузка пакета проверки реестра имен поставщиков](../../../docs/framework/security/downloading-the-validating-issuer-name-registry-package.md).  
  
## <a name="scenarios"></a>Сценарии  
 VINR реализует следующий основной сценарий:  
  
-   **Проверка токена в мультитенантном приложении**: в этом сценарии компания с названием Litware разработала мультитенантное приложение, в котором используется такой поставщик удостоверений, как Microsoft Azure AD. Это приложение обслуживает двух заказчиков: Contoso и Fabrikam. Когда пользователь из Fabrikam проходит аутентификацию в приложении Litware, токен, выданный Microsoft Azure AD, подписывается с помощью стандартного сертификата, и запрос оформляется компанией Fabrikam. Приложению необходимо убедиться, что имя эмитента и токен являются допустимыми допустимым, а также отличить подобные запросы от запросов из Contoso, которые подписаны таким же сертификатом из Microsoft Azure AD. Благодаря VINR приложению Litware проще различать и проверять запросы от разных владельцев (например, Contoso и Fabrikam).  
  
## <a name="features"></a>Функции  
 VINR обеспечивает следующие возможности.  
  
-   **Проверка имени издателя и токена для мультитенантных приложений**: проверяет входящий токен путем проверки имени издателя (клиента), а также того, подписан ли токен с использованием действительного сертификата от поставщика удостоверений.  
  
-   **Расширяемость для логики настраиваемой проверки и хранилищ данных**: обеспечивает расширяемость для добавления собственной логики проверки, а также для задания хранилища данных, отличного от файла конфигурации по умолчанию.
