---
title: Обзор Microsoft 365 Defender API
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
ms.openlocfilehash: 2ca601c3c68df9f9f1cc4fb90bcfbe907850ce91
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029733"
---
# <a name="overview-of-microsoft-365-defender-apis"></a><span data-ttu-id="127cc-104">Обзор Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="127cc-104">Overview of Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="127cc-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="127cc-105">**Applies to:**</span></span>

- <span data-ttu-id="127cc-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="127cc-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="127cc-107">Некоторые сведения относятся к предварительным выпускам продуктов, которые могут быть существенно изменены до коммерческого выпуска.</span><span class="sxs-lookup"><span data-stu-id="127cc-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="127cc-108">Корпорация Майкрософт не дает никаких гарантий, явных или подразумеваемых, относительно предоставленных здесь сведений.</span><span class="sxs-lookup"><span data-stu-id="127cc-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="127cc-109">Microsoft 365 Defender построена на платформе, готовой к интеграции.</span><span class="sxs-lookup"><span data-stu-id="127cc-109">Microsoft 365 Defender is built on top of an integration-ready platform.</span></span>

<span data-ttu-id="127cc-110">Используйте Microsoft 365 Defender API для автоматизации рабочего процесса на основе общих таблиц инцидента и расширенных таблиц охоты.</span><span class="sxs-lookup"><span data-stu-id="127cc-110">Use the Microsoft 365 Defender APIs to automate workflows based on the shared incident and advanced hunting tables.</span></span>

- <span data-ttu-id="127cc-111">**[Совмещенная очередь](api-incident.md)** инцидентов . Фокус на том, что имеет решающее значение, сгруппив всю область атаки и все влияющие активы вместе в API инцидента.</span><span class="sxs-lookup"><span data-stu-id="127cc-111">**[Combined incidents queue](api-incident.md)** - Focus on what's critical by grouping the full attack scope and all impacted assets together under the incident API.</span></span>

- <span data-ttu-id="127cc-112">**[Межпродукционная](api-advanced-hunting.md)** охота на угрозы — использование организационных знаний группы безопасности для охоты за признаками компромисса, создав собственные пользовательские запросы для просеки необработанных данных, собранных в нескольких продуктах защиты.</span><span class="sxs-lookup"><span data-stu-id="127cc-112">**[Cross-product threat hunting](api-advanced-hunting.md)** - Leverage your security team's organizational knowledge to hunt for signs of compromise, by creating your own custom queries to sift over raw data collected across multiple protection products.</span></span>

<span data-ttu-id="127cc-113">Используйте [API потоковой](../defender-endpoint/raw-data-export.md) передачи для отгрузки событий и оповещений в режиме реального времени из экземпляров по мере их возникновения в одном потоке данных.</span><span class="sxs-lookup"><span data-stu-id="127cc-113">Use the [Streaming API](../defender-endpoint/raw-data-export.md) to ship real-time events and alerts from instances as they occur within a single data stream.</span></span>

<span data-ttu-id="127cc-114">Наряду с Microsoft 365 Defender API каждый из наших других продуктов безопасности предоставляет дополнительные [API,](api-articles.md) которые помогут вам воспользоваться их уникальными возможностями.</span><span class="sxs-lookup"><span data-stu-id="127cc-114">Along with these Microsoft 365 Defender-specific APIs, each of our other security products expose [additional APIs](api-articles.md) to help you take advantage of their unique capabilities.</span></span>

> [!NOTE]
> <span data-ttu-id="127cc-115">Переход на единый портал не должен влиять на панели мониторинга PowerBi на основе API Microsoft Defender для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="127cc-115">The transition to the unified portal should not affect the PowerBi dashboards based on Microsoft Defender for Endpoint APIs.</span></span> <span data-ttu-id="127cc-116">Вы можете продолжать работать с существующими API независимо от интерактивного перехода портала.</span><span class="sxs-lookup"><span data-stu-id="127cc-116">You can continue to work with the existing APIs regardless of the interactive portal transition.</span></span>

## <a name="learn-more"></a><span data-ttu-id="127cc-117">Подробнее</span><span class="sxs-lookup"><span data-stu-id="127cc-117">Learn more</span></span>

| <span data-ttu-id="127cc-118">**Понимание доступа к API**</span><span class="sxs-lookup"><span data-stu-id="127cc-118">**Understand how to access the APIs**</span></span> |
|-|
| [<span data-ttu-id="127cc-119">Узнайте о квотах API и лицензировании</span><span class="sxs-lookup"><span data-stu-id="127cc-119">Learn about API quotas and licensing</span></span>](api-terms.md) |
| [<span data-ttu-id="127cc-120">Доступ к Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="127cc-120">Access the Microsoft 365 Defender APIs</span></span>](api-access.md) |
| <span data-ttu-id="127cc-121">**Создание приложений**</span><span class="sxs-lookup"><span data-stu-id="127cc-121">**Build apps**</span></span> |
| [<span data-ttu-id="127cc-122">Создание приложения "Hello world"</span><span class="sxs-lookup"><span data-stu-id="127cc-122">Create a 'Hello world' app</span></span>](api-hello-world.md) |
| [<span data-ttu-id="127cc-123">Создание приложения для доступа Microsoft 365 Defender API от имени пользователя</span><span class="sxs-lookup"><span data-stu-id="127cc-123">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md) |
| [<span data-ttu-id="127cc-124">Создание приложения для доступа Microsoft 365 Defender без пользователя</span><span class="sxs-lookup"><span data-stu-id="127cc-124">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md) |
| [<span data-ttu-id="127cc-125">Создание приложения с несколькими партнерами-партнерами для доступа Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="127cc-125">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md) |
| <span data-ttu-id="127cc-126">**Устранение неполадок и обслуживание приложений**</span><span class="sxs-lookup"><span data-stu-id="127cc-126">**Troubleshoot and maintain your apps**</span></span> |
| [<span data-ttu-id="127cc-127">Понимание кодов ошибок API</span><span class="sxs-lookup"><span data-stu-id="127cc-127">Understand API error codes</span></span>](api-error-codes.md) |
| [<span data-ttu-id="127cc-128">Управление секретами в приложениях с помощью хранилища ключей Azure</span><span class="sxs-lookup"><span data-stu-id="127cc-128">Manage secrets in your apps with Azure Key Vault</span></span>](/learn/modules/manage-secrets-with-azure-key-vault/) |
| [<span data-ttu-id="127cc-129">Реализация авторизации OAuth 2.0 для входных данных пользователя</span><span class="sxs-lookup"><span data-stu-id="127cc-129">Implement OAuth 2.0 authorization for user sign in</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |