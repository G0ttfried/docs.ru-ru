---
title: "&lt;disableCommitThreadStack&gt; элемент"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/disableCommitThreadStack
- http://schemas.microsoft.com/.NetConfiguration/v2.0#disableCommitThreadStack
helpviewer_keywords:
- <disableCommitThreadStack> element
- disableCommitThreadStack element
ms.assetid: 3559d46a-7640-4c72-9a11-7e980768929e
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4a7961c62d46a10767b119c4c55a4b620e1ad782
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltdisablecommitthreadstackgt-element"></a>&lt;disableCommitThreadStack&gt; элемент
Указывает, фиксируется ли весь стек потоков при запуске потока.  
  
 \<configuration>  
\<Среда выполнения >  
\<disableCommitThreadStack >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<disableCommitThreadStack enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|enabled|Обязательный атрибут.<br /><br /> Указывает, отключена ли фиксация всего стека потоков при запуске потока (режим по умолчанию).|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|Значение|Описание|  
|-----------|-----------------|  
|0|Не отключать для среды CLR режим по умолчанию, который заключается в фиксации всего стека потоков при запуске потока.|  
|1|Отключить для среды CLR режим по умолчанию, который заключается в фиксации всего стека потоков при запуске потока.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] .|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
  
## <a name="remarks"></a>Примечания  
 Режим по умолчанию для среды CLR заключается в фиксации всего стека потоков при запуске потока. Если на сервере с ограниченным объемом памяти необходимо создать большое число потоков и большинство из этих потоков будут использовать очень небольшое пространство стека, сервер может работать лучше, если среда не фиксирует весь стек потоков сразу после запуска потока.  
  
> [!NOTE]
>  Неуправляемые узлы могут использовать флаг запуска `STARTUP_DISABLE_COMMITTHREADSTACK` в перечислении [STARTUP_FLAGS](../../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) для достижения такого же результата.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как отключить для среды CLR режим по умолчанию, который заключается в фиксации всего стека потоков при запуске потока.  
  
```xml  
<configuration>  
   <runtime>  
      <disableCommitThreadStack enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также  
 [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)
