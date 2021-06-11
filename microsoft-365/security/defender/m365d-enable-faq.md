---
title: Часто задающие вопросы при включе Microsoft 365 Defender
description: Получение ответов на наиболее часто задамые вопросы о лицензировании, разрешениях, начальных параметрах и других продуктах и службах, связанных с включением Microsoft 365 Defender
keywords: часто задаваемые вопросы, вопросы, GCC, начало работы, включить Microsoft 365 Defender, Microsoft 365 Defender, M365, безопасность, расположение данных, необходимые разрешения, право на лицензию, страница параметров
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
ms.openlocfilehash: 008e3cc6ee65597a032aa932b74a64ac591927f2
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572769"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a><span data-ttu-id="58fea-104">Часто задающие вопросы при включе Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="58fea-104">Frequently asked questions when turning on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="58fea-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="58fea-105">**Applies to:**</span></span>
- <span data-ttu-id="58fea-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="58fea-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="58fea-107">Ознакомьтесь с ответами на наиболее часто задамые вопросы о включаемом [Microsoft 365 Defender,](microsoft-365-defender.md)включая необходимые лицензии и разрешения, развертывание служб поддержки и начальные параметры.</span><span class="sxs-lookup"><span data-stu-id="58fea-107">Read responses to the most commonly asked questions about turning on [Microsoft 365 Defender](microsoft-365-defender.md), including required licenses and permissions, deploying support services, and initial settings.</span></span>

<span data-ttu-id="58fea-108">Инструкции по включению службы читайте в Microsoft 365 [Defender.](m365d-enable.md)</span><span class="sxs-lookup"><span data-stu-id="58fea-108">For instructions on how to turn on the service, [read Turn on Microsoft 365 Defender](m365d-enable.md).</span></span>

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a><span data-ttu-id="58fea-109">У меня нет Microsoft 365 E5 лицензии.</span><span class="sxs-lookup"><span data-stu-id="58fea-109">I don’t have a Microsoft 365 E5 license.</span></span> <span data-ttu-id="58fea-110">Можно ли использовать Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="58fea-110">Can I still use Microsoft 365 Defender?</span></span>

<span data-ttu-id="58fea-111">Клиенты со следующими лицензиями, не относяся к E5, могут использовать Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="58fea-111">Customers with the following non-E5 licenses can use Microsoft 365 Defender:</span></span>

- <span data-ttu-id="58fea-112">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="58fea-112">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="58fea-113">Microsoft Defender для удостоверений</span><span class="sxs-lookup"><span data-stu-id="58fea-113">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="58fea-114">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="58fea-114">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="58fea-115">Defender для Office 365 (план 2)</span><span class="sxs-lookup"><span data-stu-id="58fea-115">Defender for Office 365 (Plan 2)</span></span>
 
<span data-ttu-id="58fea-116">Полный список поддерживаемых лицензий [ознакомьтесь с требованиями лицензирования.](prerequisites.md#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="58fea-116">For a full list of supported licenses, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a><span data-ttu-id="58fea-117">Необходимо ли установить или развернуть что-либо, чтобы начать использовать Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="58fea-117">Do I need to install or deploy anything to start using Microsoft 365 Defender?</span></span>

<span data-ttu-id="58fea-118">Нет, Microsoft 365 Defender консолидирует данные из Microsoft 365 служб безопасности, которые вы уже развернули.</span><span class="sxs-lookup"><span data-stu-id="58fea-118">No, Microsoft 365 Defender consolidates data from Microsoft 365 security services that you have already deployed.</span></span> <span data-ttu-id="58fea-119">После его включения опыты инцидентов, автоматизации и охоты начнут работать в пределах развернутых продуктов.</span><span class="sxs-lookup"><span data-stu-id="58fea-119">Once you turn it on, incident, automation, and hunting experiences will start working within the scope of the deployed products.</span></span> <span data-ttu-id="58fea-120">Если ни один из этих продуктов не развернут должным образом, Microsoft 365 Defender не будет отображать данные и не сможет принять никаких действий.</span><span class="sxs-lookup"><span data-stu-id="58fea-120">If none of these products are properly deployed, Microsoft 365 Defender will not display any data and is unable to take any action.</span></span>

<span data-ttu-id="58fea-121">Чтобы оптимизировать Microsoft 365 Defender, рекомендуется развернуть  все поддерживаемые Microsoft 365 и [службы.](deploy-supported-services.md)</span><span class="sxs-lookup"><span data-stu-id="58fea-121">To optimize your Microsoft 365 Defender experiences, we recommend deploying *all* supported [Microsoft 365 security products and services](deploy-supported-services.md).</span></span>

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a><span data-ttu-id="58fea-122">Где Microsoft 365 Defender обрабатывать и хранить мои данные?</span><span class="sxs-lookup"><span data-stu-id="58fea-122">Where does Microsoft 365 Defender process and store my data?</span></span>
<span data-ttu-id="58fea-123">Microsoft 365 Defender автоматически выбирает оптимальное расположение для центра обработки и хранения консолидированных данных.</span><span class="sxs-lookup"><span data-stu-id="58fea-123">Microsoft 365 Defender automatically selects an optimal location for the data center where consolidated data is processed and stored.</span></span> <span data-ttu-id="58fea-124">Если у вас есть Microsoft Defender для конечной точки, он выбирает то же расположение, что и Защитник для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="58fea-124">If you have Microsoft Defender for Endpoint, it selects the same location used by Defender for Endpoint.</span></span>

>[!NOTE]
><span data-ttu-id="58fea-125">Microsoft Defender для конечной точки автоматически содержит положения в центрах обработки данных Европейского союза (ЕС) при включении через Azure Defender.</span><span class="sxs-lookup"><span data-stu-id="58fea-125">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="58fea-126">Microsoft 365 Defender автоматически будет в том же центре обработки данных ЕС для клиентов, которые таким образом обуяли Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="58fea-126">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Microsoft Defender for Endpoint in this manner.</span></span> 

<span data-ttu-id="58fea-127">Расположение центра обработки данных отображается до и после предоставления службы на странице параметров Microsoft 365 Defender **(Параметры > Microsoft 365 Defender).**</span><span class="sxs-lookup"><span data-stu-id="58fea-127">The data center location is shown before and after the service is provisioned in the settings page for Microsoft 365 Defender (**Settings > Microsoft 365 Defender**).</span></span> <span data-ttu-id="58fea-128">Если вы предпочитаете использовать другое расположение центра обработки данных, выберите "Нужна **помощь"?** в центре Microsoft 365, чтобы связаться с поддержкой Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="58fea-128">If you prefer to use another data center location, select **Need help?** in the Microsoft 365 security center to contact Microsoft support.</span></span>

## <a name="where-can-i-access-microsoft-365-defender"></a><span data-ttu-id="58fea-129">Где можно получить доступ Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="58fea-129">Where can I access Microsoft 365 Defender?</span></span>

<span data-ttu-id="58fea-130">Microsoft 365 Defender доступен в центре Microsoft 365 безопасности.</span><span class="sxs-lookup"><span data-stu-id="58fea-130">Microsoft 365 Defender is available in Microsoft 365 security center.</span></span> <span data-ttu-id="58fea-131">Чтобы перейти в центр безопасности, просмотрите [https://security.microsoft.com](https://security.microsoft.com) URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="58fea-131">To go to the security center, browse to the URL [https://security.microsoft.com](https://security.microsoft.com).</span></span>

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a><span data-ttu-id="58fea-132">Какие разрешения требуется для доступа к Microsoft 365 Defender в центре Microsoft 365 безопасности?</span><span class="sxs-lookup"><span data-stu-id="58fea-132">What permissions do I need to access Microsoft 365 Defender in Microsoft 365 security center?</span></span>

<span data-ttu-id="58fea-133">Учетные записи, задав следующие роли Azure Active Directory Azure AD, могут получать доступ Microsoft 365 и данным Defender:</span><span class="sxs-lookup"><span data-stu-id="58fea-133">Accounts assigned the following Azure Active Directory (Azure AD) roles can access Microsoft 365 Defender functionality and data:</span></span>

- <span data-ttu-id="58fea-134">Глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="58fea-134">Global administrator</span></span>
- <span data-ttu-id="58fea-135">Администратор безопасности</span><span class="sxs-lookup"><span data-stu-id="58fea-135">Security administrator</span></span>
- <span data-ttu-id="58fea-136">Оператор безопасности</span><span class="sxs-lookup"><span data-stu-id="58fea-136">Security Operator</span></span>
- <span data-ttu-id="58fea-137">Глобальный читатель</span><span class="sxs-lookup"><span data-stu-id="58fea-137">Global Reader</span></span>
- <span data-ttu-id="58fea-138">Читатель сведений о безопасности</span><span class="sxs-lookup"><span data-stu-id="58fea-138">Security Reader</span></span>

>[!NOTE]
><span data-ttu-id="58fea-139">Параметры управления доступом на основе ролей в Microsoft Defender для конечной точки влияют на доступ к данным.</span><span class="sxs-lookup"><span data-stu-id="58fea-139">Role-based access control settings in Microsoft Defender for Endpoint influence access to data.</span></span> <span data-ttu-id="58fea-140">Дополнительные сведения об управлении доступом к [Microsoft 365 Defender](m365d-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="58fea-140">For more information, read about [managing access to Microsoft 365 Defender](m365d-permissions.md).</span></span>

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a><span data-ttu-id="58fea-141">В каком часовом поясе Microsoft 365 defender по умолчанию?</span><span class="sxs-lookup"><span data-stu-id="58fea-141">What time zone does Microsoft 365 Defender default to?</span></span>
<span data-ttu-id="58fea-142">По умолчанию Microsoft 365 Defender отображает сведения о времени в часовом поясе UTC.</span><span class="sxs-lookup"><span data-stu-id="58fea-142">By default, Microsoft 365 Defender displays time information in the UTC time zone.</span></span> <span data-ttu-id="58fea-143">Этот параметр можно изменить, чтобы использовать локальный часовой пояс.</span><span class="sxs-lookup"><span data-stu-id="58fea-143">You can change this setting to use your local time zone.</span></span> [<span data-ttu-id="58fea-144">Узнайте о настройке часовой зоны</span><span class="sxs-lookup"><span data-stu-id="58fea-144">Learn about setting the time zone</span></span>](m365d-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a><span data-ttu-id="58fea-145">Как узнать о новых Microsoft 365 Defender и обновлениях пользовательского интерфейса?</span><span class="sxs-lookup"><span data-stu-id="58fea-145">How can I learn about new Microsoft 365 Defender feature and UI updates?</span></span>

<span data-ttu-id="58fea-146">Корпорация Майкрософт регулярно предоставляет информацию по различным каналам, в том числе:</span><span class="sxs-lookup"><span data-stu-id="58fea-146">Microsoft regularly provides information through the various channels, including:</span></span>

- <span data-ttu-id="58fea-147">Центр [сообщений в](../../admin/manage/message-center.md) центре Microsoft 365 администрирования</span><span class="sxs-lookup"><span data-stu-id="58fea-147">The [message center](../../admin/manage/message-center.md) in Microsoft 365 admin center</span></span>
- <span data-ttu-id="58fea-148">Blogposts в [сообществе Microsoft 365 безопасности & соответствия требованиям](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span><span class="sxs-lookup"><span data-stu-id="58fea-148">Blogposts in the [Microsoft 365 security & compliance tech community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span></span>

<span data-ttu-id="58fea-149">Получите последние общедоступные возможности, включив функции [предварительного просмотра.](preview.md)</span><span class="sxs-lookup"><span data-stu-id="58fea-149">Get the latest publicly available experiences by turning on [preview features](preview.md).</span></span>

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a><span data-ttu-id="58fea-150">Доступен ли Microsoft 365 Defender для облако сообщества для государственных организаций (GCC) или GCC High?</span><span class="sxs-lookup"><span data-stu-id="58fea-150">Is Microsoft 365 Defender available for US Government Community Cloud (GCC) or GCC High?</span></span>
<span data-ttu-id="58fea-151">В настоящее время она недоступна.</span><span class="sxs-lookup"><span data-stu-id="58fea-151">At the moment, it is not available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="58fea-152">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="58fea-152">Related topics</span></span>

- [<span data-ttu-id="58fea-153">Microsoft 365 Обзор defender</span><span class="sxs-lookup"><span data-stu-id="58fea-153">Microsoft 365 Defender overview</span></span>](microsoft-365-defender.md)
- <span data-ttu-id="58fea-154">[Включи Microsoft 365 Defender](m365d-enable.md).</span><span class="sxs-lookup"><span data-stu-id="58fea-154">[Turn on Microsoft 365 Defender](m365d-enable.md).</span></span>
- [<span data-ttu-id="58fea-155">Требования к лицензированию и другие предварительные требования</span><span class="sxs-lookup"><span data-stu-id="58fea-155">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="58fea-156">Развертывание поддерживаемых служб</span><span class="sxs-lookup"><span data-stu-id="58fea-156">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="58fea-157">Включение предварительных функций</span><span class="sxs-lookup"><span data-stu-id="58fea-157">Turn on preview features</span></span>](preview.md)
