---
title: "Метод ICorDebugExceptionDebugEvent::GetNativeIP"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 12e6a262-d9ac-49b8-9b80-1e653a2a3819
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 32e75a18645c000562cdd94478c6ef8db41a01a5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugexceptiondebugeventgetnativeip-method"></a>Метод ICorDebugExceptionDebugEvent::GetNativeIP
Получает собственный указатель инструкции для этого события отладки исключения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetNativeIP(  
   [out]CORDB_ADDRESS *pIP  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pIP`  
 [out] Указатель на указатель инструкции для этого события отладки исключения. Дополнительные сведения см. в разделе "Примечания".  
  
## <a name="remarks"></a>Примечания  
 Смысл этого указателя инструкции стека зависит от типа события, как показано в следующей таблице.  
  
|Тип события.|Смысл значения `pStackPointer`|  
|----------------|--------------------------------------|  
|[MANAGED_EXCEPTION_FIRST_CHANCE](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|Адрес инструкции со сбоем.|  
|[MANAGED_EXCEPTION_USER_FIRST_CHANCE](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|Адрес кода в фрейме, указанном [GetStackPointer](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getstackpointer-method.md) метод, где возобновляться, если было вызвано исключение. Исключение может вызывать или не вызывать другой код, например блок catch предложения `try/catch/finally`, выполняемый в этом фрейме.|  
|[MANAGED_EXCEPTION_CATCH_HANDLER_FOUND](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|Адрес кода, где `catch` будет запускаться выполнение обработчика периода, указанного в параметре [GetStackPointer](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getstackpointer-method.md) метод.|  
|[MANAGED_EXCEPTION_UNHANDLED](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|`pIP` имеет значение 0.|  
  
 Тип события можно получить из [ICorDebugDebugEvent::GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) метод.  
  
> [!NOTE]
>  Этот метод доступен только в машинном коде .NET.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorDebugExceptionDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)  
 [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
