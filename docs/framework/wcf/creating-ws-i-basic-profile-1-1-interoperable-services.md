---
title: "Создание служб, поддерживающих взаимодействие с базовым профилем WS-I 1.1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- configuration [WCF], interoperable services
ms.assetid: 91b70a21-8f5c-4679-808c-2ed5fa6b2013
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d6bef68c8ba433e902cfd50e59a3b343e3af08cd
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="creating-ws-i-basic-profile-11-interoperable-services"></a>Создание служб, поддерживающих взаимодействие с базовым профилем WS-I 1.1
Для настройки конечной точки службы [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] таким образом, чтобы она могла взаимодействовать с клиентами веб-службы [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)], необходимо:  
  
-   использовать в качестве типа привязки для конечной точки службы тип <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType>;  
  
-   не использовать возможности обратного вызова и сеансового контракта и не управлять поведением транзакций на конечной точке службы.  
  
 В привязке можно дополнительно включить поддержку протокола HTTPS и проверку подлинности клиента на транспортном уровне.  
  
 Следующие функции класса <xref:System.ServiceModel.BasicHttpBinding> требуют функциональность, выходящую за рамки спецификации WS-I Basic Profile, версия 1.1.  
  
-   Кодирование сообщения подсистемы оптимизации передачи сообщений MTOM управляется свойством <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType>. Не изменяйте значение этого свойства по умолчанию - <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType> (не использовать MTOM).  
  
-   Безопасность сообщения управляется значением <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType> и обеспечивает поддержку WS-Security, совместимую с основным профилем безопасности WS-I версии 1.0. Не изменяйте значение этого свойства по умолчанию - <xref:System.ServiceModel.SecurityMode.Transport?displayProperty=nameWithType> (не использовать WS-Security).  
  
 Чтобы сделать метаданные для [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] службу, доступную [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)], используйте инструменты создания клиента службы Web: [инструмент языка описания веб-служб (Wsdl.exe)](http://msdn.microsoft.com/library/b9210348-8bc2-4367-8c91-d1a04b403e88), [(средство обнаружения веб-служб DISCO.exe)](http://msdn.microsoft.com/library/acd88078-c581-42bc-94ca-6633e2851979)и `Add Web Reference` компонентов в [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]; необходимо включить публикацию метаданных. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Публикации конечных точек метаданных](../../../docs/framework/wcf/publishing-metadata-endpoints.md).  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание:  
 В следующем примере кода показано, как добавить [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] конечную точку, совместимую с [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] клиентами веб-службы в коде и, кроме того, в файле конфигурации.  
  
### <a name="code"></a>Код  
 [!code-csharp[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/cs/program.cs#0)]
 [!code-vb[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/vb/program.vb#0)]  
 [!code-xml[C_HowTo-WCFServiceAndASMXClient#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/common/app.config#1)]  
  
## <a name="see-also"></a>См. также  
 [Взаимодействие с веб-службами ASP.NET](../../../docs/framework/wcf/feature-details/interop-with-aspnet-web-services.md)
