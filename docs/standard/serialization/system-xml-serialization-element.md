---
title: "Элемент &lt;system.xml.serialization&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- system.xml.serialization element
- XML serialization, configuration
- <system.xml.serialization> element
ms.assetid: 3ce45919-388a-418c-8968-6df0372c73ec
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: d673c76e57ffb8315e97b1695dbcbc1f4fe0aab9
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="ltsystemxmlserializationgt-element"></a>Элемент &lt;system.xml.serialization&gt;
Элемент верхнего уровня для управления XML-сериализацией. Дополнительные сведения о файлах конфигурации см. в разделе [Схема файла конфигурации](../../../docs/framework/configure-apps/file-schema/index.md).  
  
 \<configuration>  
\<system.xml.serialization>  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.xml.serialization>  
</system.xml.serialization>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Отсутствует.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[Элемент \<dateTimeSerialization>](../../../docs/standard/serialization/datetimeserialization-element.md)|Определяет режим сериализации объектов <xref:System.DateTime>.|  
|[Элемент \<schemaImporterExtensions>](../../../docs/standard/serialization/schemaimporterextensions-element.md)|Содержит типы, которые использует <xref:System.Xml.Serialization.XmlSchemaImporter> для сопоставления типов XSD с типами .NET Framework.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[Элемент \<configuration>](../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Корневой элемент в любом файле конфигурации, который используется средой CLR и приложениями .NET Framework.|  
  
## <a name="example"></a>Пример  
 В следующем примере кода показан способ указания режима сериализации объекта <xref:System.DateTime> и добавление типов, используемых <xref:System.Xml.Serialization.XmlSchemaImporter> при сопоставлении типов XSD с типами .NET Framework.  
  
```xml  
<system.xml.serialization>  
    <xmlSerializer checkDeserializeAdvances="false" />  
    <dateTimeSerialization mode = "Local" />  
    <schemaImporterExtensions>  
        <add   
        name = "MobileCapabilities"   
        type = "System.Web.Mobile.MobileCapabilities,   
        System.Web.Mobile, Version - 2.0.0.0, Culture = neuutral,   
        PublicKeyToken = b03f5f6f11d40a3a" />  
    </schemaImporterExtensions>  
</system.sxml.serialization>  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Xml.Serialization.XmlSchemaImporter>  
 <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>  
 [Схема файла конфигурации](../../../docs/framework/configure-apps/file-schema/index.md)  
 [Элемент \<dateTimeSerialization>](../../../docs/standard/serialization/datetimeserialization-element.md)  
 [Элемент \<schemaImporterExtensions>](../../../docs/standard/serialization/schemaimporterextensions-element.md)  
 [Элемент \<add> для элемента \<xmlSchemaImporterExtensions>](../../../docs/standard/serialization/add-element-for-xmlschemaimporterextensions.md)
