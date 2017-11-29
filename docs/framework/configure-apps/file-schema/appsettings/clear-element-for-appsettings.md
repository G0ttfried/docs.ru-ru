---
title: "&lt;Очистить&gt; элемент для &lt;appSettings&gt;"
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 6d18c7be-27db-438b-8fb5-765d396b0b7b
author: guardrex
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ac1e9a86d0c3e1bb1f23b753fd9867effef03ce5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="clear-element-for-appsettings"></a><span data-ttu-id="350d4-102">\<Очистить > элемент для \<appSettings ></span><span class="sxs-lookup"><span data-stu-id="350d4-102">\<clear> element for \<appSettings></span></span>

<span data-ttu-id="350d4-103">Очищает пользовательские параметры приложения.</span><span class="sxs-lookup"><span data-stu-id="350d4-103">Clears custom application settings.</span></span>

<span data-ttu-id="350d4-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="350d4-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="350d4-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="350d4-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="350d4-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Очистить >**</span><span class="sxs-lookup"><span data-stu-id="350d4-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="350d4-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="350d4-107">Syntax</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="350d4-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="350d4-108">Attributes</span></span>

<span data-ttu-id="350d4-109">Нет</span><span class="sxs-lookup"><span data-stu-id="350d4-109">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="350d4-110">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="350d4-110">Parent element</span></span>

|     | <span data-ttu-id="350d4-111">Описание</span><span class="sxs-lookup"><span data-stu-id="350d4-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="350d4-112">**\<appSettings>**</span><span class="sxs-lookup"><span data-stu-id="350d4-112">**\<appSettings>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) | <span data-ttu-id="350d4-113">Содержит пользовательские параметры приложения, такие как пути к файлам, URL-адреса XML-веб-службы или любые другие пользовательские данные конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="350d4-113">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom application configuration information.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="350d4-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="350d4-114">Child elements</span></span>

<span data-ttu-id="350d4-115">Нет</span><span class="sxs-lookup"><span data-stu-id="350d4-115">None</span></span>

## <a name="example"></a><span data-ttu-id="350d4-116">Пример</span><span class="sxs-lookup"><span data-stu-id="350d4-116">Example</span></span>

<span data-ttu-id="350d4-117">Приведенный ниже показано, как очистить настраиваемыми параметрами конфигурации:</span><span class="sxs-lookup"><span data-stu-id="350d4-117">The following example shows how to clear custom configuration settings:</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="350d4-118">См. также</span><span class="sxs-lookup"><span data-stu-id="350d4-118">See also</span></span>

[<span data-ttu-id="350d4-119">Схема файла конфигурации для платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="350d4-119">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)