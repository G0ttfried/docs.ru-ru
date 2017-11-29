---
title: "Перечисление CorDebugDecodeEventFlagsWindows"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugDecodeEventFlagsWindows
api_location: mscordbi.dll
api_type: COM
ms.assetid: aa6cf962-30ae-4cfd-8895-826deeb46a54
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: facde76ec24d90795de7dfb70bfe5772a6f21531
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="cordebugdecodeeventflagswindows-enumeration"></a><span data-ttu-id="73519-102">Перечисление CorDebugDecodeEventFlagsWindows</span><span class="sxs-lookup"><span data-stu-id="73519-102">CorDebugDecodeEventFlagsWindows Enumeration</span></span>
<span data-ttu-id="73519-103">Предоставляет дополнительную информацию о событиях отладки на платформе Windows.</span><span class="sxs-lookup"><span data-stu-id="73519-103">Provides additional information about debug events on the Windows platform.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73519-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="73519-104">Syntax</span></span>  
  
```  
typedef enum CorDebugDecodeEventFlagsWindows {  
    IS_FIRST_CHANCE = 1,  
} CorDebugDecodeEventFlagsWindows;  
```  
  
## <a name="members"></a><span data-ttu-id="73519-105">Члены</span><span class="sxs-lookup"><span data-stu-id="73519-105">Members</span></span>  
  
|<span data-ttu-id="73519-106">Член</span><span class="sxs-lookup"><span data-stu-id="73519-106">Member</span></span>|<span data-ttu-id="73519-107">Описание</span><span class="sxs-lookup"><span data-stu-id="73519-107">Description</span></span>|  
|------------|-----------------|  
|`IS_FIRST_CHANCE`|<span data-ttu-id="73519-108">Указывает, что событие отладки является первичным исключением.</span><span class="sxs-lookup"><span data-stu-id="73519-108">Indicates that the debug event is a first-chance exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73519-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="73519-109">Remarks</span></span>  
 <span data-ttu-id="73519-110">[ICorDebugProcess6::DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) метод включает `dwFlags` параметра, предоставляющий дополнительные сведения о событии отладки и, значение которого зависит от целевой архитектуры.</span><span class="sxs-lookup"><span data-stu-id="73519-110">The [ICorDebugProcess6::DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) method includes a `dwFlags` parameter that provides additional information about a debug event and whose value is dependent on the target architecture.</span></span> <span data-ttu-id="73519-111">Перечисление `CorDebugDecodeEventFlagsWindows` можно использовать с событиями отладки на платформе Windows.</span><span class="sxs-lookup"><span data-stu-id="73519-111">The `CorDebugDecodeEventFlagsWindows` enumeration can be used with debug events on the Windows platform.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="73519-112">Это перечисление предназначено для использования только в сценариях отладки .NET Native.</span><span class="sxs-lookup"><span data-stu-id="73519-112">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73519-113">Требования</span><span class="sxs-lookup"><span data-stu-id="73519-113">Requirements</span></span>  
 <span data-ttu-id="73519-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="73519-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73519-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="73519-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="73519-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="73519-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="73519-117">**Версии платформы .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73519-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73519-118">См. также</span><span class="sxs-lookup"><span data-stu-id="73519-118">See Also</span></span>  
 [<span data-ttu-id="73519-119">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="73519-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)