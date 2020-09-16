---
title: Microsoft 365 Multi-Geo
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.custom: seo-marvel-apr2020
ms.collection: Strat_SP_gtc
localization_priority: Normal
f1.keywords:
- NOCSH
description: В этой статье рассказывается о том, как расширить сведения о присутствии Microsoft 365 в несколько географических регионов с помощью Microsoft 365 с поддержкой нескольких регионов.
ms.openlocfilehash: 41069490a8c824bb58a8f4247987abd3ce0901b6
ms.sourcegitcommit: 62a8c226422eac9c085cc886b4836b037f95ef6d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2020
ms.locfileid: "47825363"
---
# <a name="microsoft-365-multi-geo"></a><span data-ttu-id="17e16-103">Microsoft 365 Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="17e16-103">Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="17e16-104">С помощью Microsoft 365 Multi-Geo организация может расширить присутствие Microsoft 365 до нескольких географических регионов или стран в существующем клиенте.</span><span class="sxs-lookup"><span data-stu-id="17e16-104">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span> <span data-ttu-id="17e16-105">Обратитесь в службу поддержки учетных записей Майкрософт, чтобы зарегистрировать транснациональную компанию в Microsoft 365 Multi-Geo.</span><span class="sxs-lookup"><span data-stu-id="17e16-105">Reach out to your Microsoft Account Team to sign up your Multi-National Company for Microsoft 365 Multi-Geo.</span></span>
  
<span data-ttu-id="17e16-106">Использование Microsoft 365 Multi-Geo позволяет подготавливать и хранить неактивные данные в выбранных вами географических расположениях в соответствии с требованиями к месту расположения данных, а также предоставлять современные возможности для работы всем сотрудникам.</span><span class="sxs-lookup"><span data-stu-id="17e16-106">With Microsoft 365 Multi-Geo, you can provision and store data at rest in the geo locations that you've chosen to meet data residency requirements, and at the same time unlock your global roll out of modern productivity experiences to your workforce.</span></span>

<span data-ttu-id="17e16-107">Видеовведение в Microsoft 365 с поддержкой нескольких регионов можно узнать в статье [SharePoint Online и OneDrive с поддержкой нескольких регионов, чтобы контролировать, где находятся данные](https://www.youtube.com/watch?v=Do9U3JuROhk).</span><span class="sxs-lookup"><span data-stu-id="17e16-107">For a video introduction to Microsoft 365 Multi-Geo, see [SharePoint Online and OneDrive Multi-Geo to control where your data resides](https://www.youtube.com/watch?v=Do9U3JuROhk).</span></span>

## <a name="multi-geo-architecture"></a><span data-ttu-id="17e16-108">Архитектура с поддержкой нескольких регионов</span><span class="sxs-lookup"><span data-stu-id="17e16-108">Multi-Geo architecture</span></span>

<span data-ttu-id="17e16-109">В среде с поддержкой нескольких регионов клиент Microsoft 365 включает центральное расположение (где изначально подготавливается подписка на Microsoft 365) и одно или несколько вспомогательных расположений.</span><span class="sxs-lookup"><span data-stu-id="17e16-109">In a Multi-Geo environment, your Microsoft 365 tenant consists of a central location (where your Microsoft 365 subscription was originally provisioned) and one or more satellite locations.</span></span> <span data-ttu-id="17e16-110">В клиенте с поддержкой нескольких регионов управление сведениями о географических расположениях, группах и пользователях выполняется в Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="17e16-110">In a multi-geo tenant, the information about geo locations, groups, and user information, is mastered in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="17e16-111">Так как информация клиента обрабатывается централизованно и синхронизируется с каждым регионом, общий доступ и возможности в компании носят глобальный характер.</span><span class="sxs-lookup"><span data-stu-id="17e16-111">Because your tenant information is mastered centrally and synchronized into each geo location, sharing and experiences involving anyone from your company contain global awareness.</span></span>

![Снимок экрана: карта нескольких регионов в Центре администрирования SharePoint](../media/multi-geo-world-map.png)

<span data-ttu-id="17e16-113">Обратите внимание, что Microsoft 365 Multi-Geo не предназначен для повышения производительности. Он предназначен для соблюдения требований к месту расположения данных.</span><span class="sxs-lookup"><span data-stu-id="17e16-113">Note that Microsoft 365 Multi-Geo is not designed for performance optimization, it is designed to meet data residency requirements.</span></span> <span data-ttu-id="17e16-114">Сведения о повышении производительности для Microsoft 365 см. в статье [Планирование сети и настройка производительности для Microsoft 365](https://support.office.com/article/e5f1228c-da3c-4654-bf16-d163daee8848). Вы также можете связаться с группой поддержки.</span><span class="sxs-lookup"><span data-stu-id="17e16-114">For information about performance optimization for Microsoft 365, see [Network planning and performance tuning for Microsoft 365](https://support.office.com/article/e5f1228c-da3c-4654-bf16-d163daee8848) or contact your support group.</span></span>

## <a name="terminology"></a><span data-ttu-id="17e16-115">Терминология</span><span class="sxs-lookup"><span data-stu-id="17e16-115">Terminology</span></span>

<span data-ttu-id="17e16-116">Ниже приводятся основные термины, используемые при описании Microsoft 365 Multi-Geo:</span><span class="sxs-lookup"><span data-stu-id="17e16-116">Here are the key terms used in describing Microsoft 365 Multi-Geo:</span></span>

- <span data-ttu-id="17e16-117">**Центральное расположение** — географическое расположение, в котором изначально подготовлен клиент.</span><span class="sxs-lookup"><span data-stu-id="17e16-117">**Central location** - the geo location where your tenant was originally provisioned.</span></span>
- <span data-ttu-id="17e16-118">**Администратор геообъекта** — администратор, который может управлять одним или несколькими периферийными расположениями.</span><span class="sxs-lookup"><span data-stu-id="17e16-118">**Geo administrator** - An administrator who can administer one or more specified satellite locations.</span></span>
- <span data-ttu-id="17e16-119">**Код региона** — код из трех букв для определенного географического расположения.</span><span class="sxs-lookup"><span data-stu-id="17e16-119">**Geo code** - a three-letter code for a given geo location.</span></span>
- <span data-ttu-id="17e16-120">**Географическое расположение** — регион, который можно использовать в клиенте с поддержкой нескольких регионов для размещения данных, включая почтовые ящики Exchange, а также сайты OneDrive и SharePoint.</span><span class="sxs-lookup"><span data-stu-id="17e16-120">**Geo location** – A geographic location that can be used in a multi-geo tenant to host data, including Exchange mailboxes and OneDrive and SharePoint sites.</span></span>
- <span data-ttu-id="17e16-121">**Предпочтительное расположение данных (PDL)** — свойство пользователя, устанавливаемое администратором, которое указывает географическое расположение, где следует подготовить почтовый ящик Exchange и хранилище OneDrive пользователей.</span><span class="sxs-lookup"><span data-stu-id="17e16-121">**Preferred Data Location (PDL)** – A user property set by the administrator that indicates where the geo location where the users Exchange mailbox and OneDrive should be provisioned.</span></span> <span data-ttu-id="17e16-122">PDL также определяет, где подготовлены сайты SharePoint, созданные пользователем.</span><span class="sxs-lookup"><span data-stu-id="17e16-122">The PDL also determines where SharePoint sites that are created by the user are provisioned.</span></span>
- <span data-ttu-id="17e16-123">**Вспомогательное расположение** — географическое расположение, где учитывающие регион рабочие нагрузки Microsoft 365 (SharePoint, OneDrive и Exchange) включены в клиенте с поддержкой нескольких регионов.</span><span class="sxs-lookup"><span data-stu-id="17e16-123">**Satellite location** – The geo locations where the geo-aware Microsoft 365 workloads (SharePoint, OneDrive, and Exchange) are enabled in a multi-geo tenant.</span></span>
- <span data-ttu-id="17e16-124">**Клиент** — представление организации в Microsoft 365, которое имеет, как правило, один или несколько связанных с ним доменов (например, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="17e16-124">**Tenant** – An organization's representation in Microsoft 365 which typically has one or more domains associated with it (for example, contoso.com).</span></span>

## <a name="licensing"></a><span data-ttu-id="17e16-125">Лицензирование</span><span class="sxs-lookup"><span data-stu-id="17e16-125">Licensing</span></span>

<span data-ttu-id="17e16-126">Microsoft 365 с поддержкой нескольких регионов доступен как надстройка для планов подписки Microsoft 365 для клиентов EA с не менее чем 250 рабочих мест Microsoft 365 в клиенте и не менее чем 5% из этих рабочих мест, для которых используется поддержка нескольких регионов.</span><span class="sxs-lookup"><span data-stu-id="17e16-126">Microsoft 365 Multi-Geo is available as an add-on to the following Microsoft 365 subscription plans for EA customers with a minimum of 250 Microsoft 365 seats in their tenant, and a minimum of 5% of those seats using multi-geo.</span></span> <span data-ttu-id="17e16-127">За дополнительной информацией обращайтесь к команде, в которую входит ваша учетная запись.</span><span class="sxs-lookup"><span data-stu-id="17e16-127">Please contact your Microsoft account team for details.</span></span>

- <span data-ttu-id="17e16-128">Microsoft 365 F1, E1, E3 или E5</span><span class="sxs-lookup"><span data-stu-id="17e16-128">Microsoft 365 F1, E1, E3, or E5</span></span>
- <span data-ttu-id="17e16-129">Exchange Online (план 1 или план 2)</span><span class="sxs-lookup"><span data-stu-id="17e16-129">Exchange Online Plan 1 or Plan 2</span></span>
- <span data-ttu-id="17e16-130">OneDrive для бизнеса (план 1 или план 2)</span><span class="sxs-lookup"><span data-stu-id="17e16-130">OneDrive for Business Plan 1 or Plan 2</span></span>
- <span data-ttu-id="17e16-131">SharePoint Online (план 1 или план 2)</span><span class="sxs-lookup"><span data-stu-id="17e16-131">SharePoint Online Plan 1 or Plan 2</span></span>

## <a name="microsoft-365-multi-geo-availability"></a><span data-ttu-id="17e16-132">Доступность Microsoft 365 Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="17e16-132">Microsoft 365 Multi-Geo availability</span></span>

<span data-ttu-id="17e16-133">В настоящее время Microsoft 365 Multi-Geo доступен в таких странах и регионах:</span><span class="sxs-lookup"><span data-stu-id="17e16-133">Microsoft 365 Multi-Geo is currently offered in these regions and countries:</span></span>

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

## <a name="getting-started"></a><span data-ttu-id="17e16-134">Начало работы</span><span class="sxs-lookup"><span data-stu-id="17e16-134">Getting started</span></span>

<span data-ttu-id="17e16-135">Чтобы приступить к работе с несколькими регионами, следуйте указанным ниже инструкциям.</span><span class="sxs-lookup"><span data-stu-id="17e16-135">Follow these steps to get started with multi-geo:</span></span>

1. <span data-ttu-id="17e16-136">Совместно с группой специалистов, занимающихся учетными записями, добавьте план обслуживания _с поддержкой нескольких регионов в Microsoft 365_.</span><span class="sxs-lookup"><span data-stu-id="17e16-136">Work with your account team to add the _Multi-Geo Capabilities in Microsoft 365_ service plan.</span></span> <span data-ttu-id="17e16-137">Они помогут вам добавить необходимое количество лицензий.</span><span class="sxs-lookup"><span data-stu-id="17e16-137">They will guide you to add the number of licenses needed.</span></span> <span data-ttu-id="17e16-138">Функция поддержки нескольких регионов доступна клиентам EA с не менее 250 подписками на Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="17e16-138">Multi-Geo feature is available to EA customers with a minimum of 250 Microsoft 365 subscriptions.</span></span>

   <span data-ttu-id="17e16-139">Прежде чем вы сможете начать работу в Microsoft 365 Multi-Geo, корпорации Майкрософт потребуется настроить ваш клиент Exchange Online для поддержки нескольких регионов.</span><span class="sxs-lookup"><span data-stu-id="17e16-139">Before you can start using Microsoft 365 Multi-Geo, Microsoft needs to configure your Exchange Online tenant for multi-geo support.</span></span> <span data-ttu-id="17e16-140">Этот разовый процесс настройки запускается после заказа плана обслуживания с *поддержкой нескольких регионов в Microsoft 365* и появления лицензий в вашем клиенте.</span><span class="sxs-lookup"><span data-stu-id="17e16-140">This one-time configuration process is triggered after you order the *Multi-Geo Capabilities in Microsoft 365* service plan and the licenses show up in your tenant.</span></span> <span data-ttu-id="17e16-141">Вы получите уведомления в [Центре сообщений Microsoft 365](https://support.office.com/article/38FB3333-BFCC-4340-A37B-DEDA509C2093) после присвоения лицензий с поддержкой нескольких регионов и затем сможете начать настройку и использование возможностей Microsoft 365 Multi-Geo.</span><span class="sxs-lookup"><span data-stu-id="17e16-141">You'll receive notifications in the [Microsoft 365 message center](https://support.office.com/article/38FB3333-BFCC-4340-A37B-DEDA509C2093) once your Multi-Geo licenses are applied and you then may begin configuring and using your Microsoft 365 Multi-Geo capabilities.</span></span>

2. <span data-ttu-id="17e16-142">См. статью [Планирование среды с поддержкой нескольких регионов](plan-for-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="17e16-142">Read [Plan your multi-geo environment](plan-for-multi-geo.md).</span></span>

3. <span data-ttu-id="17e16-143">Узнайте об [администрировании среды с поддержкой нескольких регионов](administering-a-multi-geo-environment.md) и о том, [как пользователи взаимодействуют со средой](multi-geo-user-experience.md).</span><span class="sxs-lookup"><span data-stu-id="17e16-143">Learn about [administering a multi-geo environment](administering-a-multi-geo-environment.md) and [how your users will experience the environment](multi-geo-user-experience.md).</span></span>

4. <span data-ttu-id="17e16-144">Когда вы будете готовы настроить Microsoft 365 Multi-Geo, [настройте свой клиент для поддержки нескольких регионов](multi-geo-tenant-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="17e16-144">When you are ready to set up Microsoft 365 Multi-Geo, [configure your tenant for multi-geo](multi-geo-tenant-configuration.md).</span></span>

5. <span data-ttu-id="17e16-145">[Настройка поиска](configure-search-for-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="17e16-145">[Set up search](configure-search-for-multi-geo.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="17e16-146">См. также</span><span class="sxs-lookup"><span data-stu-id="17e16-146">See also</span></span>

[<span data-ttu-id="17e16-147">Поддержка нескольких регионов в Exchange Online и OneDrive</span><span class="sxs-lookup"><span data-stu-id="17e16-147">Multi-Geo in Exchange Online and OneDrive</span></span>](https://Aka.ms/GoMultiGeo)

[<span data-ttu-id="17e16-148">Поддержка нескольких регионов в OneDrive и SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="17e16-148">Multi-Geo Capabilities in OneDrive and SharePoint Online</span></span>](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)

[<span data-ttu-id="17e16-149">Поддержка нескольких регионов в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="17e16-149">Multi-Geo Capabilities in Exchange Online</span></span>](multi-geo-capabilities-in-exchange-online.md)

[<span data-ttu-id="17e16-150">Взаимодействие групп в нескольких географических средах</span><span class="sxs-lookup"><span data-stu-id="17e16-150">Teams experience in a multi-geo environment</span></span>](https://docs.microsoft.com/microsoftteams/teams-experience-o365odb-spo-multi-geo)
