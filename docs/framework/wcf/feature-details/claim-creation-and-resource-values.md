---
title: "Создание утверждений и значения ресурсов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- claims [WCF], creation and resource values
ms.assetid: 30431f76-cbe7-4bad-bad7-8e43e23a82d4
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8afcd09e09cefcd08e3cb92aba980f599cf44d11
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="claim-creation-and-resource-values"></a>Создание утверждений и значения ресурсов
Класс <xref:System.IdentityModel.Claims.Claim> предоставляет несколько методов для создания экземпляров встроенных типов утверждений. Из этих методов следующие не выполняют проверки семантики или формата переданного ресурса:  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateDnsClaim%2A>  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateHashClaim%2A> (не проверяет длину или содержимое байтового массива).  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateNameClaim%2A>  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateSpnClaim%2A>  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateThumbprintClaim%2A> (не проверяет длину или содержимое байтового массива).  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateUpnClaim%2A>  
  
 При вызове перечисленных выше методов необходимо обеспечить, чтобы передаваемые значения ресурсов имели правильный формат или содержали правильную информацию (или и то, и другое).  
  
 Следующие методы принимают определенные типы:  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateDenyOnlyWindowsSidClaim%2A>  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateMailAddressClaim%2A>  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateRsaClaim%2A>  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateUriClaim%2A>  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateWindowsSidClaim%2A>  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateX500DistinguishedNameClaim%2A>  
  
## <a name="see-also"></a>См. также  
 <xref:System.IdentityModel.Claims.Claim>  
 <xref:System.IdentityModel.Claims.ClaimSet>  
 [Управление утверждениями и авторизацией с помощью модели удостоверения](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)
