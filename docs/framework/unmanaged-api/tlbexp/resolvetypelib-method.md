---
title: "Метод ResolveTypeLib"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ResolveTypeLib
api_location: tlbref.dll
f1_keywords: ResolveTypeLib
helpviewer_keywords:
- ITypeLibResolver::ResolveTypeLib method [.NET Framework]
- ResolveTypeLib method [.NET Framework]
ms.assetid: 95d2aa0d-8eeb-4a9f-a216-5249f7e2c167
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b430b050117243ced9d764045075071278841da2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="resolvetypelib-method"></a><span data-ttu-id="ea7dc-102">Метод ResolveTypeLib</span><span class="sxs-lookup"><span data-stu-id="ea7dc-102">ResolveTypeLib Method</span></span>
<span data-ttu-id="ea7dc-103">Разрешает простое имя библиотеки типов путем возвращения ее полного пути.</span><span class="sxs-lookup"><span data-stu-id="ea7dc-103">Resolves the simple name of a type library by returning its fully qualified path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea7dc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ea7dc-104">Syntax</span></span>  
  
```  
HRESULT ResolveTypeLib(  
    [in]  BSTR      bstrSimpleName,  
    [in]  GUID      tlbid,  
    [in]  LCID      lcid,  
    [in]  USHORT    wMajorVersion,  
    [in]  USHORT    wMinorVersion,  
    [in]  SYSKIND   syskind,  
    [out] BSTR     *pbstrResolvedTlbName);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ea7dc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ea7dc-105">Parameters</span></span>  
 `bstrSimpleName`  
 <span data-ttu-id="ea7dc-106">[in] Объект [BSTR](http://msdn.microsoft.com/en-us/1b2d7d2c-47af-4389-a6b6-b01b7e915228) , содержащий простое имя библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="ea7dc-106">[in] A [BSTR](http://msdn.microsoft.com/en-us/1b2d7d2c-47af-4389-a6b6-b01b7e915228) that contains the simple name of the type library.</span></span>  
  
 `tlbid`  
 <span data-ttu-id="ea7dc-107">[in] Идентификатор GUID, назначенный в библиотеку типов в реестре.</span><span class="sxs-lookup"><span data-stu-id="ea7dc-107">[in] The GUID assigned to the type library in the registry.</span></span>  
  
 `lcid`  
 <span data-ttu-id="ea7dc-108">[in] Локализация идентификатор библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="ea7dc-108">[in] The localization ID of the type library.</span></span>  
  
 `wMajorVersion`  
 <span data-ttu-id="ea7dc-109">[in] Основной номер версии библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="ea7dc-109">[in] The major version number of the type library.</span></span> <span data-ttu-id="ea7dc-110">Например, для версии *x.y*, основной номер версии — *x*.</span><span class="sxs-lookup"><span data-stu-id="ea7dc-110">For example, for version *x.y*, the major version number is *x*.</span></span>  
  
 `wMinorVersion`  
 <span data-ttu-id="ea7dc-111">[in] Дополнительный номер версии библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="ea7dc-111">[in] The minor version number of the type library.</span></span> <span data-ttu-id="ea7dc-112">Например, для версии *x.y*, дополнительный номер версии — *y*.</span><span class="sxs-lookup"><span data-stu-id="ea7dc-112">For example, for version *x.y*, the minor version number is *y*.</span></span>  
  
 `syskind`  
 <span data-ttu-id="ea7dc-113">[in] Объект [SYSKIND](http://msdn.microsoft.com/en-us/662048b2-59a8-48ca-9e4f-2f9a5306faa1) флаг, определяющий операционная среда.</span><span class="sxs-lookup"><span data-stu-id="ea7dc-113">[in] A [SYSKIND](http://msdn.microsoft.com/en-us/662048b2-59a8-48ca-9e4f-2f9a5306faa1) flag that identifies the operating environment.</span></span> <span data-ttu-id="ea7dc-114">Общие значения: SYS_WIN32 и SYS_WIN64.</span><span class="sxs-lookup"><span data-stu-id="ea7dc-114">Common values are SYS_WIN32 and SYS_WIN64.</span></span>  
  
 `pbstrResolvedTlbName`  
 <span data-ttu-id="ea7dc-115">[out] Указатель на [BSTR](http://msdn.microsoft.com/en-us/1b2d7d2c-47af-4389-a6b6-b01b7e915228) , содержащее полный путь к библиотеке типов в `bstrSimpleName` параметра.</span><span class="sxs-lookup"><span data-stu-id="ea7dc-115">[out] A pointer to a [BSTR](http://msdn.microsoft.com/en-us/1b2d7d2c-47af-4389-a6b6-b01b7e915228) that contains the full path of the type library named in the `bstrSimpleName` parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea7dc-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="ea7dc-116">Remarks</span></span>  
 <span data-ttu-id="ea7dc-117">`ResolveTypeLib` Метод вызывается методом [функция LoadTypeLibWithResolver](../../../../docs/framework/unmanaged-api/tlbexp/loadtypelibwithresolver-function.md) во время [Tlbexp.exe (программа экспорта библиотек типов)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) обработки.</span><span class="sxs-lookup"><span data-stu-id="ea7dc-117">The `ResolveTypeLib` method is called by the [LoadTypeLibWithResolver function](../../../../docs/framework/unmanaged-api/tlbexp/loadtypelibwithresolver-function.md) during [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) processing.</span></span>  
  
 <span data-ttu-id="ea7dc-118">Пользовательские реализации этого интерфейса должны возвращать [BSTR](http://msdn.microsoft.com/en-us/1b2d7d2c-47af-4389-a6b6-b01b7e915228) , содержащее полный путь к библиотеке типов в `bstrSimpleName` параметра.</span><span class="sxs-lookup"><span data-stu-id="ea7dc-118">Custom implementations of this interface must return a [BSTR](http://msdn.microsoft.com/en-us/1b2d7d2c-47af-4389-a6b6-b01b7e915228) that contains the full path of the type library named in the `bstrSimpleName` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea7dc-119">Требования</span><span class="sxs-lookup"><span data-stu-id="ea7dc-119">Requirements</span></span>  
 <span data-ttu-id="ea7dc-120">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea7dc-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea7dc-121">**Заголовок:** TlbRef.idl, TlbRef.h</span><span class="sxs-lookup"><span data-stu-id="ea7dc-121">**Header:** TlbRef.idl, TlbRef.h</span></span>  
  
 <span data-ttu-id="ea7dc-122">**Библиотека:** TlbRef.lib</span><span class="sxs-lookup"><span data-stu-id="ea7dc-122">**Library:** TlbRef.lib</span></span>  
  
 <span data-ttu-id="ea7dc-123">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea7dc-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea7dc-124">См. также</span><span class="sxs-lookup"><span data-stu-id="ea7dc-124">See Also</span></span>  
 [<span data-ttu-id="ea7dc-125">Вспомогательные функции Tlbexp</span><span class="sxs-lookup"><span data-stu-id="ea7dc-125">Tlbexp Helper Functions</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/index.md)  
 [<span data-ttu-id="ea7dc-126">LoadTypeLibEx</span><span class="sxs-lookup"><span data-stu-id="ea7dc-126">LoadTypeLibEx</span></span>](http://msdn.microsoft.com/en-us/56a7f9e1-810b-4a42-aa4d-691f4304f5ef)