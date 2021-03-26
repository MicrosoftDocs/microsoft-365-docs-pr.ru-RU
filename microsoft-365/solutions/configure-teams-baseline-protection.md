---
title: Настройка команд с базовым уровнем защиты
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom:
- Ent_Solutions
description: Узнайте, как развернуть команды с базовым уровнем защиты.
ms.openlocfilehash: 728a41bd521ed32c57c981be576e46eaee344099
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222747"
---
# <a name="configure-teams-with-baseline-protection"></a><span data-ttu-id="d70bc-103">Настройка команд с базовым уровнем защиты</span><span class="sxs-lookup"><span data-stu-id="d70bc-103">Configure teams with baseline protection</span></span>

<span data-ttu-id="d70bc-104">В этой статье объясняется, как развернуть команды с базовым уровнем защиты.</span><span class="sxs-lookup"><span data-stu-id="d70bc-104">In this article, we look at how to deploy teams with a baseline level of protection.</span></span> <span data-ttu-id="d70bc-105">Этот уровень предоставляет пользователям широкий спектр возможностей для совместной работы, улучшает управление разрешениями и обеспечивает базовую защиту от чрезмерного раскрытия информации.</span><span class="sxs-lookup"><span data-stu-id="d70bc-105">This level allows users a wide range of options for collaboration while enhancing permissions management and providing basic protection against oversharing.</span></span> <span data-ttu-id="d70bc-106">Для защиты этого уровня рекомендуется использовать политики удостоверений и доступа к устройствам, а также защиту от вредоносных программ.</span><span class="sxs-lookup"><span data-stu-id="d70bc-106">Recommended protections for this level include identity and device access policies and protection against malware.</span></span> <span data-ttu-id="d70bc-107">Кроме того, при необходимости можно применить политики условного доступа и защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="d70bc-107">Additionally, you can apply conditional access policies and data loss protections as needed.</span></span>

## <a name="initial-protections"></a><span data-ttu-id="d70bc-108">Начальная защита</span><span class="sxs-lookup"><span data-stu-id="d70bc-108">Initial protections</span></span>

<span data-ttu-id="d70bc-109">На первом этапе рекомендуется настроить базовые политики удостоверений и доступа к устройствам.</span><span class="sxs-lookup"><span data-stu-id="d70bc-109">As a first step, we recommend that you configure basic identity and device-access policies.</span></span> <span data-ttu-id="d70bc-110">Дополнительные сведения см. в статье [Рекомендации по политикам безопасности для чатов, групп и файлов Teams](../security/office-365-security/teams-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="d70bc-110">See [Policy recommendations for securing Teams chats, groups, and files](../security/office-365-security/teams-access-policies.md) for details.</span></span>

<span data-ttu-id="d70bc-111">Мы также рекомендуем включить основные функции Defender для Office 365 с целью защиты от вредоносных программ в документах, вложениях и ссылках.</span><span class="sxs-lookup"><span data-stu-id="d70bc-111">We also recommend turning on basic Defender for Office 365 features to guard against malware in documents, attachments, and links.</span></span> <span data-ttu-id="d70bc-112">Рекомендуем включить все параметры, указанные в таблице ниже.</span><span class="sxs-lookup"><span data-stu-id="d70bc-112">We recommend turning on each of the options in the following table.</span></span>

|<span data-ttu-id="d70bc-113">Параметр</span><span class="sxs-lookup"><span data-stu-id="d70bc-113">Option</span></span>|<span data-ttu-id="d70bc-114">Информация</span><span class="sxs-lookup"><span data-stu-id="d70bc-114">Information</span></span>|
|:------|:-----------|
|<span data-ttu-id="d70bc-115">Безопасные вложения для SPO, OneDrive и Teams</span><span class="sxs-lookup"><span data-stu-id="d70bc-115">Safe Attachments for SPO, OneDrive and Teams</span></span>|[<span data-ttu-id="d70bc-116">Безопасные вложения</span><span class="sxs-lookup"><span data-stu-id="d70bc-116">Safe Attachments</span></span>](../security/office-365-security/safe-attachments.md)<br>[<span data-ttu-id="d70bc-117">Defender для Office 365 — SharePoint, OneDrive и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d70bc-117">Defender for Office 365 - SharePoint, OneDrive, and Microsoft Teams</span></span>](../security/office-365-security/mdo-for-spo-odb-and-teams.md)|
|<span data-ttu-id="d70bc-118">Безопасные документы</span><span class="sxs-lookup"><span data-stu-id="d70bc-118">Safe Documents</span></span>|[<span data-ttu-id="d70bc-119">Безопасные документы в Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="d70bc-119">Safe Documents in Microsoft Defender for Office 365</span></span>](../security/office-365-security/safe-docs.md)|
|<span data-ttu-id="d70bc-120">Безопасные ссылки для Teams</span><span class="sxs-lookup"><span data-stu-id="d70bc-120">Safe Links for Teams</span></span>|[<span data-ttu-id="d70bc-121">Безопасные ссылки Office 365 в Teams</span><span class="sxs-lookup"><span data-stu-id="d70bc-121">Office 365 Safe Links in Teams</span></span>](../security/office-365-security/safe-links.md)<br>[<span data-ttu-id="d70bc-122">Безопасные ссылки</span><span class="sxs-lookup"><span data-stu-id="d70bc-122">Safe Links</span></span>](../security/office-365-security/safe-links.md)|

## <a name="teams-guest-sharing"></a><span data-ttu-id="d70bc-123">Предоставление общего доступа гостям в Teams</span><span class="sxs-lookup"><span data-stu-id="d70bc-123">Teams guest sharing</span></span>

<span data-ttu-id="d70bc-124">На каждом из уровней имеется возможность общего доступа для пользователей за пределами организации.</span><span class="sxs-lookup"><span data-stu-id="d70bc-124">In each of the tiers, we have the option of sharing with people outside your organization.</span></span> <span data-ttu-id="d70bc-125">На конфиденциальном и строго конфиденциальном уровнях защиты можно отключить предоставление общего доступа гостям на уровне команды, воспользовавшись метками конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="d70bc-125">For the sensitive and highly sensitive tiers, we will have the option to turn guest sharing off at the team level by using sensitivity labels.</span></span> <span data-ttu-id="d70bc-126">Однако параметр общего доступа для гостей на уровне организации должен быть включен, чтобы предоставление общего доступа гостям вообще было возможно в Teams.</span><span class="sxs-lookup"><span data-stu-id="d70bc-126">But the organization-level guest sharing setting must be turned on for guest sharing to work at all in Teams.</span></span>

![Снимок экрана: переключатель гостевого доступа в Teams](../media/teams-guest-access-toggle-on.png)

<span data-ttu-id="d70bc-128">Настройка параметров гостевого доступа в Teams</span><span class="sxs-lookup"><span data-stu-id="d70bc-128">To set Teams guest access settings</span></span>

1. <span data-ttu-id="d70bc-129">Войдите в Центр администрирования Microsoft 365 на сайте [https://admin.microsoft.com](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="d70bc-129">Log in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="d70bc-130">В области навигации слева щелкните **Показать все**.</span><span class="sxs-lookup"><span data-stu-id="d70bc-130">In the left navigation, click **Show all**.</span></span>
3. <span data-ttu-id="d70bc-131">В разделе **Центры администрирования** щелкните **Teams**.</span><span class="sxs-lookup"><span data-stu-id="d70bc-131">Under **Admin centers**, click **Teams**.</span></span>
4. <span data-ttu-id="d70bc-132">В Центре администрирования Teams, в области навигации слева разверните раздел **Параметры на уровне организации** и щелкните **Гостевой доступ**.</span><span class="sxs-lookup"><span data-stu-id="d70bc-132">In the Teams admin center, in the left navigation, expand **Org-wide settings** and click **Guest access**.</span></span>
5. <span data-ttu-id="d70bc-133">Убедитесь, что для параметра **Разрешить гостевой доступ в Teams** задано значение **Вкл.**.</span><span class="sxs-lookup"><span data-stu-id="d70bc-133">Ensure that **Allow guest access in Teams** is set to **On**.</span></span>
6. <span data-ttu-id="d70bc-134">Внесите необходимые изменения в дополнительные параметры гостей и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="d70bc-134">Make any desired changes to the additional guest settings, and then click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="d70bc-135">Активация параметра гостя в Teams может занять до двадцати четырех часов с момента включения.</span><span class="sxs-lookup"><span data-stu-id="d70bc-135">It may take up to twenty-four hours for the Teams guest setting to become active after you turn it on.</span></span>

<span data-ttu-id="d70bc-136">Общий доступ для гостей включается по умолчанию для групп Office 365 и SharePoint, однако если его настройки для организации были изменены, рекомендуем ознакомиться со статьей [Совместная работа с гостями в команде](./collaborate-as-team.md), чтобы убедиться, что общий доступ для гостей будет доступен в Teams.</span><span class="sxs-lookup"><span data-stu-id="d70bc-136">Guest sharing is turned on by default for Office 365 groups and SharePoint, however if you have previously changed any of the guest sharing settings for your organization, we recommend that you review [Collaborate with guests in a team](./collaborate-as-team.md) to ensure that guest sharing will be available in Teams.</span></span>

## <a name="site-and-file-sharing"></a><span data-ttu-id="d70bc-137">Общий доступ к сайтам и файлам</span><span class="sxs-lookup"><span data-stu-id="d70bc-137">Site and file sharing</span></span>

<span data-ttu-id="d70bc-138">Чтобы снизить риск случайного предоставления общего доступа к файлам или папкам пользователям за пределами вашей организации, рекомендуем изменить ссылку для общего доступа по умолчанию для SharePoint на *Только пользователи из организации*.</span><span class="sxs-lookup"><span data-stu-id="d70bc-138">To reduce the risk of accidentally sharing files or folders with people outside your organization, we recommend changing the default sharing link for SharePoint to *Only people in your organization*.</span></span> <span data-ttu-id="d70bc-139">(Если необходим внешний общий доступ и включен общий доступ для гостей, пользователи могут изменить тип ссылки при предоставлении общего доступа.)</span><span class="sxs-lookup"><span data-stu-id="d70bc-139">(If users need to share externally, and you have enabled guest sharing, they can still change the link type when they share.)</span></span>

<span data-ttu-id="d70bc-140">Изменение ссылки для общего доступа по умолчанию</span><span class="sxs-lookup"><span data-stu-id="d70bc-140">To change the default sharing link</span></span>
1. <span data-ttu-id="d70bc-141">Откройте [Центр администрирования SharePoint](https://admin.microsoft.com/sharepoint).</span><span class="sxs-lookup"><span data-stu-id="d70bc-141">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="d70bc-142">В разделе **Политики** щелкните **Общий доступ**.</span><span class="sxs-lookup"><span data-stu-id="d70bc-142">Under **Policies**, click **Sharing**.</span></span>
3. <span data-ttu-id="d70bc-143">В разделе **Ссылки на файлы и папки** выберите пункт **Только пользователи из организации**.</span><span class="sxs-lookup"><span data-stu-id="d70bc-143">Under **File and folder links**, select **Only people in your organization**.</span></span>
4. <span data-ttu-id="d70bc-144">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="d70bc-144">Click **Save**.</span></span>

<span data-ttu-id="d70bc-145">Чтобы обеспечить оптимальный общий доступ для гостей, мы также рекомендуем включить [интеграцию SharePoint и OneDrive с Azure AD B2B](/sharepoint/sharepoint-azureb2b-integration-preview).</span><span class="sxs-lookup"><span data-stu-id="d70bc-145">For the best guest sharing experience, we also recommend that you enable [SharePoint and OneDrive integration with Azure AD B2B](/sharepoint/sharepoint-azureb2b-integration-preview).</span></span>

## <a name="create-a-team"></a><span data-ttu-id="d70bc-146">Создание команды</span><span class="sxs-lookup"><span data-stu-id="d70bc-146">Create a team</span></span>

<span data-ttu-id="d70bc-147">Дополнительная настройка для базового уровня защиты выполняется на сайте SharePoint, связанном с командой.</span><span class="sxs-lookup"><span data-stu-id="d70bc-147">Additional configuration for the baseline level of protection is done in the SharePoint site associated with a team.</span></span> <span data-ttu-id="d70bc-148">Прежде чем перейти к следующему разделу, [создайте общедоступную или приватную команду](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b).</span><span class="sxs-lookup"><span data-stu-id="d70bc-148">[Create a public or private team](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) before proceeding to the next section.</span></span>

## <a name="site-sharing-settings"></a><span data-ttu-id="d70bc-149">Настройки общего доступа к сайту</span><span class="sxs-lookup"><span data-stu-id="d70bc-149">Site sharing settings</span></span>

<span data-ttu-id="d70bc-150">По умолчанию участники сайта SharePoint могут приглашать других пользователей на сайт.</span><span class="sxs-lookup"><span data-stu-id="d70bc-150">By default, members of a SharePoint site can invite others to the site.</span></span> <span data-ttu-id="d70bc-151">Если сайт является частью команды, участники команды будут включены в число участников сайта.</span><span class="sxs-lookup"><span data-stu-id="d70bc-151">When a site is part of a team, team members are included as site members.</span></span> <span data-ttu-id="d70bc-152">Тем не менее, пользователи, добавленные непосредственно на сайт, не имеют доступа к остальной части команды.</span><span class="sxs-lookup"><span data-stu-id="d70bc-152">However, people added directly to the site don't have access to the rest of the team.</span></span> <span data-ttu-id="d70bc-153">В связи с этим рекомендуем управлять разрешениями только через команду.</span><span class="sxs-lookup"><span data-stu-id="d70bc-153">For this reason, we recommend managing permissions exclusively through the team.</span></span>

<span data-ttu-id="d70bc-154">Чтобы помочь в управлении разрешениями, рекомендуем настроить связанный сайт, который могут совместно использовать только владельцы.</span><span class="sxs-lookup"><span data-stu-id="d70bc-154">To help with permissions management, we recommend configuring the associated site to only allow owners to share the site by itself.</span></span> <span data-ttu-id="d70bc-155">Это упрощает управление разрешениями и помогает избежать доступа пользователей без ведома владельца команды.</span><span class="sxs-lookup"><span data-stu-id="d70bc-155">This simplifies permissions management and helps prevent access by people without a team owner's knowledge.</span></span> <span data-ttu-id="d70bc-156">Выполните эти действия для каждой команды, которой требуется базовый уровень защиты.</span><span class="sxs-lookup"><span data-stu-id="d70bc-156">Do this for each team that requires baseline protection.</span></span>

<span data-ttu-id="d70bc-157">Обновление параметров общего доступа к сайту</span><span class="sxs-lookup"><span data-stu-id="d70bc-157">To update the site sharing settings</span></span>
1. <span data-ttu-id="d70bc-158">На панели инструментов для команды щелкните **Файлы**.</span><span class="sxs-lookup"><span data-stu-id="d70bc-158">In the tool bar for the team, click **Files**.</span></span>
2. <span data-ttu-id="d70bc-159">Щелкните **Открыть в SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="d70bc-159">Click **Open in SharePoint**.</span></span>
3. <span data-ttu-id="d70bc-160">На панели инструментов сайта SharePoint щелкните значок параметров и выберите **Разрешения для сайта**.</span><span class="sxs-lookup"><span data-stu-id="d70bc-160">In the tool bar of the SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>
4. <span data-ttu-id="d70bc-161">На панели **разрешений сайта** в разделе **Общий доступ к сайту** нажмите кнопку **Изменить, как участники могут делиться**.</span><span class="sxs-lookup"><span data-stu-id="d70bc-161">In the **Site permissions** pane, under **Site sharing**, click **Change how members can share**.</span></span>
5. <span data-ttu-id="d70bc-162">В разделе **Разрешения общего доступа** выберите **Владельцы и участники сайта, и пользователи с правами «Редактировать» могут предоставлять общий доступ к файлам и папкам, но только владельцы сайта могут делиться сайтом**, а затем нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="d70bc-162">Under **Sharing permissions**, choose **Site owners and members, and people with Edit permissions can share files and folders, but only site owners can share the site**, and then click **Save**.</span></span>

## <a name="additional-protections"></a><span data-ttu-id="d70bc-163">Дополнительная защита</span><span class="sxs-lookup"><span data-stu-id="d70bc-163">Additional protections</span></span>

<span data-ttu-id="d70bc-164">В Microsoft 365 доступны дополнительные методы защиты контента.</span><span class="sxs-lookup"><span data-stu-id="d70bc-164">Microsoft 365 offers additional methods for securing your content.</span></span> <span data-ttu-id="d70bc-165">Рассмотрите возможность использования следующих параметров для улучшения защиты вашей организации.</span><span class="sxs-lookup"><span data-stu-id="d70bc-165">Consider if the following options would help improve security for your organization.</span></span>

- <span data-ttu-id="d70bc-166">Ваши гости должны согласиться с [условиями использования](/azure/active-directory/conditional-access/terms-of-use).</span><span class="sxs-lookup"><span data-stu-id="d70bc-166">Have guests agree to a [terms of use](/azure/active-directory/conditional-access/terms-of-use).</span></span>
- <span data-ttu-id="d70bc-167">Настройте [политику времени ожидания сеанса](/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime) для гостей.</span><span class="sxs-lookup"><span data-stu-id="d70bc-167">Configure a [session timeout policy](/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime) for guests.</span></span>
- <span data-ttu-id="d70bc-168">Создайте [типы конфиденциальной информации](../compliance/sensitive-information-type-learn-about.md) и используйте [защиту от потери данных](../compliance/data-loss-prevention-policies.md) для настройки политик доступа к конфиденциальной информации.</span><span class="sxs-lookup"><span data-stu-id="d70bc-168">Create [sensitive information types](../compliance/sensitive-information-type-learn-about.md) and use [data loss protection](../compliance/data-loss-prevention-policies.md) to set policies around accessing sensitive information.</span></span>

## <a name="see-also"></a><span data-ttu-id="d70bc-169">См. также</span><span class="sxs-lookup"><span data-stu-id="d70bc-169">See Also</span></span>

[<span data-ttu-id="d70bc-170">Управление политиками собраний в Teams</span><span class="sxs-lookup"><span data-stu-id="d70bc-170">Manage meeting policies in Teams</span></span>](/microsoftteams/meeting-policies-in-teams)

[<span data-ttu-id="d70bc-171">Приступая к управлению рисками утечки внутренней информации</span><span class="sxs-lookup"><span data-stu-id="d70bc-171">Get started with insider risk management</span></span>](../compliance/insider-risk-management-configure.md)