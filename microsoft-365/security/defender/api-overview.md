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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 496ad5695d9cd491817bad5daf3c76a02addefd1
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2021
ms.locfileid: "51904192"
---
# <a name="overview-of--microsoft-365-defender-apis"></a><span data-ttu-id="1733d-104">Обзор API Защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1733d-104">Overview of  Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="1733d-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="1733d-105">**Applies to:**</span></span>

- <span data-ttu-id="1733d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1733d-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1733d-107">Некоторые сведения относятся к предварительным выпускам продуктов, которые могут быть существенно изменены до коммерческого выпуска.</span><span class="sxs-lookup"><span data-stu-id="1733d-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="1733d-108">Корпорация Майкрософт не дает никаких гарантий, явных или подразумеваемых, относительно предоставленных здесь сведений.</span><span class="sxs-lookup"><span data-stu-id="1733d-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="1733d-109">Microsoft 365 Defender построен на платформе, готовой к интеграции.</span><span class="sxs-lookup"><span data-stu-id="1733d-109">Microsoft 365 Defender is built on top of an integration-ready platform.</span></span>

<span data-ttu-id="1733d-110">Используйте API Защитника Microsoft 365 для автоматизации рабочего процесса на основе общих таблиц инцидента и расширенных таблиц охоты.</span><span class="sxs-lookup"><span data-stu-id="1733d-110">Use the Microsoft 365 Defender APIs to automate workflows based on the shared incident and advanced hunting tables.</span></span>

- <span data-ttu-id="1733d-111">**[Совмещенная очередь](api-incident.md)** инцидентов . Фокус на том, что имеет решающее значение, сгруппив всю область атаки и все влияющие активы вместе в API инцидента.</span><span class="sxs-lookup"><span data-stu-id="1733d-111">**[Combined incidents queue](api-incident.md)** - Focus on what's critical by grouping the full attack scope and all impacted assets together under the incident API.</span></span>

- <span data-ttu-id="1733d-112">**[Межпродукционная](api-advanced-hunting.md)** охота на угрозы — использование организационных знаний группы безопасности для охоты за признаками компромисса, создав собственные пользовательские запросы для просеки необработанных данных, собранных в нескольких продуктах защиты.</span><span class="sxs-lookup"><span data-stu-id="1733d-112">**[Cross-product threat hunting](api-advanced-hunting.md)** - Leverage your security team's organizational knowledge to hunt for signs of compromise, by creating your own custom queries to sift over raw data collected across multiple protection products.</span></span>

<span data-ttu-id="1733d-113">Наряду с этими API, определенными для Microsoft 365 Defender, каждый из наших других продуктов безопасности предоставляет дополнительные [API,](api-articles.md) которые помогут вам воспользоваться их уникальными возможностями.</span><span class="sxs-lookup"><span data-stu-id="1733d-113">Along with these Microsoft 365 Defender-specific APIs, each of our other security products expose [additional APIs](api-articles.md) to help you take advantage of their unique capabilities.</span></span>


> [!NOTE]
> <span data-ttu-id="1733d-114">Переход на единый портал не должен влиять на панели мониторинга PowerBi на основе API Microsoft Defender для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="1733d-114">The transition to the unified portal should not affect the PowerBi dashboards based on Microsoft Defender for Endpoint APIs.</span></span> <span data-ttu-id="1733d-115">Вы можете продолжать работать с существующими API независимо от интерактивного перехода портала.</span><span class="sxs-lookup"><span data-stu-id="1733d-115">You can continue to work with the existing APIs regardless of the interactive portal transition.</span></span>


## <a name="learn-more"></a><span data-ttu-id="1733d-116">Подробнее</span><span class="sxs-lookup"><span data-stu-id="1733d-116">Learn more</span></span>

| <span data-ttu-id="1733d-117">**Понимание доступа к API**</span><span class="sxs-lookup"><span data-stu-id="1733d-117">**Understand how to access the APIs**</span></span> |
|-|
| [<span data-ttu-id="1733d-118">Узнайте о квотах API и лицензировании</span><span class="sxs-lookup"><span data-stu-id="1733d-118">Learn about API quotas and licensing</span></span>](api-terms.md) |
| [<span data-ttu-id="1733d-119">Доступ к API защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1733d-119">Access the Microsoft 365 Defender APIs</span></span>](api-access.md) |
| <span data-ttu-id="1733d-120">**Создание приложений**</span><span class="sxs-lookup"><span data-stu-id="1733d-120">**Build apps**</span></span> |
| [<span data-ttu-id="1733d-121">Создание приложения "Hello world"</span><span class="sxs-lookup"><span data-stu-id="1733d-121">Create a 'Hello world' app</span></span>](api-hello-world.md) |
| [<span data-ttu-id="1733d-122">Создание приложения для доступа к API Защитника Microsoft 365 от имени пользователя</span><span class="sxs-lookup"><span data-stu-id="1733d-122">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md) |
| [<span data-ttu-id="1733d-123">Создание приложения для доступа к Microsoft 365 Defender без пользователя</span><span class="sxs-lookup"><span data-stu-id="1733d-123">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md) |
| [<span data-ttu-id="1733d-124">Создание приложения с несколькими партнерами-партнерами для API Защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1733d-124">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md) |
| <span data-ttu-id="1733d-125">**Устранение неполадок и обслуживание приложений**</span><span class="sxs-lookup"><span data-stu-id="1733d-125">**Troubleshoot and maintain your apps**</span></span> |
| [<span data-ttu-id="1733d-126">Понимание кодов ошибок API</span><span class="sxs-lookup"><span data-stu-id="1733d-126">Understand API error codes</span></span>](api-error-codes.md) |
| [<span data-ttu-id="1733d-127">Управление секретами в приложениях с помощью хранилища ключей Azure</span><span class="sxs-lookup"><span data-stu-id="1733d-127">Manage secrets in your apps with Azure Key Vault</span></span>](/learn/modules/manage-secrets-with-azure-key-vault/) |
| [<span data-ttu-id="1733d-128">Реализация авторизации OAuth 2.0 для входных данных пользователя</span><span class="sxs-lookup"><span data-stu-id="1733d-128">Implement OAuth 2.0 authorization for user sign in</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |