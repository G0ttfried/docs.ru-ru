---
title: "Метод IHostTaskManager::ReverseEnterRuntime"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.ReverseEnterRuntime
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::ReverseEnterRuntime
helpviewer_keywords:
- IHostTaskManager::ReverseEnterRuntime method [.NET Framework hosting]
- ReverseEnterRuntime method [.NET Framework hosting]
ms.assetid: b1e26bff-d3ea-436e-9867-29720df999f4
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1c8d84cbd02527a026206d6fa172a9d3f40683fb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ihosttaskmanagerreverseenterruntime-method"></a><span data-ttu-id="1e95a-102">Метод IHostTaskManager::ReverseEnterRuntime</span><span class="sxs-lookup"><span data-stu-id="1e95a-102">IHostTaskManager::ReverseEnterRuntime Method</span></span>
<span data-ttu-id="1e95a-103">Уведомляет узел, что вызов в среде (CLR) из неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="1e95a-103">Notifies the host that a call is being made into the common language runtime (CLR) from unmanaged code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e95a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1e95a-104">Syntax</span></span>  
  
```  
HRESULT ReverseEnterRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="1e95a-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="1e95a-105">Return Value</span></span>  
  
|<span data-ttu-id="1e95a-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1e95a-106">HRESULT</span></span>|<span data-ttu-id="1e95a-107">Описание</span><span class="sxs-lookup"><span data-stu-id="1e95a-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1e95a-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="1e95a-108">S_OK</span></span>|<span data-ttu-id="1e95a-109">`ReverseEnterRuntime`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="1e95a-109">`ReverseEnterRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="1e95a-110">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1e95a-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1e95a-111">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="1e95a-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1e95a-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1e95a-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1e95a-113">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="1e95a-113">The call timed out.</span></span>|  
|<span data-ttu-id="1e95a-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1e95a-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1e95a-115">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="1e95a-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1e95a-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1e95a-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1e95a-117">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="1e95a-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1e95a-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1e95a-118">E_FAIL</span></span>|<span data-ttu-id="1e95a-119">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="1e95a-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1e95a-120">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="1e95a-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1e95a-121">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="1e95a-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="1e95a-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="1e95a-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="1e95a-123">Недостаточно памяти для выполнения запрашиваемого выделения ресурсов.</span><span class="sxs-lookup"><span data-stu-id="1e95a-123">Not enough memory is available to complete the requested resource allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1e95a-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="1e95a-124">Remarks</span></span>  
 <span data-ttu-id="1e95a-125">Если в среде CLR вызов из последовательность, которая была создана в управляемом коде, при каждом вызове функции `ReverseEnterRuntime` соответствует вызов [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md).</span><span class="sxs-lookup"><span data-stu-id="1e95a-125">If the call into the CLR is made from a sequence that originated in managed code, each call to `ReverseEnterRuntime` corresponds to a call to [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1e95a-126">Вызовы могут осуществляться из неуправляемого кода без вложения.</span><span class="sxs-lookup"><span data-stu-id="1e95a-126">Calls can originate from unmanaged code without being nested.</span></span> <span data-ttu-id="1e95a-127">В этом случае отсутствует вызов к [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), или `ReverseLeaveRuntime`и число вызовов `ReverseEnterRuntime` не равно числу вызовов `ReverseLeaveRuntime`.</span><span class="sxs-lookup"><span data-stu-id="1e95a-127">In this case, there is no call to [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), or `ReverseLeaveRuntime`, and the number of calls to `ReverseEnterRuntime` does not equal the number of calls to `ReverseLeaveRuntime`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e95a-128">Требования</span><span class="sxs-lookup"><span data-stu-id="1e95a-128">Requirements</span></span>  
 <span data-ttu-id="1e95a-129">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1e95a-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e95a-130">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1e95a-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1e95a-131">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1e95a-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1e95a-132">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e95a-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e95a-133">См. также</span><span class="sxs-lookup"><span data-stu-id="1e95a-133">See Also</span></span>  
 [<span data-ttu-id="1e95a-134">ICLRTask-интерфейс</span><span class="sxs-lookup"><span data-stu-id="1e95a-134">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="1e95a-135">ICLRTaskManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="1e95a-135">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="1e95a-136">IHostTask-интерфейс</span><span class="sxs-lookup"><span data-stu-id="1e95a-136">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="1e95a-137">IHostTaskManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="1e95a-137">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)