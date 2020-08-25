---
title: Мониторинг приложений & отчеты — центр обеспечения безопасности
description: Узнайте, как получить более подробные сведения об использовании облачных приложений в Организации. Включает различные виды приложений, их уровень риска и оповещения.
keywords: безопасность, вредоносные программы, Microsoft 365, M365, центр безопасности, монитор, отчет, приложения
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f370a537b9355a99b90f21faab5eda75d7f84cdf
ms.sourcegitcommit: 787b198765565d54ee73972f664bdbd5023d666b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/24/2020
ms.locfileid: "46866853"
---
# <a name="app-monitoring-and-reporting-in-the-microsoft-365-security-center"></a><span data-ttu-id="76e16-105">Мониторинг приложений и создание отчетов в центре безопасности Майкрософт 365</span><span class="sxs-lookup"><span data-stu-id="76e16-105">App monitoring and reporting in the Microsoft 365 security center</span></span>

<span data-ttu-id="76e16-106">Эти отчеты предоставляют более подробные сведения об использовании облачных приложений в Организации.</span><span class="sxs-lookup"><span data-stu-id="76e16-106">These reports provide more insight into how cloud apps are being used in your organization.</span></span> <span data-ttu-id="76e16-107">Включает различные виды приложений, их уровень риска и оповещения.</span><span class="sxs-lookup"><span data-stu-id="76e16-107">Includes different kinds of apps, their level of risk, and alerts.</span></span>

## <a name="monitor-email-accounts-at-risk"></a><span data-ttu-id="76e16-108">отслеживание учетных записей электронной почты, подверженных риску;</span><span class="sxs-lookup"><span data-stu-id="76e16-108">Monitor email accounts at risk</span></span>

<span data-ttu-id="76e16-109">**Защита электронной почты** показывает, что учетные записи электронной почты подвержены риску.</span><span class="sxs-lookup"><span data-stu-id="76e16-109">**Email protection** shows email accounts at risk.</span></span> <span data-ttu-id="76e16-110">Вы можете выбрать учетную запись для дальнейшего изучения в центре безопасности защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="76e16-110">You can select an account to investigate further in Microsoft Defender Security Center.</span></span>

![Карта защиты электронной почты](../../media/email-protection.png)

## <a name="monitor-app-permissions-granted-by-users"></a><span data-ttu-id="76e16-112">Отслеживание разрешений на доступ к приложениям, предоставленных пользователями</span><span class="sxs-lookup"><span data-stu-id="76e16-112">Monitor app permissions granted by users</span></span>

<span data-ttu-id="76e16-113">**Cloud App Security — приложения OAuth** список приложений, обнаруженных в Cloud App Security, которым были предоставлены разрешения пользователей.</span><span class="sxs-lookup"><span data-stu-id="76e16-113">**Cloud App Security - OAuth apps** lists apps discovered by Cloud App Security that have been granted permissions by users.</span></span> <span data-ttu-id="76e16-114">В каталоге риска Cloud App Security входит свыше 16 000 приложений, которые оцениваются с помощью более 70 факторов риска.</span><span class="sxs-lookup"><span data-stu-id="76e16-114">Cloud App Security's risk catalog includes over 16,000 apps that are assessed using over 70 risk factors.</span></span>

<span data-ttu-id="76e16-115">Факторы риска начинаются с общей информации, например издателя приложения.</span><span class="sxs-lookup"><span data-stu-id="76e16-115">The risk factors start from general information, such as the app publisher.</span></span> <span data-ttu-id="76e16-116">Затем он перемещается в меры безопасности и элементы управления, например, поддерживает ли приложение шифрование на REST или предоставляет журнал аудита действий пользователя.</span><span class="sxs-lookup"><span data-stu-id="76e16-116">It then moves to security measures and controls, such as whether the app supports encryption at rest or provides an audit log of user activity.</span></span>

![Карточка приложений OAuth Cloud App Security](../../media/cloud-app-security-oauth-apps.png)

## <a name="monitor-cloud-app-user-accounts"></a><span data-ttu-id="76e16-118">Отслеживание учетных записей пользователей облачного приложения</span><span class="sxs-lookup"><span data-stu-id="76e16-118">Monitor cloud app user accounts</span></span>

<span data-ttu-id="76e16-119">**Учетные записи облачных приложений для** учетных записей списков проверки, которые могут потребовать внимания.</span><span class="sxs-lookup"><span data-stu-id="76e16-119">**Cloud app accounts for review** lists accounts that may require attention.</span></span>

![Карточка облачных учетных записей приложений для пересмотра](../../media/cloud-app-accounts-for-review.png)

## <a name="understand-which-cloud-apps-are-used"></a><span data-ttu-id="76e16-121">Сведения о том, какие облачные приложения используются</span><span class="sxs-lookup"><span data-stu-id="76e16-121">Understand which cloud apps are used</span></span>

<span data-ttu-id="76e16-122">**Обнаруженные облачные приложения (категории)** показывают, какие типы приложений используются в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="76e16-122">**Discovered cloud apps (categories)** show what kinds of apps are being used in your organization.</span></span> <span data-ttu-id="76e16-123">Он содержит ссылку на панель мониторинга облачного обнаружения в Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="76e16-123">It links to the Cloud Discovery dashboard in Cloud App Security.</span></span> <span data-ttu-id="76e16-124">Более подробную информацию можно найти [в разделе Краткое руководство: Working with обнаруженным приложениям](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span><span class="sxs-lookup"><span data-stu-id="76e16-124">For more information, see [Quickstart: Work with discovered apps](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span></span>  

![Карточка с обнаруженными категориями облачных приложений](../../media/discovered-cloud-apps-categories.png)

## <a name="monitor-where-users-access-cloud-apps"></a><span data-ttu-id="76e16-126">Отслеживание пользователей, обращающихся к облачным приложениям</span><span class="sxs-lookup"><span data-stu-id="76e16-126">Monitor where users access cloud apps</span></span>

<span data-ttu-id="76e16-127">**Расположения облачных действий приложения** показывают, где у пользователей есть доступ к облачным приложениям.</span><span class="sxs-lookup"><span data-stu-id="76e16-127">**Cloud app activity locations** show where users are accessing cloud apps.</span></span>

![Карточка "расположение действий облачного приложения"](../../media/cloud-app-activity-locations.png)

## <a name="monitor-health-for-infrastructure-workloads"></a><span data-ttu-id="76e16-129">Отслеживание работоспособности для рабочих нагрузок инфраструктуры</span><span class="sxs-lookup"><span data-stu-id="76e16-129">Monitor health for infrastructure workloads</span></span>

<span data-ttu-id="76e16-130">В центре безопасности Azure для рабочих нагрузок инфраструктуры отображаются оповещения о работоспособности **инфраструктуры** .</span><span class="sxs-lookup"><span data-stu-id="76e16-130">**Infrastructure health** shows health status alerts for infrastructure workloads in Azure Security Center.</span></span>

<span data-ttu-id="76e16-131">Центр безопасности Azure обеспечивает единую систему управления безопасностью и Advanced Threat Protection в локальной и облачной рабочих нагрузках.</span><span class="sxs-lookup"><span data-stu-id="76e16-131">Azure Security Center provides unified security management and advanced threat protection across on-premises and cloud workloads.</span></span> <span data-ttu-id="76e16-132">Вы можете собирать, искать и анализировать данные безопасности из различных источников, в том числе брандмауэров и других партнерских решений.</span><span class="sxs-lookup"><span data-stu-id="76e16-132">You can collect, search, and analyze security data from different sources, including firewalls and other partner solutions.</span></span>

<span data-ttu-id="76e16-133">Для получения дополнительных сведений обратитесь [к документации центра безопасности Azure](https://docs.microsoft.com/azure/security-center/).</span><span class="sxs-lookup"><span data-stu-id="76e16-133">For more information, see [Azure Security Center Documentation](https://docs.microsoft.com/azure/security-center/).</span></span>

![Карта работоспособности инфраструктуры](../../media/infrastructure-health.png)
