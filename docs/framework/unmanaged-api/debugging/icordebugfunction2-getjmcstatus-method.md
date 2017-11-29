---
title: "Метод ICorDebugFunction2::GetJMCStatus"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFunction2.GetJMCStatus
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFunction2::GetJMCStatus
helpviewer_keywords:
- ICorDebugFunction2::GetJMCStatus method [.NET Framework debugging]
- GetJMCStatus method [.NET Framework debugging]
ms.assetid: 840a71ed-bf5a-4f5e-8ed6-762222b34493
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: dc5e5e6a0ff0784825a69ba1873224a537ad46c3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugfunction2getjmcstatus-method"></a><span data-ttu-id="5e1d3-102">Метод ICorDebugFunction2::GetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="5e1d3-102">ICorDebugFunction2::GetJMCStatus Method</span></span>
<span data-ttu-id="5e1d3-103">Возвращает значение, указывающее, помечена ли функция, представленного этим объектом ICorDebugFunction2 как пользовательский код.</span><span class="sxs-lookup"><span data-stu-id="5e1d3-103">Gets a value that indicates whether the function that is represented by this ICorDebugFunction2 object is marked as user code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e1d3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5e1d3-104">Syntax</span></span>  
  
```  
HRESULT GetJMCStatus (  
    [out] BOOL   *pbIsJustMyCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5e1d3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5e1d3-105">Parameters</span></span>  
 `pbIsJustMyCode`  
 <span data-ttu-id="5e1d3-106">[out] Указатель на значение типа Boolean, `true`, если это функция, помеченная как код пользователя; в противном случае — значение `false`.</span><span class="sxs-lookup"><span data-stu-id="5e1d3-106">[out] A pointer to a Boolean value that is `true`, if this function is marked as user code; otherwise, the value is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5e1d3-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="5e1d3-107">Remarks</span></span>  
 <span data-ttu-id="5e1d3-108">Если функция представленный этим `ICorDebugFunction2` не может быть отлажен `pbIsJustMyCode` всегда будет `false`.</span><span class="sxs-lookup"><span data-stu-id="5e1d3-108">If the function represented by this `ICorDebugFunction2` cannot be debugged, `pbIsJustMyCode` will always be `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e1d3-109">Требования</span><span class="sxs-lookup"><span data-stu-id="5e1d3-109">Requirements</span></span>  
 <span data-ttu-id="5e1d3-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e1d3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e1d3-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5e1d3-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5e1d3-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5e1d3-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5e1d3-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e1d3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>