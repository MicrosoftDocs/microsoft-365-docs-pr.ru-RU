---
title: Обновление списков рассылки для Microsoft 365 групп в Outlook
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 787d7a75-e201-46f3-a242-f698162ff09f
description: Узнайте, как обновить один или несколько списков рассылки до Microsoft 365 групп в Outlook и как использовать PowerShell для обновления нескольких списков рассылки одновременно.
ms.openlocfilehash: d4686e7f2ec305194130b60fbacab24c9cf7f4e9
ms.sourcegitcommit: 4bcac4cb4f9399ebbd7c8cff0abb4d6ecedb731e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/28/2021
ms.locfileid: "52698944"
---
# <a name="upgrade-distribution-lists-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="20d55-103">Обновление списков рассылки для Microsoft 365 групп в Outlook</span><span class="sxs-lookup"><span data-stu-id="20d55-103">Upgrade distribution lists to Microsoft 365 Groups in Outlook</span></span>

<span data-ttu-id="20d55-104">Списки рассылки можно обновить до Microsoft 365 групп в Outlook.</span><span class="sxs-lookup"><span data-stu-id="20d55-104">You can upgrade distribution lists to Microsoft 365 Groups in Outlook.</span></span> <span data-ttu-id="20d55-105">Это отличный способ предоставить в списки рассылки организации все функции и функции Microsoft 365 Groups.</span><span class="sxs-lookup"><span data-stu-id="20d55-105">This is a great way to give your organization's distribution lists all the features and functionality of Microsoft 365 Groups.</span></span> [<span data-ttu-id="20d55-106">Причины для перехода со списков рассылки на группы в Outlook</span><span class="sxs-lookup"><span data-stu-id="20d55-106">Why you should upgrade your distribution lists to groups in Outlook</span></span>](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)

<span data-ttu-id="20d55-107">Вы можете обновить один или сразу несколько списков рассылки.</span><span class="sxs-lookup"><span data-stu-id="20d55-107">You can upgrade DLs one at a time, or several at the same time.</span></span>

## <a name="upgrade-one-or-many-distribution-list-groups-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="20d55-108">Обновление одной или многих групп списков рассылки для Microsoft 365 групп в Outlook</span><span class="sxs-lookup"><span data-stu-id="20d55-108">Upgrade one or many distribution list groups to Microsoft 365 Groups in Outlook</span></span>

<span data-ttu-id="20d55-109">Вы должны быть глобальным администратором или администратором Exchange для обновления группы списков рассылки.</span><span class="sxs-lookup"><span data-stu-id="20d55-109">You must be a global admin or Exchange admin to upgrade a distribution list group.</span></span> <span data-ttu-id="20d55-110">Чтобы обновить Microsoft 365 Группы, группа списков рассылки должна иметь владельца с почтовым ящиком.</span><span class="sxs-lookup"><span data-stu-id="20d55-110">To upgrade to Microsoft 365 Groups, the distribution list group must have an owner with a mailbox.</span></span>

### <a name="use-the-new-eac-to-upgrade-one-or-many-distribution-list-groups-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="20d55-111">Используйте новый EAC для обновления одной или многих групп списков рассылки для Microsoft 365 групп в Outlook</span><span class="sxs-lookup"><span data-stu-id="20d55-111">Use the new EAC to upgrade one or many distribution list groups to Microsoft 365 Groups in Outlook</span></span>

1. <span data-ttu-id="20d55-112">Перейдите в новый [центр администрирования Exchange](https://admin.exchange.microsoft.com)и перейдите в **группы** \> **получателей**.</span><span class="sxs-lookup"><span data-stu-id="20d55-112">Go to the new [Exchange admin center](https://admin.exchange.microsoft.com), and navigate to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="20d55-113">Выберите группу списка рассылки (также называемую группой рассылки), которую необходимо обновить до Microsoft 365 группы со страницы **Группы.**</span><span class="sxs-lookup"><span data-stu-id="20d55-113">Select the distribution list group (also called a **distribution group**) that you want to upgrade to Microsoft 365 group from the **Groups** page.</span></span>

3. <span data-ttu-id="20d55-114">Выберите **группу рассылки обновления из** панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="20d55-114">Select the **Upgrade distribution group** from the tool bar.</span></span>

4. <span data-ttu-id="20d55-115">В диалоговом окне **Готов к обновлению?,** нажмите **кнопку Обновление**.</span><span class="sxs-lookup"><span data-stu-id="20d55-115">In the dialog box **Ready to upgrade?**, click **Upgrade**.</span></span> <span data-ttu-id="20d55-116">Процесс начинается немедленно.</span><span class="sxs-lookup"><span data-stu-id="20d55-116">The process begins immediately.</span></span> <span data-ttu-id="20d55-117">В зависимости от размера и количества обновляемой группы списков рассылки процесс может занять несколько минут или часов.</span><span class="sxs-lookup"><span data-stu-id="20d55-117">Depending on the size and number of distribution list groups you're upgrading, the process can take minutes or hours.</span></span>

> [!NOTE]
> <span data-ttu-id="20d55-118">Баннер в верхней части указывает, что обновление, например, *группа рассылки (s) была обновлена. На отражение изменений ушло 5 минут. Фильтр по Microsoft 365 группы, чтобы увидеть обновленные группы distrubtion (s).*</span><span class="sxs-lookup"><span data-stu-id="20d55-118">A banner at the top indicates the upgrade, for example, *Distribution group(s) has been upgraded. It will take 5 minutes to reflect the changes. Filter by Microsoft 365 groups to see the upgraded distrubtion groups(s)*.</span></span>

### <a name="use-the-classic-eac-to-upgrade-one-or-many-distribution-list-groups-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="20d55-119">Используйте Классический центр EAC для обновления одной или многих групп списков рассылки для Microsoft 365 групп в Outlook</span><span class="sxs-lookup"><span data-stu-id="20d55-119">Use the Classic EAC to upgrade one or many distribution list groups to Microsoft 365 Groups in Outlook</span></span>

1. <span data-ttu-id="20d55-120">Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">центр администрирования Classic Exchange центра администрирования.</a></span><span class="sxs-lookup"><span data-stu-id="20d55-120">Go to the Classic <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="20d55-121">В центре администрирования Classic Exchange перейдите в **группы** \> **получателей.**</span><span class="sxs-lookup"><span data-stu-id="20d55-121">In the Classic Exchange admin center, go to **Recipients** \> **Groups**.</span></span><br/><span data-ttu-id="20d55-122">Вы увидите уведомление, указывающее на то, что у вас есть списки рассылки (также называемые группами рассылки), которые могут быть обновлены до Microsoft 365 Groups.</span><span class="sxs-lookup"><span data-stu-id="20d55-122">You'll see a notice indicating you have distribution lists (also called **distribution groups**) that are eligible to be upgraded to Microsoft 365 Groups.</span></span><br/> <span data-ttu-id="20d55-123">![Выберите кнопку Начало работы](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)</span><span class="sxs-lookup"><span data-stu-id="20d55-123">![Select the Get started button](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)</span></span>

3. <span data-ttu-id="20d55-124">Выберите один или несколько списков рассылки (также **называемых** группой рассылки) на странице **группы.**</span><span class="sxs-lookup"><span data-stu-id="20d55-124">Select one or more distribution lists (also called a **distribution group**) from the **groups** page.</span></span><br/><span data-ttu-id="20d55-125">![Выберите группу рассылки](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)</span><span class="sxs-lookup"><span data-stu-id="20d55-125">![Select a distribution group](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)</span></span>

4. <span data-ttu-id="20d55-126">Выберите значок обновления.</span><span class="sxs-lookup"><span data-stu-id="20d55-126">Select the upgrade icon.</span></span><br/>![Обновление до значка Microsoft 365 групп](../../media/1e28cb3d-bff3-4be3-8329-1902d2d54720.png)

5. <span data-ttu-id="20d55-128">В диалоговом окте "Да" выберите **"Да",** чтобы подтвердить обновление.</span><span class="sxs-lookup"><span data-stu-id="20d55-128">On the information dialog, select **Yes** to confirm the upgrade.</span></span> <span data-ttu-id="20d55-129">Процесс начинается немедленно.</span><span class="sxs-lookup"><span data-stu-id="20d55-129">The process begins immediately.</span></span> <span data-ttu-id="20d55-130">В зависимости от размера и количества обновляемого DLs процесс может занять несколько минут или часов.</span><span class="sxs-lookup"><span data-stu-id="20d55-130">Depending on the size and number of DLs you're upgrading, the process can take minutes or hours.</span></span><br/><span data-ttu-id="20d55-131">Если список рассылки не может быть обновлен, появится диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="20d55-131">If the distribution list can't be upgraded, a dialog appears saying so.</span></span> <span data-ttu-id="20d55-132">См. [список рассылки, которые нельзя обновить?](#which-distribution-lists-cant-be-upgraded).</span><span class="sxs-lookup"><span data-stu-id="20d55-132">See [Which distribution lists cannot be upgraded?](#which-distribution-lists-cant-be-upgraded).</span></span>

6. <span data-ttu-id="20d55-133">Если вы обновляете несколько списков рассылки, используйте выпадающий список для фильтрации списков рассылки, которые были обновлены.</span><span class="sxs-lookup"><span data-stu-id="20d55-133">If you're upgrading multiple distribution lists, use the drop-down list to filter which distribution lists have been upgraded.</span></span> <span data-ttu-id="20d55-134">Если список не завершен, подождите некоторое время, а затем выберите **Обновление,** чтобы узнать, что было успешно обновлено.</span><span class="sxs-lookup"><span data-stu-id="20d55-134">If the list isn't complete, wait a while longer and then select **Refresh** to see what's been successfully upgraded.</span></span><br/><span data-ttu-id="20d55-p107">Уведомление об окончании обновления для всех выбранных списков рассылки не выводится. То, какие списки были обновлены, можно узнать по разделам **Доступны для обновления** и **Обновленные списки рассылки**.</span><span class="sxs-lookup"><span data-stu-id="20d55-p107">There's no notice that tells you when the upgrade process has completed for all DLs you selected. You can figure this out by looking to see what's listed under **Available for upgrade** or **Upgraded DLs**.</span></span>

7. <span data-ttu-id="20d55-137">Если вы выбрали DL для обновления, но он по-прежнему появился на странице как Доступный для обновления, то обновление не удалось.</span><span class="sxs-lookup"><span data-stu-id="20d55-137">If you selected a DL for upgrade, but it's still appeared on the page as Available to upgrade, then it failed to upgrade.</span></span> <span data-ttu-id="20d55-138">Узнайте, что делать, если [обновление не работает.](#what-to-do-if-the-upgrade-doesnt-work)</span><span class="sxs-lookup"><span data-stu-id="20d55-138">See [What to do if the upgrade doesn't work](#what-to-do-if-the-upgrade-doesnt-work).</span></span>

> [!NOTE]
> <span data-ttu-id="20d55-p109">Если вы получаете письма с дайджестом сообщений группы, то могли заметить, что в них (в самом низу) иногда предлагается обновить списки рассылки, владельцем которых вы являетесь. Дополнительные сведения о письмах с дайджестом см. в статье [Групповые беседы в Outlook](https://support.microsoft.com/office/a0482e24-a769-4e39-a5ba-a7c56e828b22).</span><span class="sxs-lookup"><span data-stu-id="20d55-p109">If you're getting the groups digest emails you may notice at the bottom that it will sometimes offer to let you upgrade any eligible distribution lists that you're the owner of. See [Have a group conversation in Outlook](https://support.microsoft.com/office/a0482e24-a769-4e39-a5ba-a7c56e828b22) for more information about digest emails.</span></span>

## <a name="what-to-do-if-the-upgrade-doesnt-work"></a><span data-ttu-id="20d55-141">Что делать, если возникает ошибка обновления</span><span class="sxs-lookup"><span data-stu-id="20d55-141">What to do if the upgrade doesn't work</span></span>

<span data-ttu-id="20d55-142">Списки рассылки, которые не удалось обновить, остаются без изменений.</span><span class="sxs-lookup"><span data-stu-id="20d55-142">Distribution lists that fail to upgrade remain unchanged.</span></span>

<span data-ttu-id="20d55-p110">Если не удалось обновить **поддерживаемый** список рассылки, отправьте [запрос в службу поддержки](../../business-video/get-help-support.md). Об этой проблеме необходимо сообщить команде технических специалистов по Группам.</span><span class="sxs-lookup"><span data-stu-id="20d55-p110">If one or more **eligible** distribution lists fail to be upgraded, open a [Support ticket](../../business-video/get-help-support.md). The issue will need to be escalated to the Groups Engineering team for them to figure out the problem.</span></span>

<span data-ttu-id="20d55-145">Вполне возможно, что список рассылки не был обновлен из-за простоя службы, но маловероятно.</span><span class="sxs-lookup"><span data-stu-id="20d55-145">It's possible that the distribution list didn't get upgraded because of a service outage, but unlikely.</span></span> <span data-ttu-id="20d55-146">Попробуйте подождать немного и повторить попытку.</span><span class="sxs-lookup"><span data-stu-id="20d55-146">If you want, wait a while and then try to upgrade the DL again.</span></span>

## <a name="how-to-use-powershell-to-upgrade-several-distribution-lists-at-the-same-time"></a><span data-ttu-id="20d55-147">Обновление нескольких списков рассылки одновременно с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="20d55-147">How to use PowerShell to upgrade several distribution lists at the same time</span></span>

<span data-ttu-id="20d55-148">Если вы хорошо знакомы с PowerShell, можно воспользоваться этим средством вместо пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="20d55-148">If you're experienced at using PowerShell, you might want to go this route instead of using the UI.</span></span> <span data-ttu-id="20d55-149">У нас есть набор cmdlets, которые помогут вам обновить списки рассылки.</span><span class="sxs-lookup"><span data-stu-id="20d55-149">We have a set of cmdlets that will help you upgrade distribution lists.</span></span> <span data-ttu-id="20d55-150">См. ниже.</span><span class="sxs-lookup"><span data-stu-id="20d55-150">See below.</span></span>

### <a name="upgrade-a-single-dl"></a><span data-ttu-id="20d55-151">Обновление единого DL</span><span class="sxs-lookup"><span data-stu-id="20d55-151">Upgrade a single DL</span></span>

<span data-ttu-id="20d55-152">Чтобы обновить один DL, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="20d55-152">To upgrade a single DL, run the following command:</span></span>

```PowerShell
Upgrade-DistributionGroup -DlIdentities <Dl SMTP address>
```

<span data-ttu-id="20d55-153">Например, если вы хотите обновить DL с помощью smTP-dl1@contoso.com, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="20d55-153">For example, if you want to upgrade a DL with SMTP address dl1@contoso.com, run the following command:</span></span>

```PowerShell
Upgrade-DistributionGroup -DlIdentities dl1@contoso.com
```

> [!NOTE]
> <span data-ttu-id="20d55-154">Можно также обновить единый список рассылки до группы Microsoft 365 с помощью комлета [New-UnifiedGroup](/powershell/module/exchange/new-unifiedgroup) PowerShell</span><span class="sxs-lookup"><span data-stu-id="20d55-154">You can also upgrade a single distribution list to a Microsoft 365 group using the [New-UnifiedGroup](/powershell/module/exchange/new-unifiedgroup) PowerShell cmdlet</span></span>

### <a name="upgrade-multiple-dls-in-a-batch"></a><span data-ttu-id="20d55-155">Обновление нескольких DLs в пакете</span><span class="sxs-lookup"><span data-stu-id="20d55-155">Upgrade multiple DLs in a batch</span></span>

<span data-ttu-id="20d55-156">Вы также можете передать несколько DLs в качестве пакета и обновить их вместе:</span><span class="sxs-lookup"><span data-stu-id="20d55-156">You can also pass multiple DLs as a batch and upgrade them together:</span></span>

```PowerShell
Upgrade-DistributionGroup -DlIdentities <DL SMTP address1>, <DL SMTP address2>,
<DL SMTP address3>, <DL SMTP address4>
```

<span data-ttu-id="20d55-157">Например, если вы хотите обновить пять DLs с smTP-адресом и `dl1@contoso.com` `dl2@contoso.com` , `dl3@contoso.com` `dl4@contoso.com` `dl5@contoso.com` и, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="20d55-157">For example, if you want to upgrade five DLs with SMTP address `dl1@contoso.com` and `dl2@contoso.com`, `dl3@contoso.com`, `dl4@contoso.com` and `dl5@contoso.com`, run the following command:</span></span>

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com, dl2@contoso.com, dl3@contoso.com, dl4@contoso.com, dl5@contoso.com`

### <a name="upgrade-all-eligible-dls"></a><span data-ttu-id="20d55-158">Обновление всех подходящих DLs</span><span class="sxs-lookup"><span data-stu-id="20d55-158">Upgrade all eligible DLs</span></span>

<span data-ttu-id="20d55-159">Существует два способа обновления всех подходящих DLs.</span><span class="sxs-lookup"><span data-stu-id="20d55-159">There are two ways in which you can upgrade all the eligible DLs.</span></span>

> [!NOTE]
> <span data-ttu-id="20d55-160">Этот Upgrade-DistributionGroup не получает данные из конвейера, поэтому для успешного запуска необходимо использовать оператора "foreach-object". {}</span><span class="sxs-lookup"><span data-stu-id="20d55-160">The Upgrade-DistributionGroup cmdlet doesn't receive data from the pipeline, for this reason it's required to use "foreach-object{}" operator to run successfully.</span></span>

1. <span data-ttu-id="20d55-161">Получите подходящие DLs в клиенте и обновите их с помощью команды обновления:</span><span class="sxs-lookup"><span data-stu-id="20d55-161">Get the eligible DLs in the tenant and upgrade them using the upgrade command:</span></span>

```PowerShell
Get-EligibleDistributionGroupForMigration | Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

2. <span data-ttu-id="20d55-162">Получите список всех DLs и обновим только подходящие DLs:</span><span class="sxs-lookup"><span data-stu-id="20d55-162">Get the list of all DLs and upgrade only the eligible DLs:</span></span>

```PowerShell
Get-DistributionGroup| Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

## <a name="faq-about-upgrading-distribution-lists-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="20d55-163">FaQ об обновлении списков рассылки до Microsoft 365 групп в Outlook</span><span class="sxs-lookup"><span data-stu-id="20d55-163">FAQ about upgrading distribution lists to Microsoft 365 Groups in Outlook</span></span>

### <a name="which-distribution-lists-cant-be-upgraded"></a><span data-ttu-id="20d55-164">Какие списки рассылки нельзя обновить?</span><span class="sxs-lookup"><span data-stu-id="20d55-164">Which distribution lists can't be upgraded?</span></span>

<span data-ttu-id="20d55-165">Обновлять можно только простые облачные списки рассылки, не являющиеся вложенными.</span><span class="sxs-lookup"><span data-stu-id="20d55-165">You can only upgrade cloud-managed, simple, non-nested distribution lists.</span></span> <span data-ttu-id="20d55-166">В таблице ниже перечислены списки **рассылки, которые невозможно** обновить.</span><span class="sxs-lookup"><span data-stu-id="20d55-166">The table below lists distribution lists that **CANNOT** be upgraded.</span></span>

|<span data-ttu-id="20d55-167">**Описание**</span><span class="sxs-lookup"><span data-stu-id="20d55-167">**Property**</span></span>|<span data-ttu-id="20d55-168">**Поддерживается?**</span><span class="sxs-lookup"><span data-stu-id="20d55-168">**Eligible?**</span></span>|
|:-----|:-----|
|<span data-ttu-id="20d55-169">Список рассылки с локальным управлением.</span><span class="sxs-lookup"><span data-stu-id="20d55-169">On-premises managed distribution list.</span></span>  <br/> |<span data-ttu-id="20d55-170">Нет</span><span class="sxs-lookup"><span data-stu-id="20d55-170">No</span></span>  <br/> |
|<span data-ttu-id="20d55-p114">Вложенные списки рассылки. Список рассылки имеет дочерние группы или входит в другую группу.</span><span class="sxs-lookup"><span data-stu-id="20d55-p114">Nested distribution lists. Distribution list either has child groups or is a member of another group.</span></span>  <br/> |<span data-ttu-id="20d55-173">Нет</span><span class="sxs-lookup"><span data-stu-id="20d55-173">No</span></span>  <br/> |
|<span data-ttu-id="20d55-174">Списки рассылки **с получателями memberTypeDetails,** кроме **UserMailbox,** **SharedMailbox,** **TeamMailbox,** **MailUser**</span><span class="sxs-lookup"><span data-stu-id="20d55-174">Distribution lists with member **RecipientTypeDetails** other than **UserMailbox**, **SharedMailbox**, **TeamMailbox**, **MailUser**</span></span>  <br/> |<span data-ttu-id="20d55-175">Нет</span><span class="sxs-lookup"><span data-stu-id="20d55-175">No</span></span>  <br/> |
|<span data-ttu-id="20d55-176">Список рассылки с более чем 100 владельцами</span><span class="sxs-lookup"><span data-stu-id="20d55-176">Distribution list that has more than 100 owners</span></span>  <br/> |<span data-ttu-id="20d55-177">Нет</span><span class="sxs-lookup"><span data-stu-id="20d55-177">No</span></span>  <br/> |
|<span data-ttu-id="20d55-178">Список рассылки, который имеет только членов, но не владельца</span><span class="sxs-lookup"><span data-stu-id="20d55-178">Distribution list that only has members but no owner</span></span>  <br/> |<span data-ttu-id="20d55-179">Нет</span><span class="sxs-lookup"><span data-stu-id="20d55-179">No</span></span>  <br/> |
|<span data-ttu-id="20d55-180">Список рассылки с псевдонимом, содержащим специальные символы</span><span class="sxs-lookup"><span data-stu-id="20d55-180">Distribution list that has alias containing special characters</span></span>  <br/> |<span data-ttu-id="20d55-181">Нет</span><span class="sxs-lookup"><span data-stu-id="20d55-181">No</span></span>  <br/> |
|<span data-ttu-id="20d55-182">Список рассылки, настроенный в качестве адреса перенаправления для общего почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="20d55-182">If the distribution list is configured to be a forwarding address for Shared Mailbox</span></span>  <br/> |<span data-ttu-id="20d55-183">Нет</span><span class="sxs-lookup"><span data-stu-id="20d55-183">No</span></span>  <br/> |
|<span data-ttu-id="20d55-184">Если DL является частью **ограничения отправитель в** другом DL.</span><span class="sxs-lookup"><span data-stu-id="20d55-184">If the DL is part of **Sender Restriction** in another DL.</span></span>  <br/> |<span data-ttu-id="20d55-185">Нет</span><span class="sxs-lookup"><span data-stu-id="20d55-185">No</span></span>  <br/> |
|<span data-ttu-id="20d55-186">Группы безопасности</span><span class="sxs-lookup"><span data-stu-id="20d55-186">Security groups</span></span>  <br/> |<span data-ttu-id="20d55-187">Нет</span><span class="sxs-lookup"><span data-stu-id="20d55-187">No</span></span>  <br/> |
|<span data-ttu-id="20d55-188">Динамические списки рассылки.</span><span class="sxs-lookup"><span data-stu-id="20d55-188">Dynamic Distribution lists</span></span>  <br/> |<span data-ttu-id="20d55-189">Нет</span><span class="sxs-lookup"><span data-stu-id="20d55-189">No</span></span>  <br/> |
|<span data-ttu-id="20d55-190">Списки рассылки, преобразованные в **RoomLists**</span><span class="sxs-lookup"><span data-stu-id="20d55-190">Distribution lists that were converted to **RoomLists**</span></span>  <br/> |<span data-ttu-id="20d55-191">Нет</span><span class="sxs-lookup"><span data-stu-id="20d55-191">No</span></span>  <br/> |
|<span data-ttu-id="20d55-192">Списки рассылки, в которых **закрывается MemberJoinRestriction** и/или **MemberDepartRestriction** </span><span class="sxs-lookup"><span data-stu-id="20d55-192">Distribution lists where **MemberJoinRestriction** and/or **MemberDepartRestriction** is **Closed**</span></span>  <br/> |<span data-ttu-id="20d55-193">Нет</span><span class="sxs-lookup"><span data-stu-id="20d55-193">No</span></span>  <br/> |

### <a name="check-which-dls-are-eligible-for-upgrade"></a><span data-ttu-id="20d55-194">Проверьте, какие DLs имеют право на обновление</span><span class="sxs-lookup"><span data-stu-id="20d55-194">Check which DLs are eligible for upgrade</span></span>

<span data-ttu-id="20d55-195">Если вы хотите проверить, имеет ли DL право или нет, вы можете выполнить приведенную ниже команду:</span><span class="sxs-lookup"><span data-stu-id="20d55-195">If you want to check whether a DL is eligible or not, you can run the below command:</span></span>

`Get-DistributionGroup <DL SMTP address> | Get-EligibleDistributionGroupForMigration`

<span data-ttu-id="20d55-196">Если вы хотите проверить, какие DLs имеют право на обновление, просто запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="20d55-196">If you want to check which DLs are eligible for upgrade just run the following command:</span></span>

`Get-EligibleDistributionGroupForMigration`

### <a name="who-can-run-the-upgrade-scripts"></a><span data-ttu-id="20d55-197">Кто может выполнять сценарии обновления?</span><span class="sxs-lookup"><span data-stu-id="20d55-197">Who can run the upgrade scripts?</span></span>

<span data-ttu-id="20d55-198">Люди с глобальными правами администратора или Exchange администратора.</span><span class="sxs-lookup"><span data-stu-id="20d55-198">People with global admin or Exchange admin rights.</span></span>

### <a name="why-is-the-contact-card-still-showing-a-distribution-list-what-should-i-do-to-prevent-an-upgraded-distribution-list-from-showing-up-in-my-auto-suggest-list"></a><span data-ttu-id="20d55-199">Почему карточка контакта по-прежнему отображается в списке рассылки?</span><span class="sxs-lookup"><span data-stu-id="20d55-199">Why is the contact card still showing a distribution list?</span></span> <span data-ttu-id="20d55-200">Что нужно сделать, чтобы обновленный список рассылки не появлялся в списке автоматической рассылки?</span><span class="sxs-lookup"><span data-stu-id="20d55-200">What should I do to prevent an upgraded distribution list from showing up in my auto suggest list?</span></span>

- <span data-ttu-id="20d55-201">Для Outlook. Если кто-то пытается отправить сообщение в Outlook, введя имя группы Microsoft 365 после миграции, получатель будет решен в качестве списка рассылки, а не группы.</span><span class="sxs-lookup"><span data-stu-id="20d55-201">For Outlook: When someone tries to send an email in Outlook by typing the Microsoft 365 group name after migration, the recipient will be resolved as the distribution list instead of the group.</span></span> <span data-ttu-id="20d55-202">Карточка контакта этого получателя останется в списке рассылки.</span><span class="sxs-lookup"><span data-stu-id="20d55-202">The contact card of the recipient will be the distribution lists contact card.</span></span> <span data-ttu-id="20d55-203">Это связано с кэшем получателей или кэшем псевдонимов в Outlook.</span><span class="sxs-lookup"><span data-stu-id="20d55-203">This is because of the recipient cache or nick name cache in Outlook.</span></span> <span data-ttu-id="20d55-204">Сообщение будет успешно отправлено в группу, но может вызвать путаницу в отправитель.</span><span class="sxs-lookup"><span data-stu-id="20d55-204">The email will be sent successfully to the group, but might cause confusion to the sender.</span></span><br/><span data-ttu-id="20d55-205">Вы можете выполнить шаги в этой статье, сведения о списке Outlook [AutoComplete](/outlook/troubleshoot/contacts/information-about-the-outlook-autocomplete-list) для сброса кэша, который исправит эту проблему.</span><span class="sxs-lookup"><span data-stu-id="20d55-205">You can perform the steps in this article, [Information about the Outlook AutoComplete list](/outlook/troubleshoot/contacts/information-about-the-outlook-autocomplete-list) to reset the cache, which will fix this issue.</span></span>

- <span data-ttu-id="20d55-206">Для Outlook в Интернете: в случае Outlook в Интернете получатель списка рассылки по-прежнему будет оставаться в кэше.</span><span class="sxs-lookup"><span data-stu-id="20d55-206">For Outlook on the web: In case of Outlook on the web, the distribution list recipient will still remain in the cache.</span></span> <span data-ttu-id="20d55-207">Чтобы обновить кэш, можно выполнить действия в ["Удалить](https://support.microsoft.com/office/9E1419D9-E88F-445B-B07F-F558B8A37C58) предложенное имя или адрес электронной почты из списка автозаполнений", чтобы увидеть контактную карточку группы.</span><span class="sxs-lookup"><span data-stu-id="20d55-207">You can follow the steps in [Remove suggested name or email address from the Auto-Complete List](https://support.microsoft.com/office/9E1419D9-E88F-445B-B07F-F558B8A37C58) to refresh the cache to see the group contact card.</span></span>

### <a name="do-new-group-members-get-a-welcome-email-in-their-inbox"></a><span data-ttu-id="20d55-208">Получат ли участники группы приветственные сообщения?</span><span class="sxs-lookup"><span data-stu-id="20d55-208">Do new group members get a welcome email in their inbox?</span></span>

<span data-ttu-id="20d55-p118">Нет. По умолчанию параметру, который отвечает за отправку таких сообщений, присвоено значение false. Этот параметр относится как к существующим, так и к новым участникам группы, которые могут присоединиться к ней после переноса. Если владелец группы разрешит гостевым пользователям присоединяться к ней, они не будут получать приветственные сообщения. Несмотря на это они смогут использовать группу.</span><span class="sxs-lookup"><span data-stu-id="20d55-p118">No. The setting to enable welcome messages is set to false by default. This setting affects both existing and new group members who may join after the migration is complete. If the group owner later allows guest users, guest users won't receive a welcome email in their inbox. Guest members can continue working with the group.</span></span>

### <a name="what-if-one-or-some-of-the-dls-are-not-upgraded"></a><span data-ttu-id="20d55-214">Что делать, если один или несколько DLs не обновлены?</span><span class="sxs-lookup"><span data-stu-id="20d55-214">What if one or some of the DLs are not upgraded?</span></span>

<span data-ttu-id="20d55-215">Есть несколько случаев, когда, хотя DL имеет право, но не может быть обновлен.</span><span class="sxs-lookup"><span data-stu-id="20d55-215">There are some cases in which though DL is eligible but could not be upgraded.</span></span> <span data-ttu-id="20d55-216">DL не обновляется и остается как DL.</span><span class="sxs-lookup"><span data-stu-id="20d55-216">The DL does not get upgraded and remains as a DL.</span></span>

- <span data-ttu-id="20d55-217">Если администратор применял политику адресов групповой электронной почты для групп в организации и они пытаются обновить DLs, которые не соответствуют критериям, DL не обновляется. </span><span class="sxs-lookup"><span data-stu-id="20d55-217">Where admin has applied **Group Email Address Policy** for the groups in an organization and they try to upgrade DLs that doesn't fulfill the criteria, the DL does not get upgraded</span></span>

- <span data-ttu-id="20d55-218">DLs с **набором memberJoinRestriction** или **MemberDepartRestriction,** задаваемой **в закрытом** режиме, не удалось обновить</span><span class="sxs-lookup"><span data-stu-id="20d55-218">DLs with **MemberJoinRestriction** or **MemberDepartRestriction** set to **Closed**, could not be upgraded</span></span>

### <a name="what-happens-to-the-dl-if-the-upgrade-from-eac-fails"></a><span data-ttu-id="20d55-219">Что происходит со списком рассылки при сбое обновления, запущенного через EAC?</span><span class="sxs-lookup"><span data-stu-id="20d55-219">What happens to the DL if the upgrade from EAC fails?</span></span>

<span data-ttu-id="20d55-p120">Обновление происходит только после отправки вызова на сервер. Если обновление завершится сбоем, список рассылки не будет изменен. Он будет работать, как прежде.</span><span class="sxs-lookup"><span data-stu-id="20d55-p120">The upgrade will happen only when the call is submitted to the server. If the upgrade fails, your DLs will be intact. They will work like they used to.</span></span>

## <a name="related-content"></a><span data-ttu-id="20d55-223">Связанные материалы</span><span class="sxs-lookup"><span data-stu-id="20d55-223">Related content</span></span>

<span data-ttu-id="20d55-224">[Сравнение групп](../create-groups/compare-groups.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="20d55-224">[Compare groups](../create-groups/compare-groups.md) (article)</span></span>\
<span data-ttu-id="20d55-225">[Объяснение групп Microsoft 365 пользователям](../create-groups/explain-groups-knowledge-worker.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="20d55-225">[Explaining Microsoft 365 Groups to your users](../create-groups/explain-groups-knowledge-worker.md) (article)</span></span>\
[<span data-ttu-id="20d55-226">Добавление или удаление участников из Microsoft 365 групп с помощью центра администрирования</span><span class="sxs-lookup"><span data-stu-id="20d55-226">Add or remove members from Microsoft 365 groups using the admin center</span></span>](../create-groups/add-or-remove-members-from-groups.md)
