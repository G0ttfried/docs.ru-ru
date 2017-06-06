---
title: "Программа регистрации служб WorkFlow (WFServicesReg.exe) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9e92c87b-99c5-4e8d-9d53-7944cc2b47d3
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Программа регистрации служб WorkFlow (WFServicesReg.exe)
Средство регистрации служб Workflow Services \(WFServicesReg.exe\) — это автономное средство, которое можно использовать для добавления, удаления или восстановления элементов конфигурации для служб Windows Workflow Foundation.  
  
## Синтаксис  
  
```  
  
WFServicesReg.exe [-c | -r | -v | -m | -i]  
```  
  
## Заметки  
 Это средство можно найти в следующей папке установки [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)]: %windir%\\Microsoft.NET\\Framework\\v3.5 или %windir%\\Microsoft.NET\\Framework64\\v3.5 на 64\-разрядных компьютерах.  
  
 В следующей таблице представлены параметры, которые могут использоваться со средством регистрации служб Workflow Services \(WFServicesReg.exe\).  
  
|Параметр|Описание|  
|--------------|--------------|  
|`/c`|Настраивает службы Windows Workflow Services.Используется в сценариях установки и восстановления.|  
|`/r`|Удаляет конфигурацию служб Windows Workflow Services.|  
|`/v`|Отображает подробную выходную информацию \(при настройке или удалении\).|  
|`/m`|Включает формат ведения журнала MSI.|  
|`/i`|Сворачивает окно при выполнении приложения.|  
  
## Регистрация  
 Средство проверяет файл Web.config и регистрирует следующие объекты.  
  
-   Ссылочные сборки [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)].  
  
-   Поставщик построения для XOML\-файлов.  
  
-   Обработчики HTTP\-данных для XOML\- и RULES\-файлов.  
  
 Средство проверяет файл Machine.config и регистрирует следующие расширения.  
  
-   behaviorExtensions  
  
-   bindingElementExtensions  
  
-   bindingExtensions  
  
 Средство также регистрирует следующие средства импорта метаданных клиента.  
  
-   policyImporters  
  
-   wsdlImporters  
  
 Средство также регистрирует карты скриптов и обработчики XOML и RULES в метабазе IIS.  
  
 На компьютерах под управлением [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] и [!INCLUDE[wxp](../../../includes/wxp-md.md)] \(IIS 5.1 и [!INCLUDE[iis601](../../../includes/iis601-md.md)]\) регистрируется один набор карт скриптов XOML и RULES.  
  
 На 64\-разрядных компьютерах средство регистрирует карты скриптов режима WOW, если включен переключатель `Enable32BitAppOnWin64`, или собственные 64\-разрядные карты скриптов, если переключатель `Enable32BitAppOnWin64` отключен.  
  
 На компьютерах под управлением [!INCLUDE[wv](../../../includes/wv-md.md)] и Windows Server 2008 \(IIS 7.0 и более поздних версий\) регистрируется два набора обработчиков XOML\- и RULES\-файлов: один для интегрированного режима и один для классического режима.  
  
 На 64\-разрядных компьютерах регистрируется три набора обработчиков \(независимо от состояния переключателя `Enable32BitAppOnWin64`\): один для интегрированного режима, один для классического режима WOW и один для собственного 64\-разрядного классического режима.  
  
> [!NOTE]
>  В отличие от ServiceModelreg.exe средство WFServicesReg.exe не позволяет добавлять, удалять или восстанавливать карты скриптов или обработчики для конкретного веб\-сайта.Пути обхода данной проблемы см. в разделе "Восстановление карт скриптов".  
  
## Сценарии использования  
  
### Установка IIS после установки .NET Framework 3.5  
 На компьютере под управлением [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] установка [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] выполняется перед установкой IIS.Из\-за недоступности метабазы IIS при установке [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] карты скриптов XOML и RULES не устанавливаются.  
  
 После установки IIS можно воспользоваться средством WFServicesReg.exe с переключателем `/c` для установки этих карт скриптов.  
  
### Восстановление карт скриптов  
  
#### Карта скрипта удалена из узла "Веб\-сайты"  
 На компьютере под управлением [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] XOML\- и RULES\-файлы были случайно удалены из узла "Веб\-сайты".Чтобы выполнить восстановление, запустите средство WFServicesReg.exe с переключателем `/c`.  
  
#### Карта скрипта удалена из конкретного веб\-сайта  
 На компьютере под управлением [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] XOML\- и RULES\-файлы были случайно удалены из конкретного веб\-сайта \(например, из веб\-сайта по умолчанию\), а не из узла "Веб\-сайты".  
  
 Чтобы восстановить удаленные обработчики для конкретного веб\-сайта, выполните команду "WFServicesReg.exe \/r" для удаления обработчиков из всех веб\-сайтов, а затем выполните команду "WFServicesReg.exe \/c" для создания соответствующих обработчиков для всех веб\-сайтов.  
  
### Настройка обработчиков после переключения режима IIS  
 Если IIS работает в режиме общей конфигурации и установлена платформа [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)], метабаза IIS настраивается в общем расположении.Если переключить IIS в режим, отличный от режима общей конфигурации, в локальной метабазе не будут содержаться необходимые обработчики.Для правильной настройки метабазы можно импортировать общую метабазу в локальную или выполнить команду "WFServicesReg.exe \/c", позволяющую настроить локальную метабазу.