---
title: Обзор API Защитника Microsoft 365
description: Узнайте о доступных API в Microsoft 365 Defender
keywords: api, apis, обзор, инциденты, инциденты, охота на угрозы, защитник Microsoft 365
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
ms.openlocfilehash: 0fbe8751a9f82a8e264f1a38207744d091b57474
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922190"
---
# <a name="overview-of--microsoft-365-defender-apis"></a><span data-ttu-id="f17cd-104">Обзор API Защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f17cd-104">Overview of  Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="f17cd-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="f17cd-105">**Applies to:**</span></span>

- <span data-ttu-id="f17cd-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f17cd-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f17cd-107">Некоторые сведения относятся к предварительно изданным продуктам, которые могут быть существенно изменены до его коммерческого выпуска.</span><span class="sxs-lookup"><span data-stu-id="f17cd-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="f17cd-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="f17cd-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="f17cd-109">Microsoft 365 Defender построен на платформе, готовой к интеграции.</span><span class="sxs-lookup"><span data-stu-id="f17cd-109">Microsoft 365 Defender is built on top of an integration-ready platform.</span></span>

<span data-ttu-id="f17cd-110">Используйте API Защитника Microsoft 365 для автоматизации рабочего процесса на основе общих таблиц инцидента и расширенных таблиц охоты.</span><span class="sxs-lookup"><span data-stu-id="f17cd-110">Use the Microsoft 365 Defender APIs to automate workflows based on the shared incident and advanced hunting tables.</span></span>

- <span data-ttu-id="f17cd-111">**[Совмещенная очередь](api-incident.md)** инцидентов . Фокус на том, что имеет решающее значение, сгруппив всю область атаки и все влияющие активы вместе в API инцидента.</span><span class="sxs-lookup"><span data-stu-id="f17cd-111">**[Combined incidents queue](api-incident.md)** - Focus on what's critical by grouping the full attack scope and all impacted assets together under the incident API.</span></span>

- <span data-ttu-id="f17cd-112">**[Межпродукционная](api-advanced-hunting.md)** охота на угрозы — использование организационных знаний группы безопасности для охоты за признаками компромисса, создав собственные пользовательские запросы для просеки необработанных данных, собранных в нескольких продуктах защиты.</span><span class="sxs-lookup"><span data-stu-id="f17cd-112">**[Cross-product threat hunting](api-advanced-hunting.md)** - Leverage your security team's organizational knowledge to hunt for signs of compromise, by creating your own custom queries to sift over raw data collected across multiple protection products.</span></span>

<span data-ttu-id="f17cd-113">Наряду с этими API, определенными для Microsoft 365 Defender, каждый из наших других продуктов безопасности предоставляет дополнительные [API,](api-articles.md) которые помогут вам воспользоваться их уникальными возможностями.</span><span class="sxs-lookup"><span data-stu-id="f17cd-113">Along with these Microsoft 365 Defender-specific APIs, each of our other security products expose [additional APIs](api-articles.md) to help you take advantage of their unique capabilities.</span></span>

## <a name="learn-more"></a><span data-ttu-id="f17cd-114">Подробнее</span><span class="sxs-lookup"><span data-stu-id="f17cd-114">Learn more</span></span>

| <span data-ttu-id="f17cd-115">**Понимание доступа к API**</span><span class="sxs-lookup"><span data-stu-id="f17cd-115">**Understand how to access the APIs**</span></span> |
|-|
| [<span data-ttu-id="f17cd-116">Узнайте о квотах API и лицензировании</span><span class="sxs-lookup"><span data-stu-id="f17cd-116">Learn about API quotas and licensing</span></span>](api-terms.md) |
| [<span data-ttu-id="f17cd-117">Доступ к API защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f17cd-117">Access the Microsoft 365 Defender APIs</span></span>](api-access.md) |
| <span data-ttu-id="f17cd-118">**Создание приложений**</span><span class="sxs-lookup"><span data-stu-id="f17cd-118">**Build apps**</span></span> |
| [<span data-ttu-id="f17cd-119">Создание приложения "Hello world"</span><span class="sxs-lookup"><span data-stu-id="f17cd-119">Create a 'Hello world' app</span></span>](api-hello-world.md) |
| [<span data-ttu-id="f17cd-120">Создание приложения для доступа к API Защитника Microsoft 365 от имени пользователя</span><span class="sxs-lookup"><span data-stu-id="f17cd-120">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md) |
| [<span data-ttu-id="f17cd-121">Создание приложения для доступа к Microsoft 365 Defender без пользователя</span><span class="sxs-lookup"><span data-stu-id="f17cd-121">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md) |
| [<span data-ttu-id="f17cd-122">Создание приложения с несколькими партнерами-партнерами для API Защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f17cd-122">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md) |
| <span data-ttu-id="f17cd-123">**Устранение неполадок и обслуживание приложений**</span><span class="sxs-lookup"><span data-stu-id="f17cd-123">**Troubleshoot and maintain your apps**</span></span> |
| [<span data-ttu-id="f17cd-124">Понимание кодов ошибок API</span><span class="sxs-lookup"><span data-stu-id="f17cd-124">Understand API error codes</span></span>](api-error-codes.md) |
| [<span data-ttu-id="f17cd-125">Управление секретами в приложениях с помощью хранилища ключей Azure</span><span class="sxs-lookup"><span data-stu-id="f17cd-125">Manage secrets in your apps with Azure Key Vault</span></span>](/learn/modules/manage-secrets-with-azure-key-vault/) |
| [<span data-ttu-id="f17cd-126">Реализация авторизации OAuth 2.0 для входных данных пользователя</span><span class="sxs-lookup"><span data-stu-id="f17cd-126">Implement OAuth 2.0 authorization for user sign in</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |