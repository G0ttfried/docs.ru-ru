---
title: "Метод ICorDebugProcess::GetHelperThreadID"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugProcess.GetHelperThreadID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetHelperThreadID
helpviewer_keywords:
- GetHelperThreadID method [.NET Framework debugging]
- ICorDebugProcess::GetHelperThreadID method [.NET Framework debugging]
ms.assetid: 84e1e605-37c1-49a5-8e12-35db85654622
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 03e801cb58b8f5c3f658085fcee4288278e545c5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocessgethelperthreadid-method"></a>Метод ICorDebugProcess::GetHelperThreadID
Получает идентификатор потока операционной системы (ОС) вспомогательный внутренний поток отладчика.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetHelperThreadID (  
    [out] DWORD *pThreadID  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pThreadID`  
 [out] Указатель на ОС потока идентификатор вспомогательный внутренний поток отладчика.  
  
## <a name="remarks"></a>Примечания  
 При отладке управляемого и неуправляемого кода это отладчик обязан гарантировать непрерывное потока с указанным Идентификатором, если он попадает на точку останова размещенную отладчиком. Отладчик может возникнуть необходимость скрыть этот поток от пользователя. Если ни один вспомогательный поток существует в процессе, `GetHelperThreadID` метод возвращает нуль в *`pThreadID`.  
  
 Идентификатор потока вспомогательного потока кэшировать нельзя, поскольку со временем может меняться. Необходимо повторно запросить идентификатор потока при каждом событии остановки.  
  
 Идентификатор потока вспомогательный поток отладчика будут правильными для каждой неуправляемой [ICorDebugManagedCallback::CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) события, позволяя тем самым отладчику определить ИД вспомогательного потока и скрыть его от пользователя. Поток, который указан в качестве вспомогательного потока во время неуправляемый `ICorDebugManagedCallback::CreateThread` событие никогда не будет выполняться управляемого пользовательского кода.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl. CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
