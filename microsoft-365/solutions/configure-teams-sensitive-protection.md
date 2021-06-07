---
title: Настройте группы с защитой для конфиденциальных данных
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
recommendations: false
description: Узнайте, как развернуть группы с защитой для конфиденциальных данных.
ms.openlocfilehash: a3f715cb05ad1d5acf3c93c58959f12ebec46978
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2021
ms.locfileid: "52788346"
---
# <a name="configure-teams-with-protection-for-sensitive-data"></a><span data-ttu-id="e1c96-103">Настройте группы с защитой для конфиденциальных данных</span><span class="sxs-lookup"><span data-stu-id="e1c96-103">Configure teams with protection for sensitive data</span></span>

<span data-ttu-id="e1c96-104">В этой статье мы рассмотрим настройку команды для чувствительного уровня защиты.</span><span class="sxs-lookup"><span data-stu-id="e1c96-104">In this article, we look at setting up a team for a sensitive level of protection.</span></span> <span data-ttu-id="e1c96-105">Перед выполнением действий, описанных в этой статье, убедитесь, что вы выполнили действия, описанные в разделе [Развертывание групп с базовой защитой](configure-teams-baseline-protection.md).</span><span class="sxs-lookup"><span data-stu-id="e1c96-105">Be sure you've completed the steps in [Deploy teams with baseline protection](configure-teams-baseline-protection.md) before following the steps in this article.</span></span> <span data-ttu-id="e1c96-106">Чувствительный уровень предлагает следующие дополнительные защиты по сравнению с базовым уровнем:</span><span class="sxs-lookup"><span data-stu-id="e1c96-106">The sensitive tier offers the following additional protections over the baseline tier:</span></span>

- <span data-ttu-id="e1c96-p102">Метка конфиденциальности для команды, позволяющая включать или отключать гостевой общий доступ и ограничивающая доступ к контенту SharePoint только веб-содержимым для неуправляемых устройств. Эта метка также может быть использована для классификации файлов.</span><span class="sxs-lookup"><span data-stu-id="e1c96-p102">A sensitivity label for the team that allows you to turn guest sharing on or off and limits access to SharePoint content to web-only for unmanaged devices. This label can also be used to classify files.</span></span>
- <span data-ttu-id="e1c96-109">Более ограниченный тип ссылки для обмена по умолчанию</span><span class="sxs-lookup"><span data-stu-id="e1c96-109">A more restrictive default sharing link type</span></span>
- <span data-ttu-id="e1c96-110">Только владельцы команд могут создавать частные каналы.</span><span class="sxs-lookup"><span data-stu-id="e1c96-110">Only team owners can create private channels.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="e1c96-111">Видеодемонстрация</span><span class="sxs-lookup"><span data-stu-id="e1c96-111">Video demonstration</span></span>

<span data-ttu-id="e1c96-112">Посмотрите это видео с обзором процедур, описанных в этой статье.</span><span class="sxs-lookup"><span data-stu-id="e1c96-112">Watch this video for a walkthrough of the procedures described in this article.</span></span>
<br>
<br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4NMS6]

## <a name="guest-sharing"></a><span data-ttu-id="e1c96-113">Предоставление общего доступа гостям</span><span class="sxs-lookup"><span data-stu-id="e1c96-113">Guest sharing</span></span>

<span data-ttu-id="e1c96-114">В зависимости от характера вашего бизнеса, вы можете или не можете включить гостевой обмен для команд, которые содержат конфиденциальные данные.</span><span class="sxs-lookup"><span data-stu-id="e1c96-114">Depending on the nature of your business, you may or may not want to enable guest sharing for teams that contain sensitive data.</span></span> <span data-ttu-id="e1c96-115">Если вы планируете сотрудничать с людьми, не входящими в вашу организацию, в команде, мы рекомендуем включить обмен гостями.</span><span class="sxs-lookup"><span data-stu-id="e1c96-115">If you do plan to collaborate with people outside your organization in the team, we recommend enabling guest sharing.</span></span> <span data-ttu-id="e1c96-116">Microsoft 365 включает в себя множество функций безопасности и соответствия требованиям, которые помогут вам безопасно делиться конфиденциальным контентом.</span><span class="sxs-lookup"><span data-stu-id="e1c96-116">Microsoft 365 includes a variety of security and compliance features to help you share sensitive content securely.</span></span> <span data-ttu-id="e1c96-117">Как правило, это более безопасный вариант, чем отправка содержимого по электронной почте непосредственно людям за пределами вашей организации.</span><span class="sxs-lookup"><span data-stu-id="e1c96-117">This is generally a more secure option than emailing content directly to people outside your organization.</span></span>

<span data-ttu-id="e1c96-118">Подробнее о том, как безопасно делиться с гостями, см. На следующих ресурсах:</span><span class="sxs-lookup"><span data-stu-id="e1c96-118">For details about sharing with guests securely, see the following resources:</span></span>

- [<span data-ttu-id="e1c96-119">Ограничьте случайное воздействие файлов при обмене с людьми за пределами вашей организации</span><span class="sxs-lookup"><span data-stu-id="e1c96-119">Limit accidental exposure to files when sharing with people outside your organization</span></span>](./share-limit-accidental-exposure.md)
- [<span data-ttu-id="e1c96-120">Создание безопасной среды гостевого общего доступа</span><span class="sxs-lookup"><span data-stu-id="e1c96-120">Create a secure guest sharing environment</span></span>](./create-secure-guest-sharing-environment.md)

<span data-ttu-id="e1c96-121">Чтобы разрешить или заблокировать гостевой обмен, мы используем комбинацию метки чувствительности для команды и элементов управления общим доступом на уровне сайта для связанного сайта SharePoint, которые обсуждаются позже.</span><span class="sxs-lookup"><span data-stu-id="e1c96-121">To allow or block guest sharing, we use a combination of a sensitivity label for the team and site-level sharing controls for the associated SharePoint site, both discussed later.</span></span>

## <a name="sensitivity-labels"></a><span data-ttu-id="e1c96-122">Метки конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="e1c96-122">Sensitivity labels</span></span>

<span data-ttu-id="e1c96-123">Для чувствительного уровня защиты мы будем использовать метку чувствительности для классификации команды.</span><span class="sxs-lookup"><span data-stu-id="e1c96-123">For the sensitive level of protection, we'll be using a sensitivity label to classify the team.</span></span> <span data-ttu-id="e1c96-124">Эту метку также можно использовать для классификации отдельных файлов в этой или других группах или в других местоположениях файлов, таких как SharePoint или OneDrive.</span><span class="sxs-lookup"><span data-stu-id="e1c96-124">This label can also be used to classify individual files in this or other teams, or in other file locations such as SharePoint or OneDrive.</span></span> 

<span data-ttu-id="e1c96-125">В качестве первого шага необходимо включить метки чувствительности для Teams.</span><span class="sxs-lookup"><span data-stu-id="e1c96-125">As a first step, you must enable sensitivity labels for Teams.</span></span> <span data-ttu-id="e1c96-126">Дополнительные сведения см. в разделе [Использование меток чувствительности для защиты содержимого в Microsoft Teams, группах Office 365 и сайтах SharePoint](../compliance/sensitivity-labels-teams-groups-sites.md).</span><span class="sxs-lookup"><span data-stu-id="e1c96-126">See [Use sensitivity labels to protect content in Microsoft Teams, Office 365 groups, and SharePoint sites](../compliance/sensitivity-labels-teams-groups-sites.md) for details.</span></span>

<span data-ttu-id="e1c96-127">Если у вас уже есть метки чувствительности, развернутые в вашей организации, подумайте, как эта метка согласуется с вашей общей стратегией меток.</span><span class="sxs-lookup"><span data-stu-id="e1c96-127">If you already have sensitivity labels deployed in your organization, consider how this label fits with your overall label strategy.</span></span> <span data-ttu-id="e1c96-128">Вы можете изменить имя или настройки, если это необходимо для удовлетворения потребностей вашей организации.</span><span class="sxs-lookup"><span data-stu-id="e1c96-128">You can change the name or settings if needed to meet the needs of your organization.</span></span>

<span data-ttu-id="e1c96-129">После того, как вы включили метки чувствительности для Команд, следующим шагом будет создание метки.</span><span class="sxs-lookup"><span data-stu-id="e1c96-129">Once you have enabled sensitivity labels for Teams, the next step is to create the label.</span></span>

<span data-ttu-id="e1c96-130">Чтобы создать метку чувствительности</span><span class="sxs-lookup"><span data-stu-id="e1c96-130">To create a sensitivity label</span></span>
1. <span data-ttu-id="e1c96-131">Откройте [центр соответствия требованиям Microsoft 365](https://compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="e1c96-131">Open the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="e1c96-132">В разделе **Решения** нажмите **Защита информации**.</span><span class="sxs-lookup"><span data-stu-id="e1c96-132">Under **Solutions**, click **Information protection**.</span></span>
3. <span data-ttu-id="e1c96-133">Нажмите **Создать метку**.</span><span class="sxs-lookup"><span data-stu-id="e1c96-133">Click **Create a label**.</span></span>
4. <span data-ttu-id="e1c96-134">Дайте ярлыку имя.</span><span class="sxs-lookup"><span data-stu-id="e1c96-134">Give the label a name.</span></span> <span data-ttu-id="e1c96-135">Мы предлагаем вариант **Конфиденциально**, но вы можете выбрать другое имя, если оно уже используется.</span><span class="sxs-lookup"><span data-stu-id="e1c96-135">We suggest **Sensitive**, but you can choose a different name if that one is already in use.</span></span>
5. <span data-ttu-id="e1c96-136">Добавьте отображаемое имя и описание, а затем нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e1c96-136">Add a display name and description, and then click **Next**.</span></span>
6. <span data-ttu-id="e1c96-137">На странице **Определить область для этой метки** выберите **Файлы и электронные письма** и **Группы и сайты**, а затем нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e1c96-137">On the **Define the scope for this label page**, select **Files & emails** and **Groups & sites** and click **Next**.</span></span>
7. <span data-ttu-id="e1c96-138">На странице **Выберите параметры защиты файлов и сообщений электронной почты** нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e1c96-138">On the **Choose protection settings for files and emails** page, click **Next**.</span></span>
8. <span data-ttu-id="e1c96-139">На странице *Автоматическое применение меток для файлов и писем*\* нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e1c96-139">On the *Auto-labeling for files and emails*\* page, click **Next**.</span></span>
9. <span data-ttu-id="e1c96-140">На странице **Определение параметров защиты для групп и сайтов** выберите **Параметры конфиденциальности и доступа для внешних пользователей** и **Параметры доступа к устройствам и внешнего общего доступа**, а затем нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e1c96-140">On the **Define protection settings for groups and sites** page, select **Privacy and external user access settings** and **Device access and external sharing settings** and click **Next**.</span></span>
10. <span data-ttu-id="e1c96-141">На странице **Определение параметров конфиденциальности и доступа для внешних пользователей** в разделе **Конфиденциальность** выберите вариант **Частный**.</span><span class="sxs-lookup"><span data-stu-id="e1c96-141">On the **Define privacy and external user access settings** page, under **Privacy**, select the **Private** option.</span></span>
11. <span data-ttu-id="e1c96-142">Если вы хотите разрешить гостевой доступ, в разделе **Доступ внешних пользователей** выберите **Разрешить владельцам групп Microsoft 365 добавлять людей из-за пределов организации в группу в качестве гостей**.</span><span class="sxs-lookup"><span data-stu-id="e1c96-142">If you want to allow guest access, under **External user access**, select **Let Microsoft 365 Group owners add people outside your organization to the group as guests**.</span></span>
12. <span data-ttu-id="e1c96-143">Нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e1c96-143">Click **Next**.</span></span>
13. <span data-ttu-id="e1c96-144">На странице **Определение параметров доступа к устройствам и внешнего общего доступа** выберите **Управление внешним общим доступом с помеченных сайтов SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="e1c96-144">On the **Define external sharing and device access settings** page, select **Control external sharing from labeled SharePoint sites**.</span></span>
14. <span data-ttu-id="e1c96-145">В разделе **Доступ к контенту можно предоставить таким пользователям** выберите **Новые и существующие гости**, если вы разрешаете гостевой доступ, или **Только пользователи из вашей организации** (если не разрешаете гостевой доступ).</span><span class="sxs-lookup"><span data-stu-id="e1c96-145">Under **Content can be shared with**, choose **New and existing guests** if you're allowing guest access or **Only people in your organization** if not.</span></span>
15. <span data-ttu-id="e1c96-146">В разделе **Доступ с неуправляемых устройств** выберите **Разрешить только ограниченный веб-доступ**.</span><span class="sxs-lookup"><span data-stu-id="e1c96-146">Under **Access from unmanaged devices**, choose **Allow limited, web-only access**.</span></span>
16. <span data-ttu-id="e1c96-147">Нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e1c96-147">Click **Next**.</span></span>
17. <span data-ttu-id="e1c96-148">На странице **Автоматическое применение меток для столбцов базы данных** нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e1c96-148">On the **Auto-labeling for database columns** page, click **Next**.</span></span>
18. <span data-ttu-id="e1c96-149">Щелкните **Создать метку**, а затем нажмите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="e1c96-149">Click **Create label**, and then click **Done**.</span></span>

<span data-ttu-id="e1c96-150">После того как вы создали ярлык, вам нужно опубликовать его пользователям, которые будут его использовать.</span><span class="sxs-lookup"><span data-stu-id="e1c96-150">Once you've created the label, you need to publish it to the users who will use it.</span></span> <span data-ttu-id="e1c96-151">Для деликатной защиты мы сделаем ярлык доступным для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="e1c96-151">For sensitive protection, we'll make the label available to all users.</span></span> <span data-ttu-id="e1c96-152">Вы публикуете метку в Центре соответствия требованиям Microsoft 365 на вкладке **Политики меток** на странице **Защита информации**.</span><span class="sxs-lookup"><span data-stu-id="e1c96-152">You publish the label in the Microsoft 365 compliance center, on the **Label policies** tab of the **Information protection** page.</span></span> <span data-ttu-id="e1c96-153">Если у вас есть существующая политика, которая применяется ко всем пользователям, добавьте эту метку к этой политике.</span><span class="sxs-lookup"><span data-stu-id="e1c96-153">If you have an existing policy that applies to all users, add this label to that policy.</span></span> <span data-ttu-id="e1c96-154">Если вам нужно создать новую политику, см. [Публикация меток чувствительности путем создания политики меток](../compliance/create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy).</span><span class="sxs-lookup"><span data-stu-id="e1c96-154">If you need to create a new policy, see [Publish sensitivity labels by creating a label policy](../compliance/create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy).</span></span>

## <a name="create-a-team"></a><span data-ttu-id="e1c96-155">Создание команды</span><span class="sxs-lookup"><span data-stu-id="e1c96-155">Create a team</span></span>

<span data-ttu-id="e1c96-156">Дальнейшая настройка чувствительного сценария выполняется на сайте SharePoint, связанном с командой, поэтому следующим шагом является создание команды.</span><span class="sxs-lookup"><span data-stu-id="e1c96-156">Further configuration of the sensitive scenario is done in the SharePoint site associated with the team, so the next step is to create a team.</span></span>

<span data-ttu-id="e1c96-157">Создать группу для конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="e1c96-157">To create a team for sensitive information</span></span>
1. <span data-ttu-id="e1c96-158">В командах нажмите **Teams** в левой части приложения, затем нажмите **Присоединиться или создать группу** в нижней части списка команд.</span><span class="sxs-lookup"><span data-stu-id="e1c96-158">In Teams, click **Teams** on the left side of the app, then click **Join or create a team** at the bottom of the teams list.</span></span>
2. <span data-ttu-id="e1c96-159">Нажмите **Создать группу** (первая карта, верхний левый угол).</span><span class="sxs-lookup"><span data-stu-id="e1c96-159">Click **Create team** (first card, top left corner).</span></span>
3. <span data-ttu-id="e1c96-160">Выберите **Создать группу с нуля**.</span><span class="sxs-lookup"><span data-stu-id="e1c96-160">Choose **Build a team from scratch**.</span></span>
4. <span data-ttu-id="e1c96-161">В списке **Чувствительность** выберите **конфиденциальный** ярлык, который вы только что создали.</span><span class="sxs-lookup"><span data-stu-id="e1c96-161">In the **Sensitivity** list, choose the **sensitive** label that you just created.</span></span>
5. <span data-ttu-id="e1c96-162">В разделе **Конфиденциальность** нажмите **Приватный**.</span><span class="sxs-lookup"><span data-stu-id="e1c96-162">Under **Privacy**, click **Private**.</span></span>
6. <span data-ttu-id="e1c96-163">Введите имя для группы и нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="e1c96-163">Type a name for the team, and then click **Create**.</span></span>
7. <span data-ttu-id="e1c96-164">Добавьте пользователей в группу и нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="e1c96-164">Add users to the team, and then click **Close**.</span></span>

## <a name="private-channel-settings"></a><span data-ttu-id="e1c96-165">Настройки частного канала</span><span class="sxs-lookup"><span data-stu-id="e1c96-165">Private channel settings</span></span>

<span data-ttu-id="e1c96-166">На этом уровне мы ограничиваем создание частных каналов для владельцев команд.</span><span class="sxs-lookup"><span data-stu-id="e1c96-166">In this tier, we restrict creating private channels to team owners.</span></span>

<span data-ttu-id="e1c96-167">Ограничить создание частного канала</span><span class="sxs-lookup"><span data-stu-id="e1c96-167">To restrict private channel creation</span></span>
1. <span data-ttu-id="e1c96-168">В группе нажмите **Дополнительные параметры**, а затем нажмите **Управление группой**.</span><span class="sxs-lookup"><span data-stu-id="e1c96-168">In the team, click **More options**, and then click **Manage team**.</span></span>
2. <span data-ttu-id="e1c96-169">На вкладке **Настройки** разверните **Разрешения участников**.</span><span class="sxs-lookup"><span data-stu-id="e1c96-169">On the **Settings** tab, expand **Member permissions**.</span></span>
3. <span data-ttu-id="e1c96-170">Снимите флажок **Разрешить участникам создавать частные каналы**.</span><span class="sxs-lookup"><span data-stu-id="e1c96-170">Clear the **Allow members to create private channels** check box.</span></span>

<span data-ttu-id="e1c96-171">Вы также можете использовать [политики групп](/MicrosoftTeams/teams-policies), чтобы контролировать, кто может создавать частные каналы.</span><span class="sxs-lookup"><span data-stu-id="e1c96-171">You can also use [teams policies](/MicrosoftTeams/teams-policies) to control who can create private channels.</span></span>

## <a name="sharepoint-settings"></a><span data-ttu-id="e1c96-172">Параметры SharePoint</span><span class="sxs-lookup"><span data-stu-id="e1c96-172">SharePoint settings</span></span>

<span data-ttu-id="e1c96-173">Каждый раз, когда вы создаете новую команду с конфиденциальной меткой, в SharePoint нужно выполнить два шага:</span><span class="sxs-lookup"><span data-stu-id="e1c96-173">Each time you create a new team with the sensitive label, there are two steps to do in SharePoint:</span></span>

- <span data-ttu-id="e1c96-174">Измените параметры общего гостевого доступа для сайта в центре администрирования SharePoint, чтобы ссылка общего доступа по умолчанию реализовала вариант *Определенные пользователи*.</span><span class="sxs-lookup"><span data-stu-id="e1c96-174">Update the guest sharing settings for the site in the SharePoint admin center to update the default sharing link to *Specific people*.</span></span>
- <span data-ttu-id="e1c96-175">Обновите настройки общего доступа к сайту на самом сайте, чтобы пользователи не могли делиться сайтом.</span><span class="sxs-lookup"><span data-stu-id="e1c96-175">Update the site sharing settings in the site itself to prevent members from sharing the site.</span></span>

### <a name="site-default-sharing-link-settings"></a><span data-ttu-id="e1c96-176">Параметры ссылки общего доступа сайта по умолчанию</span><span class="sxs-lookup"><span data-stu-id="e1c96-176">Site default sharing link settings</span></span>

<span data-ttu-id="e1c96-177">Обновить тип ссылки общего доступа сайта по умолчанию</span><span class="sxs-lookup"><span data-stu-id="e1c96-177">To update the site default sharing link type</span></span>

1. <span data-ttu-id="e1c96-178">Откройте [центр администрирования SharePoint](https://admin.microsoft.com/sharepoint).</span><span class="sxs-lookup"><span data-stu-id="e1c96-178">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="e1c96-179">В разделе **Сайты** выберите **Активные сайты**.</span><span class="sxs-lookup"><span data-stu-id="e1c96-179">Under **Sites**, click **Active sites**.</span></span>
3. <span data-ttu-id="e1c96-180">Нажмите на сайт, который связан с командой.</span><span class="sxs-lookup"><span data-stu-id="e1c96-180">Click the site that is associated with team.</span></span>
4. <span data-ttu-id="e1c96-181">На вкладке **Политики** в разделе **Внешний обмен** нажмите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="e1c96-181">On the **Policies** tab, under **External sharing**, click **Edit**.</span></span>
5. <span data-ttu-id="e1c96-182">В разделе Тип ссылки для общего доступа по умолчанию снимите флажок **То же, что и на уровне организации** и выберите **Определенные люди (только те, кого пользователь указывает)**.</span><span class="sxs-lookup"><span data-stu-id="e1c96-182">Under Default sharing link type, clear the **Same as organization-level setting** check box, and select **Specific people (only the people the user specifies)**.</span></span>
6. <span data-ttu-id="e1c96-183">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="e1c96-183">Click **Save**.</span></span>

<span data-ttu-id="e1c96-184">Если вы хотите написать сценарий как часть процесса создания вашей команды, вы можете использовать [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) с параметром `-DefaultSharingLinkType Direct` для изменения типа ссылки общего доступа на *Определенные пользователи*.</span><span class="sxs-lookup"><span data-stu-id="e1c96-184">If you want to script this as part of your team creation process, you can use [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) with the `-DefaultSharingLinkType Direct` parameter to change the default sharing link to *Specific people*.</span></span>

#### <a name="private-channels"></a><span data-ttu-id="e1c96-185">Частные каналы</span><span class="sxs-lookup"><span data-stu-id="e1c96-185">Private channels</span></span>

<span data-ttu-id="e1c96-186">Если вы добавите частные каналы в группу, каждый частный канал создаст новый сайт SharePoint с настройками общего доступа по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e1c96-186">If you add private channels to the team, each private channel creates a new SharePoint site with the default sharing settings.</span></span> <span data-ttu-id="e1c96-187">Эти сайты не отображаются в центре администрирования SharePoint, поэтому необходимо использовать командлет Set-SPOSite PowerShell для обновления параметров общего доступа к гостям.</span><span class="sxs-lookup"><span data-stu-id="e1c96-187">These sites are not visible in the SharePoint admin center, so you must use the Set-SPOSite PowerShell cmdlet to update the guest sharing settings.</span></span>

### <a name="site-sharing-settings"></a><span data-ttu-id="e1c96-188">Настройки общего доступа к сайту</span><span class="sxs-lookup"><span data-stu-id="e1c96-188">Site sharing settings</span></span>

<span data-ttu-id="e1c96-189">Чтобы гарантировать, что сайт SharePoint не будет использоваться совместно с людьми, которые не являются членами команды, мы ограничиваем такой обмен для владельцев.</span><span class="sxs-lookup"><span data-stu-id="e1c96-189">To help ensure that the SharePoint site does not get shared with people who are not members of the team, we limit such sharing to owners.</span></span>

<span data-ttu-id="e1c96-190">Чтобы настроить общий доступ только для владельцев сайтов</span><span class="sxs-lookup"><span data-stu-id="e1c96-190">To configure owners-only site sharing</span></span>
1. <span data-ttu-id="e1c96-191">В Teams перейдите на вкладку **Общие** команды, которую вы хотите обновить.</span><span class="sxs-lookup"><span data-stu-id="e1c96-191">In Teams, navigate to the **General** tab of the team you want to update.</span></span>
2. <span data-ttu-id="e1c96-192">На панели инструментов для команды щелкните **Файлы**.</span><span class="sxs-lookup"><span data-stu-id="e1c96-192">In the tool bar for the team, click **Files**.</span></span>
3. <span data-ttu-id="e1c96-193">Щелкните многоточие, а затем — **Открыть в SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="e1c96-193">Click the ellipsis, and then click **Open in SharePoint**.</span></span>
4. <span data-ttu-id="e1c96-194">На панели инструментов базового сайта SharePoint щелкните значок параметров и выберите вариант **Разрешения для сайта**.</span><span class="sxs-lookup"><span data-stu-id="e1c96-194">In the tool bar of the underlying SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>
5. <span data-ttu-id="e1c96-195">На панели **разрешений сайта** в разделе **Общий доступ к сайту** нажмите кнопку **Изменить, как участники могут делиться**.</span><span class="sxs-lookup"><span data-stu-id="e1c96-195">In the **Site permissions** pane, under **Site sharing**, click **Change how members can share**.</span></span>
6. <span data-ttu-id="e1c96-196">В разделе **Разрешения общего доступа** выберите **Владельцы и участники сайта, и пользователи с правами «Редактировать» могут предоставлять общий доступ к файлам и папкам, но только владельцы сайта могут делиться сайтом**, а затем нажать **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="e1c96-196">Under **Sharing permissions**, choose **Site owners and members, and people with Edit permissions can share files and folders, but only site owners can share the site**, and then click **Save**.</span></span>


## <a name="see-also"></a><span data-ttu-id="e1c96-197">См. также</span><span class="sxs-lookup"><span data-stu-id="e1c96-197">See Also</span></span>

[<span data-ttu-id="e1c96-198">Создание и настройка меток конфиденциальности и соответствующих политик</span><span class="sxs-lookup"><span data-stu-id="e1c96-198">Create and configure sensitivity labels and their policies</span></span>](../compliance/create-sensitivity-labels.md)
