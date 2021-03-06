---
title: "Приступая к работе Tutorial1 он"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF [WCF], getting started
- Windows Communication Foundation [WCF], getting started
- getting started [WCF]
ms.assetid: df939177-73cb-4440-bd95-092a421516a1
caps.latest.revision: "47"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 74a322730c5e9fc205097da310a8db1fd7c50f82
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="getting-started-tutorial"></a>Учебник по началу работы
Содержащиеся в этом разделе подразделы призваны кратко познакомить читателя с процессом программирования в [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]. Их нужно выполнять в том порядке, в котором они перечислены в конце этой страницы. Прохождение этих занятий позволит получить базовое представление об этапах, которые необходимы для создания служб и клиентских приложений [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]. Служба предоставляет одну или несколько конечных точек, каждая из которых предоставляет одну или несколько операций службы. *Конечная точка* службы задает адрес, где можно найти службу, привязку, которая содержит сведения, описывающие, как клиент должен обмениваться данными со службой и контракт, определяющий функцию предоставляемую службой клиентам.  
  
 После изучения разделов этого учебника вы получите готовую службу и клиента, который может вызывать операции этой службы. В первых трех разделах описано, как определить контракт службы, реализовать контракт службы и разместить службу. Созданная служба является резидентной в консольном приложении. Службы можно размещать в службах Internet Information Services (IIS). [!INCLUDE[crabout](../../../includes/crabout-md.md)]как это сделать, см. [как: размещение службы WCF в IIS](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md). Эта служба настроена в коде, однако службы можно настраивать с помощью файла конфигурации. [!INCLUDE[crabout](../../../includes/crabout-md.md)]с помощью файла конфигурации в разделе [Настройка служб с помощью файла конфигурации](../../../docs/framework/wcf/configuring-services-using-configuration-files.md).  
  
 В следующих трех разделах описано, как создать клиентский прокси, настроить клиентское приложение и использовать клиентский прокси для вызова служебных действий, предоставляемых службой. Службы публикуют доступные метаданные, определяющие сведения, необходимые клиентским приложениям для взаимодействия со службой. [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] автоматизирует процесс доступа к этим метаданным и использует его для настройки клиентского приложения для службы. Если вы не используете [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)], можно использовать [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) для создания и настройки клиентского приложения для службы.  
  
 Все темы этого раздела предполагают, что в качестве среды разработки используется Visual Studio 2011. Если используется другая среда разработки, игнорируйте инструкции, относящиеся только к [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)].  
  
> [!NOTE]
>  Если вы используете [!INCLUDE[wv](../../../includes/wv-md.md)] или более поздних версиях операционной системы Windows, необходимо запустить [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] , перейдите в меню "Пуск" и щелкните правой кнопкой мыши Visual Studio 2011 и выбрав **Запуск от имени администратора**. Чтобы всегда запускать Visual Studio 2011 от имени администратора, можно создать ярлык, щелкните ярлык правой кнопкой мыши, выберите пункт Свойства, выберите **совместимости** и проверьте **запускать эту программу от имени администратора** флажок. При запуске среды Visual Studio 2011 с помощью этого ярлыка, она будет выполняться от имени администратора.  
  
 Образцы приложений, которые можно загрузить на жесткий диск и запуска, см. в разделах [образцов Windows Communication Foundation](http://msdn.microsoft.com/library/8ec9d192-5d81-4f64-bfd3-90c5e5858c91). Для этого раздела см. в разделе, в частности, [Приступая к работе](../../../docs/framework/wcf/samples/getting-started-sample.md).  
  
 Более подробные сведения о создании служб и клиентов см. в разделе [базовое Программирование WCF](../../../docs/framework/wcf/basic-wcf-programming.md).  
  
## <a name="in-this-section"></a>В этом разделе  
 [Практическое руководство. Определение контракта службы](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)  
 Создание контракта [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] с использованием определенного пользователем интерфейса. Контракт определяет функциональные возможности, предоставляемые службой.  
  
 [Практическое руководство. Реализация контракта службы](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)  
 Реализация контракта службы. Контракт определяется один раз и должен быть реализован классом службы.  
  
 [Практическое руководство. Размещение и запуск базовой службы](../../../docs/framework/wcf/how-to-host-and-run-a-basic-wcf-service.md)  
 Настройка конечной точки службы в коде, ее размещение в консольном приложении и запуск службы. Чтобы служба стала активной, ее необходимо настроить и разместить в среде выполнения. Эта среда создает службу и управляет ее контекстом и временем существования.  
  
 [Практическое руководство. Создание клиента](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)  
 Извлечение метаданных, которые служат для создания клиентского прокси-класса [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] из службы [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]. В этом процессе используется функция добавления ссылки на службу в среде Visual Studio 2011.  
  
 [Практическое руководство. Настройка клиента](../../../docs/framework/wcf/how-to-configure-a-basic-wcf-client.md)  
 Описывает, как настроить клиент WCF. Настройка клиента требует задания конечной точки, которую клиент использует для получения доступа к службе.  
  
 [Практическое руководство. Использование клиента](../../../docs/framework/wcf/how-to-use-a-wcf-client.md)  
 Использование клиента [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] для вызова операций службы.  
  
## <a name="reference"></a>Ссылка  
 <xref:System.ServiceModel.ServiceContractAttribute>  
  
 <xref:System.ServiceModel.OperationContractAttribute>  
  
## <a name="related-sections"></a>Связанные разделы  
 [Примеры Windows Communication Foundation](http://msdn.microsoft.com/library/8ec9d192-5d81-4f64-bfd3-90c5e5858c91)  
  
 [Базовый жизненный цикл программирования](../../../docs/framework/wcf/basic-programming-lifecycle.md)  
  
## <a name="see-also"></a>См. также  
 [Концептуальный обзор](../../../docs/framework/wcf/conceptual-overview.md)  
 [Руководство по работе с документацией](../../../docs/framework/wcf/guide-to-the-documentation.md)  
 [Что такое Windows Communication Foundation](../../../docs/framework/wcf/whats-wcf.md)  
 [Подробные сведения о возможностях WCF](../../../docs/framework/wcf/feature-details/index.md)
