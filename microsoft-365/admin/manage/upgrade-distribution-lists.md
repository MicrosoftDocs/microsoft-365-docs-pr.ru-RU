---
title: Обновление списков рассылки до Групп Microsoft 365 в Outlook
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
description: Узнайте, как обновить один или несколько списков рассылки до Microsoft 365 Groups в Outlook и как использовать PowerShell для одновременного обновления нескольких списков рассылки.
ms.openlocfilehash: ab7c2ff68b1f16915d65fff0d7292e3b3ad72d02
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579246"
---
# <a name="upgrade-distribution-lists-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="ad12d-103">Обновление списков рассылки до Групп Microsoft 365 в Outlook</span><span class="sxs-lookup"><span data-stu-id="ad12d-103">Upgrade distribution lists to Microsoft 365 Groups in Outlook</span></span>

<span data-ttu-id="ad12d-104">Списки рассылки можно обновить до Microsoft 365 Groups с помощью Outlook.</span><span class="sxs-lookup"><span data-stu-id="ad12d-104">You can upgrade distribution lists to Microsoft 365 Groups with Outlook.</span></span> <span data-ttu-id="ad12d-105">Это отличный способ предоставить в списки рассылки организации все функции и функции Microsoft 365 Groups.</span><span class="sxs-lookup"><span data-stu-id="ad12d-105">This is a great way to give your organization's distribution lists all the features and functionality of Microsoft 365 Groups.</span></span> [<span data-ttu-id="ad12d-106">Причины для перехода со списков рассылки на группы в Outlook</span><span class="sxs-lookup"><span data-stu-id="ad12d-106">Why you should upgrade your distribution lists to groups in Outlook</span></span>](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)

<span data-ttu-id="ad12d-107">Вы можете обновить один или сразу несколько списков рассылки.</span><span class="sxs-lookup"><span data-stu-id="ad12d-107">You can upgrade DLs one at a time, or several at the same time.</span></span>

## <a name="upgrade-one-or-many-distribution-lists-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="ad12d-108">Обновление одного или многих списков рассылки до Групп Microsoft 365 в Outlook</span><span class="sxs-lookup"><span data-stu-id="ad12d-108">Upgrade one or many distribution lists to Microsoft 365 Groups in Outlook</span></span>

<span data-ttu-id="ad12d-109">Чтобы обновить список рассылки, необходимо быть глобальным администратором или администратором Exchange.</span><span class="sxs-lookup"><span data-stu-id="ad12d-109">You must be a global admin or Exchange admin to upgrade a distribution list.</span></span> <span data-ttu-id="ad12d-110">Чтобы перейти на Microsoft 365 Groups, группа рассылки должна иметь владельца с почтовым ящиком.</span><span class="sxs-lookup"><span data-stu-id="ad12d-110">To upgrade to Microsoft 365 Groups, a distribution group must have an owner with a mailbox.</span></span>

1. <span data-ttu-id="ad12d-111">Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Центр администрирования Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="ad12d-111">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="ad12d-112">В центре администрирования Exchange перейдите в **группы** \> **получателей.**</span><span class="sxs-lookup"><span data-stu-id="ad12d-112">In the Exchange admin center, go to **Recipients** \> **Groups**.</span></span><br/><span data-ttu-id="ad12d-113">Вы увидите уведомление, указывающее на  то, что у вас есть списки рассылки (также называемые группами рассылки), которые могут быть обновлены до Microsoft 365 Groups.</span><span class="sxs-lookup"><span data-stu-id="ad12d-113">You'll see a notice indicating you have distribution lists (also called **distribution groups** ) that are eligible to be upgraded to Microsoft 365 Groups.</span></span><br/> <span data-ttu-id="ad12d-114">![Выберите кнопку Начало работы](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)</span><span class="sxs-lookup"><span data-stu-id="ad12d-114">![Select the Get started button](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)</span></span>

3. <span data-ttu-id="ad12d-115">Выберите один или несколько списков рассылки ( **групп рассылки** ) на странице **групп**.</span><span class="sxs-lookup"><span data-stu-id="ad12d-115">Select one or more distribution lists (also called a **distribution group** ) from the **groups** page.</span></span><br/><span data-ttu-id="ad12d-116">![Выберите группу рассылки](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)</span><span class="sxs-lookup"><span data-stu-id="ad12d-116">![Select a distribution group](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)</span></span>

4. <span data-ttu-id="ad12d-117">Выберите значок обновления.</span><span class="sxs-lookup"><span data-stu-id="ad12d-117">Select the upgrade icon.</span></span><br/>![Обновление до значка Microsoft 365 Groups](../../media/1e28cb3d-bff3-4be3-8329-1902d2d54720.png)

5. <span data-ttu-id="ad12d-119">В диалоговом окте "Да" выберите **"Да",** чтобы подтвердить обновление.</span><span class="sxs-lookup"><span data-stu-id="ad12d-119">On the information dialog, select **Yes** to confirm the upgrade.</span></span> <span data-ttu-id="ad12d-120">Процесс начинается немедленно.</span><span class="sxs-lookup"><span data-stu-id="ad12d-120">The process begins immediately.</span></span> <span data-ttu-id="ad12d-121">В зависимости от размера и количества обновляемого DLs процесс может занять несколько минут или часов.</span><span class="sxs-lookup"><span data-stu-id="ad12d-121">Depending on the size and number of DLs you're upgrading, the process can take minutes or hours.</span></span><br/><span data-ttu-id="ad12d-122">Если список рассылки не может быть обновлен, появится диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="ad12d-122">If the distribution list can't be upgraded, a dialog appears saying so.</span></span> <span data-ttu-id="ad12d-123">См. [список рассылки, которые нельзя обновить?](#which-distribution-lists-cant-be-upgraded).</span><span class="sxs-lookup"><span data-stu-id="ad12d-123">See [Which distribution lists cannot be upgraded?](#which-distribution-lists-cant-be-upgraded).</span></span>

6. <span data-ttu-id="ad12d-124">Если вы обновляете несколько списков рассылки, используйте выпадающий список для фильтрации списков рассылки, которые были обновлены.</span><span class="sxs-lookup"><span data-stu-id="ad12d-124">If you're upgrading multiple distribution lists, use the drop-down list to filter which distribution lists have been upgraded.</span></span> <span data-ttu-id="ad12d-125">Если список не завершен, подождите некоторое время, а затем выберите **Обновление,** чтобы узнать, что было успешно обновлено.</span><span class="sxs-lookup"><span data-stu-id="ad12d-125">If the list isn't complete, wait a while longer and then select **Refresh** to see what's been successfully upgraded.</span></span><br/><span data-ttu-id="ad12d-p106">Уведомление об окончании обновления для всех выбранных списков рассылки не выводится. То, какие списки были обновлены, можно узнать по разделам **Доступны для обновления** и **Обновленные списки рассылки**.</span><span class="sxs-lookup"><span data-stu-id="ad12d-p106">There's no notice that tells you when the upgrade process has completed for all DLs you selected. You can figure this out by looking to see what's listed under **Available for upgrade** or **Upgraded DLs**.</span></span>

7. <span data-ttu-id="ad12d-p107">Если вы выбрали список рассылки для обновления, но оно по-прежнему отображается на странице "Доступны для обновления", его не удалось обновить. См. раздел [Что делать, если возникает ошибка обновления](#what-to-do-if-the-upgrade-doesnt-work).</span><span class="sxs-lookup"><span data-stu-id="ad12d-p107">If you selected a DL for upgrade, but it's still appears on the page as Available to upgrade, then it failed to upgrade. See [What to do if the upgrade doesn't work](#what-to-do-if-the-upgrade-doesnt-work).</span></span>

> [!NOTE]
> <span data-ttu-id="ad12d-p108">Если вы получаете письма с дайджестом сообщений группы, то могли заметить, что в них (в самом низу) иногда предлагается обновить списки рассылки, владельцем которых вы являетесь. Дополнительные сведения о письмах с дайджестом см. в статье [Групповые беседы в Outlook](https://support.microsoft.com/office/a0482e24-a769-4e39-a5ba-a7c56e828b22).</span><span class="sxs-lookup"><span data-stu-id="ad12d-p108">If you're getting the groups digest emails you may notice at the bottom that it will sometimes offer to let you upgrade any eligible distribution lists that you're the owner of. See [Have a group conversation in Outlook](https://support.microsoft.com/office/a0482e24-a769-4e39-a5ba-a7c56e828b22) for more information about digest emails.</span></span>

## <a name="what-to-do-if-the-upgrade-doesnt-work"></a><span data-ttu-id="ad12d-132">Что делать, если возникает ошибка обновления</span><span class="sxs-lookup"><span data-stu-id="ad12d-132">What to do if the upgrade doesn't work</span></span>

<span data-ttu-id="ad12d-133">Списки рассылки, которые не удалось обновить, остаются без изменений.</span><span class="sxs-lookup"><span data-stu-id="ad12d-133">Distribution lists that fail to upgrade remain unchanged.</span></span>

<span data-ttu-id="ad12d-p109">Если не удалось обновить **поддерживаемый** список рассылки, отправьте [запрос в службу поддержки](../contact-support-for-business-products.md). Об этой проблеме необходимо сообщить команде технических специалистов по Группам.</span><span class="sxs-lookup"><span data-stu-id="ad12d-p109">If one or more **eligible** distribution lists fail to be upgraded, open a [Support ticket](../contact-support-for-business-products.md). The issue will need to be escalated to the Groups Engineering team for them to figure out the problem.</span></span>

<span data-ttu-id="ad12d-p110">Возможно, список рассылки не удалось обновить из-за сбоя службы, но такое случается довольно редко. Попробуйте подождать немного и повторить попытку.</span><span class="sxs-lookup"><span data-stu-id="ad12d-p110">It's possible that the distribution list didn't get upgraded because of a service outage, but pretty unlikely. If you want, wait a while and then try to upgrade the DL again.</span></span>

## <a name="how-to-use-powershell-to-upgrade-several-distribution-lists-at-the-same-time"></a><span data-ttu-id="ad12d-138">Обновление нескольких списков рассылки одновременно с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="ad12d-138">How to use PowerShell to upgrade several distribution lists at the same time</span></span>

<span data-ttu-id="ad12d-139">Если вы хорошо знакомы с PowerShell, можно воспользоваться этим средством вместо пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="ad12d-139">If you're experienced at using PowerShell, you might want to go this route instead of using the UI.</span></span> <span data-ttu-id="ad12d-140">У нас есть набор cmdlets, которые помогут вам обновить списки рассылки.</span><span class="sxs-lookup"><span data-stu-id="ad12d-140">We have a set of cmdlets that will help you upgrade distribution lists.</span></span> <span data-ttu-id="ad12d-141">См. ниже.</span><span class="sxs-lookup"><span data-stu-id="ad12d-141">See below.</span></span>

### <a name="upgrade-a-single-dl"></a><span data-ttu-id="ad12d-142">Обновление единого DL</span><span class="sxs-lookup"><span data-stu-id="ad12d-142">Upgrade a single DL</span></span>

<span data-ttu-id="ad12d-143">Чтобы обновить один DL, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ad12d-143">To upgrade a single DL run the following command:</span></span>

```PowerShell
Upgrade-DistributionGroup -DlIdentities \<Dl SMTP address\>`
```

<span data-ttu-id="ad12d-144">Например, если вы хотите обновить DLs с помощью smTP-dl1@contoso.com, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ad12d-144">For example, if you want to upgrade a DLs with SMTP address dl1@contoso.com, run the following command:</span></span>

```PowerShell
Upgrade-DistributionGroup -DlIdentities dl1@contoso.com`
```

> [!NOTE]
> <span data-ttu-id="ad12d-145">Можно также обновить единый список рассылки до группы Microsoft 365 с помощью комлета [New-UnifiedGroup](/powershell/module/exchange/new-unifiedgroup) PowerShell</span><span class="sxs-lookup"><span data-stu-id="ad12d-145">You can also upgrade a single distribution list to a Microsoft 365 group using the [New-UnifiedGroup](/powershell/module/exchange/new-unifiedgroup) PowerShell cmdlet</span></span>

### <a name="upgrade-multiple-dls-in-a-batch"></a><span data-ttu-id="ad12d-146">Обновление нескольких DLs в пакете</span><span class="sxs-lookup"><span data-stu-id="ad12d-146">Upgrade multiple DLs in a batch</span></span>

<span data-ttu-id="ad12d-147">Вы также можете передать несколько DLs в качестве пакета и обновить их вместе:</span><span class="sxs-lookup"><span data-stu-id="ad12d-147">You can also pass multiple DLs as a batch and upgrade them together:</span></span>

```PowerShell
Upgrade-DistributionGroup -DlIdentities \<DL SMTP address1\>, \< DL SMTP address2\>,
\< DL SMTP address3\>, \< DL SMTP address 4\>
```

<span data-ttu-id="ad12d-148">Например, если вы хотите обновить пять DLs с smTP-адресом и `dl1@contoso.com` `dl2@contoso.com` , `dl3@contoso.com` `dl4@contoso.com` `dl5@contoso.com` и, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ad12d-148">For example, if you want to upgrade five DLs with SMTP address `dl1@contoso.com` and `dl2@contoso.com`, `dl3@contoso.com`, `dl4@contoso.com` and `dl5@contoso.com`, run the following command:</span></span>

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com, dl2@contoso.com, dl3@contoso.com, dl4@contoso.com, dl5@contoso.com`

### <a name="upgrade-all-eligible-dls"></a><span data-ttu-id="ad12d-149">Обновление всех подходящих DLs</span><span class="sxs-lookup"><span data-stu-id="ad12d-149">Upgrade all eligible DLs</span></span>

<span data-ttu-id="ad12d-150">Существует два способа обновления всех подходящих DLs.</span><span class="sxs-lookup"><span data-stu-id="ad12d-150">There are two ways in which you can upgrade all the eligible DLs.</span></span>

> [!NOTE]
> <span data-ttu-id="ad12d-151">Этот Upgrade-DistributionGroup не получает данные из конвейера, поэтому для успешного запуска необходимо использовать оператора "foreach-object". {}</span><span class="sxs-lookup"><span data-stu-id="ad12d-151">The Upgrade-DistributionGroup cmdlet doesn't receive data from the pipeline, for this reason it's required to use "foreach-object{}" operator to run successfully.</span></span>

1. <span data-ttu-id="ad12d-152">Получите подходящие DLs в клиенте и обновите их с помощью команды обновления:</span><span class="sxs-lookup"><span data-stu-id="ad12d-152">Get the eligible DLs in the tenant and upgrade them using the upgrade command:</span></span>

```PowerShell
Get-EligibleDistributionGroupForMigration | Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

2. <span data-ttu-id="ad12d-153">Получите список всех DLs и обновим только подходящие DLs:</span><span class="sxs-lookup"><span data-stu-id="ad12d-153">Get the list of all DLs and upgrade only the eligible DLs:</span></span>

```PowerShell
Get-DistributionGroup| Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

## <a name="faq-about-upgrading-distribution-lists-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="ad12d-154">FaQ об обновлении списков рассылки до Microsoft 365 Groups в Outlook</span><span class="sxs-lookup"><span data-stu-id="ad12d-154">FAQ about upgrading distribution lists to Microsoft 365 Groups in Outlook</span></span>

### <a name="which-distribution-lists-cant-be-upgraded"></a><span data-ttu-id="ad12d-155">Какие списки рассылки нельзя обновить?</span><span class="sxs-lookup"><span data-stu-id="ad12d-155">Which distribution lists can't be upgraded?</span></span>

<span data-ttu-id="ad12d-156">Обновлять можно только простые облачные списки рассылки, не являющиеся вложенными.</span><span class="sxs-lookup"><span data-stu-id="ad12d-156">You can only upgrade cloud-managed, simple, non-nested distribution lists.</span></span> <span data-ttu-id="ad12d-157">В таблице ниже перечислены списки **рассылки, которые невозможно** обновить.</span><span class="sxs-lookup"><span data-stu-id="ad12d-157">The table below lists distribution lists that **CANNOT** be upgraded.</span></span>

|<span data-ttu-id="ad12d-158">**Описание**</span><span class="sxs-lookup"><span data-stu-id="ad12d-158">**Property**</span></span>|<span data-ttu-id="ad12d-159">**Поддерживается?**</span><span class="sxs-lookup"><span data-stu-id="ad12d-159">**Eligible?**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ad12d-160">Список рассылки с локальным управлением.</span><span class="sxs-lookup"><span data-stu-id="ad12d-160">On-premises managed distribution list.</span></span>  <br/> |<span data-ttu-id="ad12d-161">Нет</span><span class="sxs-lookup"><span data-stu-id="ad12d-161">No</span></span>  <br/> |
|<span data-ttu-id="ad12d-p113">Вложенные списки рассылки. Список рассылки имеет дочерние группы или входит в другую группу.</span><span class="sxs-lookup"><span data-stu-id="ad12d-p113">Nested distribution lists. Distribution list either has child groups or is a member of another group.</span></span>  <br/> |<span data-ttu-id="ad12d-164">Нет</span><span class="sxs-lookup"><span data-stu-id="ad12d-164">No</span></span>  <br/> |
|<span data-ttu-id="ad12d-165">Списки рассылки **с получателями memberTypeDetails,** кроме **UserMailbox,** **SharedMailbox,** **TeamMailbox,** **MailUser**</span><span class="sxs-lookup"><span data-stu-id="ad12d-165">Distribution lists with member **RecipientTypeDetails** other than **UserMailbox**, **SharedMailbox**, **TeamMailbox**, **MailUser**</span></span>  <br/> |<span data-ttu-id="ad12d-166">Нет</span><span class="sxs-lookup"><span data-stu-id="ad12d-166">No</span></span>  <br/> |
|<span data-ttu-id="ad12d-167">Список рассылки, в котором более 100 владельцев</span><span class="sxs-lookup"><span data-stu-id="ad12d-167">Distribution list which has more than 100 owners</span></span>  <br/> |<span data-ttu-id="ad12d-168">Нет</span><span class="sxs-lookup"><span data-stu-id="ad12d-168">No</span></span>  <br/> |
|<span data-ttu-id="ad12d-169">Список рассылки, у которого нет владельцев.</span><span class="sxs-lookup"><span data-stu-id="ad12d-169">Distribution list which only has members but no owner</span></span>  <br/> |<span data-ttu-id="ad12d-170">Нет</span><span class="sxs-lookup"><span data-stu-id="ad12d-170">No</span></span>  <br/> |
|<span data-ttu-id="ad12d-171">Список рассылки, в псевдониме которого есть специальные знаки.</span><span class="sxs-lookup"><span data-stu-id="ad12d-171">Distribution list which has alias containing special characters</span></span>  <br/> |<span data-ttu-id="ad12d-172">Нет</span><span class="sxs-lookup"><span data-stu-id="ad12d-172">No</span></span>  <br/> |
|<span data-ttu-id="ad12d-173">Список рассылки, настроенный в качестве адреса перенаправления для общего почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="ad12d-173">If the distribution list is configured to be a forwarding address for Shared Mailbox</span></span>  <br/> |<span data-ttu-id="ad12d-174">Нет</span><span class="sxs-lookup"><span data-stu-id="ad12d-174">No</span></span>  <br/> |
|<span data-ttu-id="ad12d-175">Если DL является частью **ограничения отправитель в** другом DL.</span><span class="sxs-lookup"><span data-stu-id="ad12d-175">If the DL is part of **Sender Restriction** in another DL.</span></span>  <br/> |<span data-ttu-id="ad12d-176">Нет</span><span class="sxs-lookup"><span data-stu-id="ad12d-176">No</span></span>  <br/> |
|<span data-ttu-id="ad12d-177">Группы безопасности</span><span class="sxs-lookup"><span data-stu-id="ad12d-177">Security groups</span></span>  <br/> |<span data-ttu-id="ad12d-178">Нет</span><span class="sxs-lookup"><span data-stu-id="ad12d-178">No</span></span>  <br/> |
|<span data-ttu-id="ad12d-179">Динамические списки рассылки.</span><span class="sxs-lookup"><span data-stu-id="ad12d-179">Dynamic Distribution lists</span></span>  <br/> |<span data-ttu-id="ad12d-180">Нет</span><span class="sxs-lookup"><span data-stu-id="ad12d-180">No</span></span>  <br/> |
|<span data-ttu-id="ad12d-181">Списки рассылки, преобразованные в **RoomLists**</span><span class="sxs-lookup"><span data-stu-id="ad12d-181">Distribution lists which were converted to **RoomLists**</span></span>  <br/> |<span data-ttu-id="ad12d-182">Нет</span><span class="sxs-lookup"><span data-stu-id="ad12d-182">No</span></span>  <br/> |
|<span data-ttu-id="ad12d-183">Списки рассылки, в которых **закрывается MemberJoinRestriction** и/или **MemberDepartRestriction** </span><span class="sxs-lookup"><span data-stu-id="ad12d-183">Distribution lists where **MemberJoinRestriction** and/or **MemberDepartRestriction** is **Closed**</span></span>  <br/> |<span data-ttu-id="ad12d-184">Нет</span><span class="sxs-lookup"><span data-stu-id="ad12d-184">No</span></span>  <br/> |

### <a name="check-which-dls-are-eligible-for-upgrade"></a><span data-ttu-id="ad12d-185">Проверьте, какие DLs имеют право на обновление</span><span class="sxs-lookup"><span data-stu-id="ad12d-185">Check which DLs are eligible for upgrade</span></span>

<span data-ttu-id="ad12d-186">Если вы хотите проверить, имеет ли DL право или нет, вы можете выполнить приведенную ниже команду:</span><span class="sxs-lookup"><span data-stu-id="ad12d-186">If you want to check whether a DL is eligible or not, you can run the below command:</span></span>

`Get-DistributionGroup \<DL SMTP address\> | Get-EligibleDistributionGroupForMigration`

<span data-ttu-id="ad12d-187">Если вы хотите проверить, какие DLs имеют право на обновление, просто запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ad12d-187">If you want to check which DLs are eligible for upgrade just run the following command:</span></span>

`Get-EligibleDistributionGroupForMigration`

### <a name="who-can-run-the-upgrade-scripts"></a><span data-ttu-id="ad12d-188">Кто может выполнять сценарии обновления?</span><span class="sxs-lookup"><span data-stu-id="ad12d-188">Who can run the upgrade scripts?</span></span>

<span data-ttu-id="ad12d-189">Люди с правами глобального администратора или администратора Exchange.</span><span class="sxs-lookup"><span data-stu-id="ad12d-189">People with global admin or Exchange admin rights.</span></span>

### <a name="why-is-the-contact-card-still-showing-a-distribution-list-what-should-i-do-to-prevent-a-upgraded-distribution-list-from-showing-up-in-my-auto-suggest-list"></a><span data-ttu-id="ad12d-190">Почему карточка контакта по-прежнему отображается в списке рассылки?</span><span class="sxs-lookup"><span data-stu-id="ad12d-190">Why is the contact card still showing a distribution list?</span></span> <span data-ttu-id="ad12d-191">Что сделать, чтобы обновленный список рассылки не отображался в списке автозаполнения?</span><span class="sxs-lookup"><span data-stu-id="ad12d-191">What should I do to prevent a upgraded distribution list from showing up in my auto suggest list?</span></span>

- <span data-ttu-id="ad12d-192">Для Outlook. Если кто-то пытается отправить сообщение электронной почты в Outlook, введя имя группы Microsoft 365 после миграции, получатель будет решаться в качестве списка рассылки, а не группы.</span><span class="sxs-lookup"><span data-stu-id="ad12d-192">For Outlook: When someone tries to send an email in Outlook by typing the Microsoft 365 group name after migration, the recipient will be resolved as the distribution list instead of the group.</span></span> <span data-ttu-id="ad12d-193">Карточка контакта этого получателя останется в списке рассылки.</span><span class="sxs-lookup"><span data-stu-id="ad12d-193">The contact card of the recipient will be the distribution lists contact card.</span></span> <span data-ttu-id="ad12d-194">Это связано с кэшем получателей или кэшем псевдонимов в Outlook.</span><span class="sxs-lookup"><span data-stu-id="ad12d-194">This is because of the recipient cache or nick name cache in Outlook.</span></span> <span data-ttu-id="ad12d-195">Сообщение будет успешно отправлено в группу, но может вызвать путаницу в отправитель.</span><span class="sxs-lookup"><span data-stu-id="ad12d-195">The email will be sent successfully to the group, but might cause confusion to the sender.</span></span><br/><span data-ttu-id="ad12d-196">Для решения этой проблемы вам нужно сбросить кэш, выполнив действия, описанные в статье [Сведения о списке автозаполнения в Outlook](/outlook/troubleshoot/contacts/information-about-the-outlook-autocomplete-list).</span><span class="sxs-lookup"><span data-stu-id="ad12d-196">You can perform the steps in this topic, [Information about the Outlook AutoComplete list](/outlook/troubleshoot/contacts/information-about-the-outlook-autocomplete-list) to reset the cache, which will fix this issue.</span></span>

- <span data-ttu-id="ad12d-197">Для Outlook в Интернете. В случае Outlook в Интернете получатель списка рассылки по-прежнему останется в кэше.</span><span class="sxs-lookup"><span data-stu-id="ad12d-197">For Outlook on the web: In case of Outlook on the web, the distribution list recipient will still remain in the cache.</span></span> <span data-ttu-id="ad12d-198">Чтобы обновить кэш, можно выполнить действия в ["Удалить](https://support.microsoft.com/office/9E1419D9-E88F-445B-B07F-F558B8A37C58) предложенное имя или адрес электронной почты из списка автозаполнений", чтобы увидеть контактную карточку группы.</span><span class="sxs-lookup"><span data-stu-id="ad12d-198">You can follow the steps in [Remove suggested name or email address from the Auto-Complete List](https://support.microsoft.com/office/9E1419D9-E88F-445B-B07F-F558B8A37C58) to refresh the cache to see the group contact card.</span></span>

### <a name="do-new-group-members-get-a-welcome-email-in-their-inbox"></a><span data-ttu-id="ad12d-199">Получат ли участники группы приветственные сообщения?</span><span class="sxs-lookup"><span data-stu-id="ad12d-199">Do new group members get a welcome email in their inbox?</span></span>

<span data-ttu-id="ad12d-p117">Нет. По умолчанию параметру, который отвечает за отправку таких сообщений, присвоено значение false. Этот параметр относится как к существующим, так и к новым участникам группы, которые могут присоединиться к ней после переноса. Если владелец группы разрешит гостевым пользователям присоединяться к ней, они не будут получать приветственные сообщения. Несмотря на это они смогут использовать группу.</span><span class="sxs-lookup"><span data-stu-id="ad12d-p117">No. The setting to enable welcome messages is set to false by default. This setting affects both existing and new group members who may join after the migration is complete. If the group owner later allows guest users, guest users won't receive a welcome email in their inbox. Guest members can continue working with the group.</span></span>

### <a name="what-if-one-or-some-of-the-dls-are-not-upgraded"></a><span data-ttu-id="ad12d-205">Что делать, если один или несколько DLs не обновлены?</span><span class="sxs-lookup"><span data-stu-id="ad12d-205">What if one or some of the DLs are not upgraded?</span></span>

<span data-ttu-id="ad12d-206">Есть несколько случаев, когда, хотя DL имеет право, но не может быть обновлен.</span><span class="sxs-lookup"><span data-stu-id="ad12d-206">There are some cases in which though DL is eligible but could not be upgraded.</span></span> <span data-ttu-id="ad12d-207">DL не обновляется и остается как DL.</span><span class="sxs-lookup"><span data-stu-id="ad12d-207">The DL does not get upgraded and remains as a DL.</span></span>

- <span data-ttu-id="ad12d-208">Если администратор применил  политику адресов групповой электронной почты для групп в организации и они пытаются обновить DLs, которые не соответствуют критериям, DL не обновляется.</span><span class="sxs-lookup"><span data-stu-id="ad12d-208">Where admin has applied **Group Email Address Policy** for the groups in an organization and they try to upgrade DLs which doesn't fulfill the criteria, the DL does not get upgraded</span></span>

- <span data-ttu-id="ad12d-209">DLs с **набором memberJoinRestriction** или **MemberDepartRestriction,** задаваемой **в закрытом** режиме, не удалось обновить</span><span class="sxs-lookup"><span data-stu-id="ad12d-209">DLs with **MemberJoinRestriction** or **MemberDepartRestriction** set to **Closed**, could not be upgraded</span></span>

### <a name="what-happens-to-the-dl-if-the-upgrade-from-eac-fails"></a><span data-ttu-id="ad12d-210">Что происходит со списком рассылки при сбое обновления, запущенного через EAC?</span><span class="sxs-lookup"><span data-stu-id="ad12d-210">What happens to the DL if the upgrade from EAC fails?</span></span>

<span data-ttu-id="ad12d-p119">Обновление происходит только после отправки вызова на сервер. Если обновление завершится сбоем, список рассылки не будет изменен. Он будет работать, как прежде.</span><span class="sxs-lookup"><span data-stu-id="ad12d-p119">The upgrade will happen only when the call is submitted to the server. If the upgrade fails, your DLs will be intact. They will work like they used to.</span></span>