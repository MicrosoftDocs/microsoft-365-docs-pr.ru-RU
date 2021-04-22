---
title: Часто задающие вопросы при включив Microsoft 365 Defender
description: Получение ответов на наиболее часто задамые вопросы о лицензировании, разрешениях, начальных параметрах и других продуктах и службах, связанных с включением Microsoft 365 Defender
keywords: часто задаваемые вопросы, GCC, привнося начало, включить Microsoft 365 Defender, Microsoft 365 Defender, M365, безопасность, расположение данных, необходимые разрешения, право на лицензию, страницу параметров
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 55c1a3807fe8e28ca12f4f638c1ab2ca717523ed
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933437"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a><span data-ttu-id="d94c7-104">Часто задающие вопросы при включив Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d94c7-104">Frequently asked questions when turning on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d94c7-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="d94c7-105">**Applies to:**</span></span>
- <span data-ttu-id="d94c7-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d94c7-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="d94c7-107">Ознакомьтесь с ответами на наиболее часто задамые вопросы о включании [защитника Microsoft 365,](microsoft-365-defender.md)включая необходимые лицензии и разрешения, развертывание служб поддержки и начальные параметры.</span><span class="sxs-lookup"><span data-stu-id="d94c7-107">Read responses to the most commonly asked questions about turning on [Microsoft 365 Defender](microsoft-365-defender.md), including required licenses and permissions, deploying support services, and initial settings.</span></span>

<span data-ttu-id="d94c7-108">Инструкции по включению службы читайте в публикации ["Включи Microsoft 365 Defender".](m365d-enable.md)</span><span class="sxs-lookup"><span data-stu-id="d94c7-108">For instructions on how to turn on the service, [read Turn on Microsoft 365 Defender](m365d-enable.md).</span></span>

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a><span data-ttu-id="d94c7-109">У меня нет лицензии Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="d94c7-109">I don’t have a Microsoft 365 E5 license.</span></span> <span data-ttu-id="d94c7-110">Могу ли я по-прежнему использовать Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="d94c7-110">Can I still use Microsoft 365 Defender?</span></span>

<span data-ttu-id="d94c7-111">Клиенты со следующими лицензиями, не относясь к E5, могут использовать Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="d94c7-111">Customers with the following non-E5 licenses can use Microsoft 365 Defender:</span></span>

- <span data-ttu-id="d94c7-112">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="d94c7-112">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="d94c7-113">Microsoft Defender для удостоверений</span><span class="sxs-lookup"><span data-stu-id="d94c7-113">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="d94c7-114">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="d94c7-114">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="d94c7-115">Defender for Office 365 (Plan 2)</span><span class="sxs-lookup"><span data-stu-id="d94c7-115">Defender for Office 365 (Plan 2)</span></span>
 
<span data-ttu-id="d94c7-116">Полный список поддерживаемых лицензий [ознакомьтесь с требованиями лицензирования.](prerequisites.md#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="d94c7-116">For a full list of supported licenses, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a><span data-ttu-id="d94c7-117">Необходимо ли установить или развернуть что-либо, чтобы начать использовать Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="d94c7-117">Do I need to install or deploy anything to start using Microsoft 365 Defender?</span></span>

<span data-ttu-id="d94c7-118">Нет, Microsoft 365 Defender консолидирует данные из служб безопасности Microsoft 365, которые вы уже развернули.</span><span class="sxs-lookup"><span data-stu-id="d94c7-118">No, Microsoft 365 Defender consolidates data from Microsoft 365 security services that you have already deployed.</span></span> <span data-ttu-id="d94c7-119">После его включения опыты инцидентов, автоматизации и охоты начнут работать в пределах развернутых продуктов.</span><span class="sxs-lookup"><span data-stu-id="d94c7-119">Once you turn it on, incident, automation, and hunting experiences will start working within the scope of the deployed products.</span></span> <span data-ttu-id="d94c7-120">Если ни один из этих продуктов не развернут должным образом, Microsoft 365 Defender не будет отображать данные и не сможет принять никаких действий.</span><span class="sxs-lookup"><span data-stu-id="d94c7-120">If none of these products are properly deployed, Microsoft 365 Defender will not display any data and is unable to take any action.</span></span>

<span data-ttu-id="d94c7-121">Для оптимизации работы с Microsoft 365 Defender  рекомендуется развернуть все поддерживаемые продукты и службы безопасности [Microsoft 365.](deploy-supported-services.md)</span><span class="sxs-lookup"><span data-stu-id="d94c7-121">To optimize your Microsoft 365 Defender experiences, we recommend deploying *all* supported [Microsoft 365 security products and services](deploy-supported-services.md).</span></span>

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a><span data-ttu-id="d94c7-122">Где Microsoft 365 Defender обрабатывает и хранит мои данные?</span><span class="sxs-lookup"><span data-stu-id="d94c7-122">Where does Microsoft 365 Defender process and store my data?</span></span>
<span data-ttu-id="d94c7-123">Microsoft 365 Defender автоматически выбирает оптимальное расположение для центра обработки и хранения консолидированных данных.</span><span class="sxs-lookup"><span data-stu-id="d94c7-123">Microsoft 365 Defender automatically selects an optimal location for the data center where consolidated data is processed and stored.</span></span> <span data-ttu-id="d94c7-124">Если у вас есть Microsoft Defender для конечной точки, он выбирает то же расположение, что и Защитник для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="d94c7-124">If you have Microsoft Defender for Endpoint, it selects the same location used by Defender for Endpoint.</span></span>

>[!NOTE]
><span data-ttu-id="d94c7-125">Microsoft Defender для конечной точки автоматически содержит положения в центрах обработки данных Европейского союза (ЕС) при включении через Azure Defender.</span><span class="sxs-lookup"><span data-stu-id="d94c7-125">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="d94c7-126">Microsoft 365 Defender автоматически будет предоставление в том же центре обработки данных ЕС для клиентов, которые таким образом провизировали Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="d94c7-126">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Microsoft Defender for Endpoint in this manner.</span></span> 

<span data-ttu-id="d94c7-127">Расположение центра обработки данных отображается до и после предоставления службы на странице параметры для Microsoft 365 Defender **(Параметры > Microsoft 365 Defender).**</span><span class="sxs-lookup"><span data-stu-id="d94c7-127">The data center location is shown before and after the service is provisioned in the settings page for Microsoft 365 Defender (**Settings > Microsoft 365 Defender**).</span></span> <span data-ttu-id="d94c7-128">Если вы предпочитаете использовать другое расположение центра обработки данных, выберите "Нужна **помощь"?** в центре безопасности Microsoft 365 обратитесь в службу поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="d94c7-128">If you prefer to use another data center location, select **Need help?** in the Microsoft 365 security center to contact Microsoft support.</span></span>

## <a name="where-can-i-access-microsoft-365-defender"></a><span data-ttu-id="d94c7-129">Где можно получить доступ к Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="d94c7-129">Where can I access Microsoft 365 Defender?</span></span>

<span data-ttu-id="d94c7-130">Microsoft 365 Defender доступен в центре безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d94c7-130">Microsoft 365 Defender is available in Microsoft 365 security center.</span></span> <span data-ttu-id="d94c7-131">Чтобы перейти в центр безопасности, просмотрите [https://security.microsoft.com](https://security.microsoft.com) URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="d94c7-131">To go to the security center, browse to the URL [https://security.microsoft.com](https://security.microsoft.com).</span></span>

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a><span data-ttu-id="d94c7-132">Какие разрешения необходимо получить доступ к Microsoft 365 Defender в центре безопасности Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="d94c7-132">What permissions do I need to access Microsoft 365 Defender in Microsoft 365 security center?</span></span>

<span data-ttu-id="d94c7-133">Учетные записи, на которые назначены следующие роли Azure Active Directory (AD), могут получать доступ к функциям и данным Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="d94c7-133">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft 365 Defender functionality and data:</span></span>

- <span data-ttu-id="d94c7-134">Глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="d94c7-134">Global administrator</span></span>
- <span data-ttu-id="d94c7-135">Администратор безопасности</span><span class="sxs-lookup"><span data-stu-id="d94c7-135">Security administrator</span></span>
- <span data-ttu-id="d94c7-136">Оператор безопасности</span><span class="sxs-lookup"><span data-stu-id="d94c7-136">Security Operator</span></span>
- <span data-ttu-id="d94c7-137">Глобальный читатель</span><span class="sxs-lookup"><span data-stu-id="d94c7-137">Global Reader</span></span>
- <span data-ttu-id="d94c7-138">Читатель сведений о безопасности</span><span class="sxs-lookup"><span data-stu-id="d94c7-138">Security Reader</span></span>

>[!NOTE]
><span data-ttu-id="d94c7-139">Параметры управления доступом на основе ролей в Microsoft Defender для конечной точки влияют на доступ к данным.</span><span class="sxs-lookup"><span data-stu-id="d94c7-139">Role-based access control settings in Microsoft Defender for Endpoint influence access to data.</span></span> <span data-ttu-id="d94c7-140">Дополнительные сведения об управлении доступом к [Microsoft 365 Defender](m365d-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="d94c7-140">For more information, read about [managing access to Microsoft 365 Defender](m365d-permissions.md).</span></span>

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a><span data-ttu-id="d94c7-141">В каком часовом поясе по умолчанию работает Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="d94c7-141">What time zone does Microsoft 365 Defender default to?</span></span>
<span data-ttu-id="d94c7-142">По умолчанию Microsoft 365 Defender отображает сведения о времени в часовом поясе UTC.</span><span class="sxs-lookup"><span data-stu-id="d94c7-142">By default, Microsoft 365 Defender displays time information in the UTC time zone.</span></span> <span data-ttu-id="d94c7-143">Этот параметр можно изменить, чтобы использовать локальный часовой пояс.</span><span class="sxs-lookup"><span data-stu-id="d94c7-143">You can change this setting to use your local time zone.</span></span> [<span data-ttu-id="d94c7-144">Узнайте о настройке часовой зоны</span><span class="sxs-lookup"><span data-stu-id="d94c7-144">Learn about setting the time zone</span></span>](m365d-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a><span data-ttu-id="d94c7-145">Как узнать о новых обновлениях функции Защитника Microsoft 365 и пользовательского интерфейса?</span><span class="sxs-lookup"><span data-stu-id="d94c7-145">How can I learn about new Microsoft 365 Defender feature and UI updates?</span></span>

<span data-ttu-id="d94c7-146">Корпорация Майкрософт регулярно предоставляет информацию по различным каналам, в том числе:</span><span class="sxs-lookup"><span data-stu-id="d94c7-146">Microsoft regularly provides information through the various channels, including:</span></span>

- <span data-ttu-id="d94c7-147">Центр [сообщений в](../../admin/manage/message-center.md) центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d94c7-147">The [message center](../../admin/manage/message-center.md) in Microsoft 365 admin center</span></span>
- <span data-ttu-id="d94c7-148">Blogposts в [сообществе безопасности Microsoft 365 & соответствия требованиям](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span><span class="sxs-lookup"><span data-stu-id="d94c7-148">Blogposts in the [Microsoft 365 security & compliance tech community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span></span>

<span data-ttu-id="d94c7-149">Получите последние общедоступные возможности, включив функции [предварительного просмотра.](preview.md)</span><span class="sxs-lookup"><span data-stu-id="d94c7-149">Get the latest publicly available experiences by turning on [preview features](preview.md).</span></span>

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a><span data-ttu-id="d94c7-150">Доступен ли Microsoft 365 Defender для облачных правительственных сообществ США (GCC) или GCC High?</span><span class="sxs-lookup"><span data-stu-id="d94c7-150">Is Microsoft 365 Defender available for US Government Community Cloud (GCC) or GCC High?</span></span>
<span data-ttu-id="d94c7-151">В настоящее время она недоступна.</span><span class="sxs-lookup"><span data-stu-id="d94c7-151">At the moment, it is not available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d94c7-152">Похожие темы</span><span class="sxs-lookup"><span data-stu-id="d94c7-152">Related topics</span></span>

- [<span data-ttu-id="d94c7-153">Обзор Защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d94c7-153">Microsoft 365 Defender overview</span></span>](microsoft-365-defender.md)
- <span data-ttu-id="d94c7-154">[Включи Microsoft 365 Defender.](m365d-enable.md)</span><span class="sxs-lookup"><span data-stu-id="d94c7-154">[Turn on Microsoft 365 Defender](m365d-enable.md).</span></span>
- [<span data-ttu-id="d94c7-155">Требования к лицензированию и другие предварительные требования</span><span class="sxs-lookup"><span data-stu-id="d94c7-155">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="d94c7-156">Развертывание поддерживаемых служб</span><span class="sxs-lookup"><span data-stu-id="d94c7-156">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="d94c7-157">Включение предварительных функций</span><span class="sxs-lookup"><span data-stu-id="d94c7-157">Turn on preview features</span></span>](preview.md)
