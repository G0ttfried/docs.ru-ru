---
title: "Объявления обнаружения и клиент объявления | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 426c6437-f8d2-4968-b23a-18afd671aa4b
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Объявления обнаружения и клиент объявления
Функция обнаружения [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] позволяет компонентам объявлять свою доступность.При соответствующей настройке служба отправляет объявления Hello и Bye.Клиенты или другие компоненты могут прослушивать данные сообщения с объявлениями и действовать необходимым образом.Это дает клиенту альтернативный метод получения данных о службах.Функция объявлений может использоваться несколькими разными способами. Например, если службы часто входят в сеть и выходят из сети, то объявления могут стать альтернативой их поиску.Такой подход дает возможность снизить нагрузку на сеть, а клиенту — получать больше сведений о наличии или отсутствии службы по мере получения объявлений.  
  
## Объявления обнаружения  
 Когда служба, настроенная для объявлений, подключается к сети и становится доступной для обнаружения, она отправляет сообщение Hello, которое объявляет прослушивающим клиентам о ее доступности.Сообщение содержит сведения, связанные с обнаружением службы, например контракт, адрес конечной точки и соответствующие области.В классе <xref:System.ServiceModel.Discovery.AnnouncementEndpoint> можно указать, куда отправляется сообщение с объявлением.Если конечной точкой объявления является <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>, то сообщения Hello и Bye одновременно передаются нескольким абонентам. Если же конечная точка объявления является одноадресной рассылкой, то сообщения передаются непосредственно указанной конечной точке.  
  
> [!NOTE]
>  Объявления отправляются при открытии и закрытии узла службы.При неправильном завершении этих вызовов сообщения могут не отправляться.Например, при возникновении ошибки службы сообщение с объявлением Bye не отправляется.  
  
> [!TIP]
>  Функцию объявлений можно настроить на отправку объявлений в заданных ситуациях.  
  
 [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] определяет <xref:System.ServiceModel.Discovery.AnnouncementEndpoint> и <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> как стандартные конечные точки, позволяя службам и клиентам отправлять объявления Hello и Bye.  
  
### Объявления в службе  
 Чтобы настроить отправку объявлений службой, добавьте <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> с конечной точкой объявления.В следующем примере показано, как программным способом добавить это поведение в узел службы.В этом примере используется `UdpAnnouncementEndpoint`, которая подразумевает, что сообщения являются многоадресной рассылкой в расположения, указываемые конечной точкой.  
  
```  
ServiceDiscoveryBehavior serviceDiscoveryBehavior = new ServiceDiscoveryBehavior();  
serviceDiscoveryBehavior.AnnouncementEndpoints.Add(new UdpAnnouncementEndpoint());  
serviceHost.Description.Behaviors.Add(serviceDiscoveryBehavior);  
```  
  
 Это поведение можно также настроить в файле конфигурации, как показано в следующем примере.  
  
```  
<services>  
  <service behaviorConfiguration="CalculatorBehavior" name="Microsoft.Samples.Discovery.CalculatorService">  
    <!--Add Discovery Endpoint-->  
    <endpoint name="udpDiscoveryEpt" kind="udpDiscoveryEndpoint" />  
  </service>  
</services>  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorBehavior">  
      <!--Add Discovery behavior-->  
      <serviceDiscovery>  
        <announcementEndpoints>  
          <endpoint kind="udpAnnouncementEndpoint" />  
        </announcementEndpoints>  
      </serviceDiscovery>  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 В предыдущих примерах служба настраивается для автоматической отправки сообщений с объявлениями.Можно также отправлять сообщения с объявлениями явным образом с помощью класса <xref:System.ServiceModel.Discovery.AnnouncementClient>.  
  
### Объявления на клиенте  
 В клиентском приложение должна быть размещена служба объявлений, которая занимается обработкой сообщений Hello и Bye и подписана на события <xref:System.ServiceModel.Discovery.AnnouncementService.OnlineAnnouncementReceived> и <xref:System.ServiceModel.Discovery.AnnouncementService.OfflineAnnouncementReceived>.Следующий пример показывает, как это сделать.  
  
```  
// Create an AnnouncementService instance  
AnnouncementService announcementService = new AnnouncementService();  
  
// Subscribe the announcement events  
announcementService.OnlineAnnouncementReceived += OnOnlineEvent;  
announcementService.OfflineAnnouncementReceived += OnOfflineEvent;  
  
// Create ServiceHost for the AnnouncementService  
using (ServiceHost announcementServiceHost = new ServiceHost(announcementService))  
{  
    // Listen for the announcements sent over UDP multicast  
    announcementServiceHost.AddServiceEndpoint(new UdpAnnouncementEndpoint());  
    announcementServiceHost.Open();  
  
    Console.WriteLine("Press <ENTER> to terminate.");  
    Console.ReadLine();  
}  
  
```  
  
 При входящей обработке сообщения Hello или Bye метаданные обнаружения конечной точки доступны через <xref:System.ServiceModel.Discovery.AnnouncementEventArgs>, как показано в следующем примере.  
  
```  
static void OnOnlineEvent(object sender, AnnouncementEventArgs e)  
{  
    Console.WriteLine("Received an online announcement from {0}",   
e.EndpointDiscoveryMetadata.Address);  
}  
  
static void OnOfflineEvent(object sender, AnnouncementEventArgs e)  
{  
    Console.WriteLine("Received an offline announcement from {0}",   
e.EndpointDiscoveryMetadata.Address);  
}  
```