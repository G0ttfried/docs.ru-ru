---
title: "Метод IMetaDataImport::GetCustomAttributeProps"
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
- IMetaDataImport.GetCustomAttributeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetCustomAttributeProps
helpviewer_keywords:
- GetCustomAttributeProps method [.NET Framework metadata]
- IMetaDataImport::GetCustomAttributeProps method [.NET Framework metadata]
ms.assetid: 6eefb243-a281-41c1-bcdc-7e17513bc446
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b1e6ef9443b99b3e6b36154558ce226d421dbc0a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgetcustomattributeprops-method"></a>Метод IMetaDataImport::GetCustomAttributeProps
Возвращает значение настраиваемого атрибута по указанному токену метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetCustomAttributeProps (  
   [in]            mdCustomAttribute   cv,  
   [out, optional] mdToken             *ptkObj,  
   [out, optional] mdToken             *ptkType,  
   [out, optional] void const          **ppBlob,  
   [out, optional] ULONG               *pcbSize  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `cv`  
 [in] Токен метаданных, который представляет извлекаемый пользовательский атрибут.  
  
 `ptkObj`  
 [out, optional] Токен метаданных, представляющий объект, который изменяет пользовательский атрибут. Это значение может быть любым типом токена метаданных, кроме `mdCustomAttribute`.  
  
 `ptkType`  
 [out, optional] Токен метаданных `mdMethodDef` или `mdMemberRef`, представляющий <xref:System.Type> возвращаемого пользовательского атрибута.  
  
 `ppBlob`  
 [out, optional] Указатель на массив данных, который является значением пользовательского атрибута.  
  
 `pcbSize`  
 [out, optional] Размер в байтах данных, возвращаемых в *`ppBlob`.  
  
## <a name="remarks"></a>Примечания  
 Пользовательский атрибут хранится в виде массива данных, в формате, который поддерживается подсистемой метаданных.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
