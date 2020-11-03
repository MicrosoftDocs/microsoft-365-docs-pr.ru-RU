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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dcb7997c8c248c2b4e7d16902b6ebdd7756ccd0b
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846632"
---
# <a name="app-monitoring-and-reporting-in-the-microsoft-365-security-center"></a><span data-ttu-id="846c7-105">Мониторинг приложений и создание отчетов в центре безопасности Майкрософт 365</span><span class="sxs-lookup"><span data-stu-id="846c7-105">App monitoring and reporting in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="846c7-106">Эти отчеты предоставляют более подробные сведения об использовании облачных приложений в Организации.</span><span class="sxs-lookup"><span data-stu-id="846c7-106">These reports provide more insight into how cloud apps are being used in your organization.</span></span> <span data-ttu-id="846c7-107">Включает различные виды приложений, их уровень риска и оповещения.</span><span class="sxs-lookup"><span data-stu-id="846c7-107">Includes different kinds of apps, their level of risk, and alerts.</span></span>

## <a name="monitor-email-accounts-at-risk"></a><span data-ttu-id="846c7-108">отслеживание учетных записей электронной почты, подверженных риску;</span><span class="sxs-lookup"><span data-stu-id="846c7-108">Monitor email accounts at risk</span></span>

<span data-ttu-id="846c7-109">**Защита электронной почты** показывает, что учетные записи электронной почты подвержены риску.</span><span class="sxs-lookup"><span data-stu-id="846c7-109">**Email protection** shows email accounts at risk.</span></span> <span data-ttu-id="846c7-110">Вы можете выбрать учетную запись для дальнейшего изучения в центре безопасности защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="846c7-110">You can select an account to investigate further in Microsoft Defender Security Center.</span></span>

![Карта защиты электронной почты](../../media/email-protection.png)

## <a name="monitor-app-permissions-granted-by-users"></a><span data-ttu-id="846c7-112">Отслеживание разрешений на доступ к приложениям, предоставленных пользователями</span><span class="sxs-lookup"><span data-stu-id="846c7-112">Monitor app permissions granted by users</span></span>

<span data-ttu-id="846c7-113">**Cloud App Security — приложения OAuth** список приложений, обнаруженных в Cloud App Security, которым были предоставлены разрешения пользователей.</span><span class="sxs-lookup"><span data-stu-id="846c7-113">**Cloud App Security - OAuth apps** lists apps discovered by Cloud App Security that have been granted permissions by users.</span></span> <span data-ttu-id="846c7-114">В каталоге риска Cloud App Security входит свыше 16 000 приложений, которые оцениваются с помощью более 70 факторов риска.</span><span class="sxs-lookup"><span data-stu-id="846c7-114">Cloud App Security's risk catalog includes over 16,000 apps that are assessed using over 70 risk factors.</span></span>

<span data-ttu-id="846c7-115">Факторы риска начинаются с общей информации, например издателя приложения.</span><span class="sxs-lookup"><span data-stu-id="846c7-115">The risk factors start from general information, such as the app publisher.</span></span> <span data-ttu-id="846c7-116">Затем он перемещается в меры безопасности и элементы управления, например, поддерживает ли приложение шифрование на REST или предоставляет журнал аудита действий пользователя.</span><span class="sxs-lookup"><span data-stu-id="846c7-116">It then moves to security measures and controls, such as whether the app supports encryption at rest or provides an audit log of user activity.</span></span>

![Карточка приложений OAuth Cloud App Security](../../media/cloud-app-security-oauth-apps.png)

## <a name="monitor-cloud-app-user-accounts"></a><span data-ttu-id="846c7-118">Отслеживание учетных записей пользователей облачного приложения</span><span class="sxs-lookup"><span data-stu-id="846c7-118">Monitor cloud app user accounts</span></span>

<span data-ttu-id="846c7-119">**Учетные записи облачных приложений для** учетных записей списков проверки, которые могут потребовать внимания.</span><span class="sxs-lookup"><span data-stu-id="846c7-119">**Cloud app accounts for review** lists accounts that may require attention.</span></span>

![Карточка облачных учетных записей приложений для пересмотра](../../media/cloud-app-accounts-for-review.png)

## <a name="understand-which-cloud-apps-are-used"></a><span data-ttu-id="846c7-121">Сведения о том, какие облачные приложения используются</span><span class="sxs-lookup"><span data-stu-id="846c7-121">Understand which cloud apps are used</span></span>

<span data-ttu-id="846c7-122">**Обнаруженные облачные приложения (категории)** показывают, какие типы приложений используются в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="846c7-122">**Discovered cloud apps (categories)** show what kinds of apps are being used in your organization.</span></span> <span data-ttu-id="846c7-123">Он содержит ссылку на панель мониторинга облачного обнаружения в Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="846c7-123">It links to the Cloud Discovery dashboard in Cloud App Security.</span></span> <span data-ttu-id="846c7-124">Более подробную информацию можно найти [в разделе Краткое руководство: Working with обнаруженным приложениям](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span><span class="sxs-lookup"><span data-stu-id="846c7-124">For more information, see [Quickstart: Work with discovered apps](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span></span>  

![Карточка с обнаруженными категориями облачных приложений](../../media/discovered-cloud-apps-categories.png)

## <a name="monitor-where-users-access-cloud-apps"></a><span data-ttu-id="846c7-126">Отслеживание пользователей, обращающихся к облачным приложениям</span><span class="sxs-lookup"><span data-stu-id="846c7-126">Monitor where users access cloud apps</span></span>

<span data-ttu-id="846c7-127">**Расположения облачных действий приложения** показывают, где у пользователей есть доступ к облачным приложениям.</span><span class="sxs-lookup"><span data-stu-id="846c7-127">**Cloud app activity locations** show where users are accessing cloud apps.</span></span>

![Карточка "расположение действий облачного приложения"](../../media/cloud-app-activity-locations.png)

## <a name="monitor-health-for-infrastructure-workloads"></a><span data-ttu-id="846c7-129">Отслеживание работоспособности для рабочих нагрузок инфраструктуры</span><span class="sxs-lookup"><span data-stu-id="846c7-129">Monitor health for infrastructure workloads</span></span>

<span data-ttu-id="846c7-130">В **работоспособности инфраструктуры** отображаются оповещения о состоянии работоспособности для рабочих нагрузок инфраструктуры в защитнике Azure \*.</span><span class="sxs-lookup"><span data-stu-id="846c7-130">**Infrastructure health** shows health status alerts for infrastructure workloads in Azure Defender\*.</span></span>

<span data-ttu-id="846c7-131">Защитник Azure \* обеспечивает единую систему управления безопасностью и защитник для Office 365 в локальной и облачной рабочих нагрузках.</span><span class="sxs-lookup"><span data-stu-id="846c7-131">Azure Defender\* provides unified security management and Defender for Office 365 across on-premises and cloud workloads.</span></span> <span data-ttu-id="846c7-132">Вы можете собирать, искать и анализировать данные безопасности из различных источников, в том числе брандмауэров и других партнерских решений.</span><span class="sxs-lookup"><span data-stu-id="846c7-132">You can collect, search, and analyze security data from different sources, including firewalls and other partner solutions.</span></span>

<span data-ttu-id="846c7-133">Для получения дополнительных сведений обратитесь [к документации по Защитнику Azure \*](https://docs.microsoft.com/azure/security-center/).</span><span class="sxs-lookup"><span data-stu-id="846c7-133">For more information, see [Azure Defender\* Documentation](https://docs.microsoft.com/azure/security-center/).</span></span>

![Карта работоспособности инфраструктуры](../../media/infrastructure-health.png)
