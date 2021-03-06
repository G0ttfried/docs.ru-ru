---
title: "Условные методы Get и Put"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3d22067f-57b8-4e0f-a571-a694512187ae
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 08efa127ed06ffc8cff3c7bb83af7be929329794
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="conditional-get-and-put"></a>Условные методы Get и Put
В этом образце демонстрируется использование новых интерфейсов API условного получения и обновления для модели программирования WCF REST. Поскольку больше всего подходят для условного получения и обновления ориентацией на ресурсы и службы REST, в этом примере расширяет [базовой службы ресурсов](../../../../docs/framework/wcf/samples/basic-resource-service.md) образца. В этом примере уделяется добавлена поддержка условного получения и обновления для [базовой службы ресурсов](../../../../docs/framework/wcf/samples/basic-resource-service.md) образца с помощью новых API, представленные в [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)].  
  
## <a name="demonstrates"></a>Демонстрации  
 Условное получение и обновление  
  
## <a name="discussion"></a>Обсуждение  
 В этом образце служба WCF предоставляет доступ к коллекции клиентов в стиле REST и с ориентацией на ресурсы. Подробное описание реализации службы, см. в разделе [базовой службы ресурсов](../../../../docs/framework/wcf/samples/basic-resource-service.md) образца.  
  
 В этом примере добавляется условного получения и обновления возможностей [базовой службы ресурсов](../../../../docs/framework/wcf/samples/basic-resource-service.md) образца. Для проверки наличия у клиента последней сущности для данного ресурса при условном получении и обновлении используются теги сущности HTTP и заголовки HTTP If-None-Match и If-Match. Однако реализация кода для правильной проверки заголовков HTTP If-None-Match и If-Match занимает много времени и редко получается без ошибок. В связи с этим в контекст <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> были добавлены методы <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> и <xref:System.ServiceModel.Web.IncomingWebRequestContext>, доступ к которым можно получить с помощью текущего экземпляра контекста <xref:System.ServiceModel.Web.WebOperationContext>. Кроме того, в контекст `SetETag` был добавлен метод <xref:System.ServiceModel.Web.OutgoingWebRequestContext>, что упрощает возврат допустимых тегов сущностей.  
  
 Метод <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> предназначен для использования с операциями [WebGet]. Он принимает тег текущей сущности данного ресурса в качестве параметра `entityTag`, который может иметь тип `string`, `int`, `long` или `Guid`. Метод <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> проверяет тег сущности по заголовку HTTP If-None-Match запроса. Если этот тег сущности имеется в заголовке HTTP If-None-Match, то формируется исключение <xref:System.ServiceModel.Web.WebFaultException> с кодом состояния «Не изменено» (304). В противном случае метод возвращает значение. Этот механизм условного получения позволяет клиенту сообщать серверу, что у него есть эта сущность, и отправлять текущую сущность, только если ее у клиента нет. Пример использования метода <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> можно посмотреть в операциях `GetCustomer` и `GetCustomers` службы. Важно отметить, что при вызове метода <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> значение может быть не возвращено. Разработчикам следует реализовывать операцию так, чтобы до вызова метода <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> уже было известно, что запрос выполнен успешно, с тем чтобы при отсутствии вызова метода <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> служба отправляла сообщение с кодом состояния успешного выполнения.  
  
 Метод <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> похож на метод <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A>. Он тоже принимает тег текущей сущности для данного ресурса. Тем не менее он предназначен для использования с операциями [WebInvoke], в которых метод имеет значение «PUT» или «DELETE». Метод <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> проверяет тег сущности по заголовку HTTP If-Match запроса. Если в заголовке HTTP If-Match тег сущности отсутствует, то формируется исключение <xref:System.ServiceModel.Web.WebFaultException> с кодом состояния «Предварительное условие не выполнено» (412). Этот механизм условного обновления позволяет клиенту сообщать серверу, что у него есть эта сущность для ресурса; он позволяет клиенту изменять ресурс, только если имеющаяся у него сущность является текущей. Пример использования метода <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> можно посмотреть в операциях `UpdateCustomer` и `DeleteCustomer` службы. Как и в случае с методом <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A>, важно отметить, что при вызове метода <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> значение может быть не возвращено. Разработчикам следует реализовывать операцию так, чтобы до вызова метода <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> уже было известно, что запрос выполнен успешно, с тем чтобы при отсутствии вызова метода <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> служба отправляла сообщение с кодом состояния успешного выполнения.  
  
 Образец состоит из резидентной службы и клиента, который работает в консольном приложении. Во время выполнения консольного приложения клиент совершает запросы к службе и выводит в окно консоли нужные сведения из ответов.  
  
#### <a name="to-run-the-sample"></a>Выполнение образца  
  
1.  Откройте решение для образца Conditional Get and Put. Для успешного выполнения образца среду [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] необходимо запускать от имени администратора. Для этого щелкните правой кнопкой мыши [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] значок и выбрав **Запуск от имени администратора** в контекстном меню.  
  
2.  Нажмите сочетание клавиш CTRL+SHIFT+B, чтобы построить решение, а затем сочетание клавиш CTRL+F5, чтобы запустить проект консольного приложения. Если запустить этот проект с включенной функцией отладки (нажав клавишу F5 вместо CTRL+F5), то отладчик будет останавливаться, когда условная проверка GET и PUT формирует исключение. В этом случае нажмите клавишу F5, чтобы продолжить выполнение образца.  
  
3.  Открывается окно консоли с URI запущенной службы и URI HTML-страницы справки для запущенной службы.  
  
4.  Во время выполнения образца клиент отправляет запросы к службе и выводит ответы в окно консоли.  
  
5.  Чтобы завершить образец, нажмите любую клавишу.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\ConditionalGetAndPut`
