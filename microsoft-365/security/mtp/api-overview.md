---
title: Обзор API Microsoft 365 Defender
description: Узнайте о доступных API в Microsoft 365 Defender
keywords: API, API, обзор, инцидент, инциденты, охота на угрозы, Защитник Microsoft 365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 8e06d4b4f7c895b532091c73e8269411fb38bf21
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931006"
---
# <a name="overview-of--microsoft-365-defender-apis"></a><span data-ttu-id="49d08-104">Обзор API Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="49d08-104">Overview of  Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="49d08-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="49d08-105">**Applies to:**</span></span>

- <span data-ttu-id="49d08-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="49d08-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="49d08-107">Некоторые сведения относятся к предварительно выпущенным продуктам, которые могут быть существенно изменены до его коммерческого выпуска.</span><span class="sxs-lookup"><span data-stu-id="49d08-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="49d08-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="49d08-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="49d08-109">Microsoft 365 Defender построен на платформе, готовой к интеграции.</span><span class="sxs-lookup"><span data-stu-id="49d08-109">Microsoft 365 Defender is built on top of an integration-ready platform.</span></span>

<span data-ttu-id="49d08-110">Используйте API Microsoft 365 Defender для автоматизации рабочего процесса на основе общих таблиц инцидента и таблицы расширенных охоты.</span><span class="sxs-lookup"><span data-stu-id="49d08-110">Use the Microsoft 365 Defender APIs to automate workflows based on the shared incident and advanced hunting tables.</span></span>

- <span data-ttu-id="49d08-111">**[Объединенная очередь инцидентов](api-incident.md)** — сгруппировать всю область атаки и все активы, на которые влияет API инцидентов, сосредоточьвшись на том, что является критически важным.</span><span class="sxs-lookup"><span data-stu-id="49d08-111">**[Combined incidents queue](api-incident.md)** - Focus on what's critical by grouping the full attack scope and all impacted assets together under the incident API.</span></span>

- <span data-ttu-id="49d08-112">**[Кросспроигрывная](api-advanced-hunting.md)** охота на угрозы — используйте организационные знания вашей группы безопасности, чтобы искать признаки компрометации, создавая собственные пользовательские запросы для иссылки необработанных данных, собранных в нескольких продуктах защиты.</span><span class="sxs-lookup"><span data-stu-id="49d08-112">**[Cross-product threat hunting](api-advanced-hunting.md)** - Leverage your security team's organizational knowledge to hunt for signs of compromise, by creating your own custom queries to sift over raw data collected across multiple protection products.</span></span>

<span data-ttu-id="49d08-113">Наряду с этими API Для Защитника Microsoft 365 каждый из наших других продуктов безопасности предоставляет дополнительные [API,](api-articles.md) которые помогут вам воспользоваться их уникальными возможностями.</span><span class="sxs-lookup"><span data-stu-id="49d08-113">Along with these Microsoft 365 Defender-specific APIs, each of our other security products expose [additional APIs](api-articles.md) to help you take advantage of their unique capabilities.</span></span>

## <a name="learn-more"></a><span data-ttu-id="49d08-114">Подробнее</span><span class="sxs-lookup"><span data-stu-id="49d08-114">Learn more</span></span>

| <span data-ttu-id="49d08-115">**Как получить доступ к API**</span><span class="sxs-lookup"><span data-stu-id="49d08-115">**Understand how to access the APIs**</span></span> |
|-|
| [<span data-ttu-id="49d08-116">Узнайте о квотах API и лицензировании</span><span class="sxs-lookup"><span data-stu-id="49d08-116">Learn about API quotas and licensing</span></span>](api-terms.md) |
| [<span data-ttu-id="49d08-117">Доступ к API Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="49d08-117">Access the Microsoft 365 Defender APIs</span></span>](api-access.md) |
| <span data-ttu-id="49d08-118">**Создание приложений**</span><span class="sxs-lookup"><span data-stu-id="49d08-118">**Build apps**</span></span> |
| [<span data-ttu-id="49d08-119">Создание приложения "Hello world"</span><span class="sxs-lookup"><span data-stu-id="49d08-119">Create a 'Hello world' app</span></span>](api-hello-world.md) |
| [<span data-ttu-id="49d08-120">Создание приложения для доступа к API Microsoft 365 Defender от имени пользователя</span><span class="sxs-lookup"><span data-stu-id="49d08-120">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md) |
| [<span data-ttu-id="49d08-121">Создание приложения для доступа к Защитнику Microsoft 365 без пользователя</span><span class="sxs-lookup"><span data-stu-id="49d08-121">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md) |
| [<span data-ttu-id="49d08-122">Создание приложения с мультиязычным доступом партнеров к API Защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="49d08-122">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md) |
| <span data-ttu-id="49d08-123">**Устранение неполадок и обслуживание приложений**</span><span class="sxs-lookup"><span data-stu-id="49d08-123">**Troubleshoot and maintain your apps**</span></span> |
| [<span data-ttu-id="49d08-124">Коды ошибок API</span><span class="sxs-lookup"><span data-stu-id="49d08-124">Understand API error codes</span></span>](api-error-codes.md) |
| [<span data-ttu-id="49d08-125">Управление секретами в приложениях с помощью Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="49d08-125">Manage secrets in your apps with Azure Key Vault</span></span>](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/) |
| [<span data-ttu-id="49d08-126">Реализация авторизации OAuth 2.0 для входов пользователей</span><span class="sxs-lookup"><span data-stu-id="49d08-126">Implement OAuth 2.0 authorization for user sign in</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |
