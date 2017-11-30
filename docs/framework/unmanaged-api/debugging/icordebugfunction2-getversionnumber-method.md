---
title: "Метод ICorDebugFunction2::GetVersionNumber"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFunction2.GetVersionNumber
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFunction2::GetVersionNumber
helpviewer_keywords:
- ICorDebugFunction2::GetVersionNumber method [.NET Framework debugging]
- GetVersionNumber method, ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: e3a1ce48-9bb9-4ed6-a5fe-5e1819a6333f
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 37b9e34174d88be08c92c54906ebd20977dc266a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugfunction2getversionnumber-method"></a>Метод ICorDebugFunction2::GetVersionNumber
Возвращает версию этой функции изменить и продолжить.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetVersionNumber (  
    [out] ULONG32   *pnVersion  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pnVersion`  
 [out] Указатель на целое число, номер версии, представленного этим объектом ICorDebugFunction2 функции.  
  
## <a name="remarks"></a>Примечания  
 Среда выполнения хранит информацию о количестве изменений, произошедших в каждый модуль во время сеанса отладки. Номер версии функции — одно больше числа редактирования, которая представлена функция. Исходную версию функции — версия 1. Номер увеличивается для модуля каждый раз [ICorDebugModule2::ApplyChanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md) вызывается для данного модуля. Таким образом Если тело функции был заменен в первый и третий вызов `ICorDebugModule2::ApplyChanges`, `GetVersionNumber` может вернуть 1, 2 или 4 для этой функции, но не версию 3. (Эта функция будет иметь версии 3 не).  
  
 Номер версии отслеживается отдельно для каждого модуля. Таким образом при выполнении четырех изменений на модуле 1 и модуль 2 следующее изменение на модуле 1 присвоит номер версии 6 всем измененным функциям в модуле 1. Если данное изменение затрагивает модуль 2, функции модуля 2 получает номер версии 2.  
  
 Номер версии, получаемой в результате `GetVersionNumber` метод может быть ниже, чем у полученных [ICorDebugFunction::GetCurrentVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md).  
  
 [ICorDebugCode::GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md) метод выполняет те же функции, как `ICorDebugFunction2::GetVersionNumber`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]