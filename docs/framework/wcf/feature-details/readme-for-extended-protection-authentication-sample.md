---
title: "Файл ReadMe для образца проверки подлинности с расширенной защитой"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 80bf2e97-398d-4db5-9040-d96478a2ccab
caps.latest.revision: "3"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 78e787c129c0161e8730472124ee4162e2d1ba9d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="readme-for-extended-protection-authentication-sample"></a>Файл ReadMe для образца проверки подлинности с расширенной защитой
Расширенная защита-это технология безопасности для защиты от атак в середине (MITM), в которых злоумышленник (» в посредник»), перехватывает клиентские учетные данные и использует их для доступа к защищенным ресурсам на сервере предполагаемого клиента.  
  
 Дополнительные сведения см. в разделе [расширенная защита для проверки подлинности Обзор](../../../../docs/framework/wcf/feature-details/extended-protection-for-authentication-overview.md).  
  
> [!NOTE]
>  Этот образец работает только в случае размещения в службах IIS. Он не работает на сервере разработки Visual Studio, поскольку этот сервер не поддерживает HTTPS.  
  
## <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1.  Установите службы IIS на компьютер из окна «Установка и удаление программ -> Компоненты Windows».  
  
2.  Включите проверку подлинности Windows в окне «Компоненты Windows: службы IIS -> службы Интернета -> Безопасность -> Проверка подлинности Windows».  
  
3.  Включите активацию HTTP в окне «Компоненты Windows: платформа Microsoft .NET Framework 3.5.1 -> Активация Windows Communication Foundation HTTP».  
  
4.  Для работы этого образца клиенту необходимо установить защищенный канал с сервером, для чего требуется наличие сертификата сервера, который может устанавливаться из диспетчера служб IIS.  
  
    1.  Откройте окно «Диспетчер служб IIS -> Сертификаты сервера» (с вкладки представления компонентов).  
  
    2.  Для тестирования этого образца можно создать самозаверяющий сертификат. (Чтобы не выводить в Internet Explorer запрос об отсутствии защиты сертификата, можно установить его в хранилище «Доверенные корневые центры сертификации».)  
  
5.  Перейдите в область «Действия» для веб-узла по умолчанию. Нажмите кнопку «Изменить узел» -> «Привязки». Добавьте тип HTTPS, если он отсутствует, указав номер порта 443, и назначьте SSL-сертификат, созданный на предыдущем шаге.  
  
6.  Постройте службу. В службах IIS будет создан виртуальный каталог (из действия после построения, указанного в свойствах проекта) и скопированы DLL-файлы, SVC-файлы и файлы конфигурации, необходимые для размещения службы в Интернете.  
  
7.  Откройте диспетчер служб IIS. Щелкните правой кнопкой мыши виртуальный каталог (ExtendedProtection), созданный на предыдущем шаге, и выберите команду «Преобразовать в приложение».  
  
8.  Откройте модуль проверки подлинности в диспетчере служб IIS для этого виртуального каталога и включите проверку подлинности Windows.  
  
9. Откройте дополнительные параметры проверки подлинности Windows для этого виртуального каталога и установите для нее значение «Требуется», поскольку в образце соответствующий параметр ExtendedProtection имеет значение «Всегда».  
  
10. Проверить работу службы можно, обратившись по URL-адресу из окна браузера. Чтобы получить доступ к этому URL-адресу с другого компьютера, убедитесь, что в брандмауэре открыты все входящие подключения HTTP и HTTPS.  
  
11. Откройте файл конфигурации клиента и укажите полное имя компьютера для \<клиента >- \<endpoint >-атрибут адреса, заменив << full_machine_name >>.  
  
12. Запустите клиент. Клиент обменивается данными со службой, устанавливая защищенный канал и используя расширенную защиту не базе канала.
