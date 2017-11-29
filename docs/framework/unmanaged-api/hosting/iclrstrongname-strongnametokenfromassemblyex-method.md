---
title: "Метод ICLRStrongName::StrongNameTokenFromAssemblyEx"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.StrongNameTokenFromAssemblyEx
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::StrongNameTokenFromAssemblyEx
helpviewer_keywords:
- StrongNameTokenFromAssemblyEx method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameTokenFromAssemblyEx method [.NET Framework hosting]
ms.assetid: 648ea90e-5e60-40a0-a56a-3e61bf2fba7c
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e46216f9e64d76188d60dbfcfc8e5113f2409b07
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrstrongnamestrongnametokenfromassemblyex-method"></a><span data-ttu-id="aa92f-102">Метод ICLRStrongName::StrongNameTokenFromAssemblyEx</span><span class="sxs-lookup"><span data-stu-id="aa92f-102">ICLRStrongName::StrongNameTokenFromAssemblyEx Method</span></span>
<span data-ttu-id="aa92f-103">Создает маркер строгого имени из указанного файла сборки и возвращает открытый ключ, представляющий маркер.</span><span class="sxs-lookup"><span data-stu-id="aa92f-103">Creates a strong name token from the specified assembly file, and returns the public key that the token represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa92f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aa92f-104">Syntax</span></span>  
  
```  
HRESULT StrongNameTokenFromAssemblyEx (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="aa92f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="aa92f-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="aa92f-106">[in] Путь к файлу переносимого исполняемого (PE) для сборки.</span><span class="sxs-lookup"><span data-stu-id="aa92f-106">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="aa92f-107">[out] Возвращаемый строгое имя маркера.</span><span class="sxs-lookup"><span data-stu-id="aa92f-107">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="aa92f-108">[out] Размер в байтах строгое имя маркера.</span><span class="sxs-lookup"><span data-stu-id="aa92f-108">[out] The size, in bytes, of the strong name token.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="aa92f-109">[out] Возвращаемый открытый ключ.</span><span class="sxs-lookup"><span data-stu-id="aa92f-109">[out] The returned public key.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="aa92f-110">[out] Размер в байтах для открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="aa92f-110">[out] The size, in bytes, of the public key.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aa92f-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="aa92f-111">Return Value</span></span>  
 <span data-ttu-id="aa92f-112">`S_OK`Если метод успешно завершена; в противном случае — значение HRESULT, указывающее на сбой (в разделе [часто встречающихся значений HRESULT](http://go.microsoft.com/fwlink/?LinkId=213878) список).</span><span class="sxs-lookup"><span data-stu-id="aa92f-112">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aa92f-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="aa92f-113">Remarks</span></span>  
 <span data-ttu-id="aa92f-114">Маркер строгого имени — это сокращенная форма открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="aa92f-114">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="aa92f-115">Маркер является 64-разрядный хэш, который создается из открытого ключа, используемого для подписания сборки.</span><span class="sxs-lookup"><span data-stu-id="aa92f-115">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="aa92f-116">Маркер является частью строгого имени для сборки и может быть считано из метаданных сборки.</span><span class="sxs-lookup"><span data-stu-id="aa92f-116">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="aa92f-117">После получения ключа и создания маркера, необходимо вызвать [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) метод для освобождения выделенной памяти.</span><span class="sxs-lookup"><span data-stu-id="aa92f-117">After the key is retrieved and the token is created, you should call the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa92f-118">Требования</span><span class="sxs-lookup"><span data-stu-id="aa92f-118">Requirements</span></span>  
 <span data-ttu-id="aa92f-119">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa92f-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa92f-120">**Заголовок:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="aa92f-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="aa92f-121">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="aa92f-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aa92f-122">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa92f-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa92f-123">См. также</span><span class="sxs-lookup"><span data-stu-id="aa92f-123">See Also</span></span>  
 [<span data-ttu-id="aa92f-124">Метод StrongNameTokenFromAssembly</span><span class="sxs-lookup"><span data-stu-id="aa92f-124">StrongNameTokenFromAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassembly-method.md)  
 [<span data-ttu-id="aa92f-125">Iclrstrongname-интерфейс</span><span class="sxs-lookup"><span data-stu-id="aa92f-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)