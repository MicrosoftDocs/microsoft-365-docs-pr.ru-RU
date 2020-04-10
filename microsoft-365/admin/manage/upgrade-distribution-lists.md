---
title: Обновление списков рассылки до групп Office 365 в Outlook
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 787d7a75-e201-46f3-a242-f698162ff09f
description: Узнайте, как обновить один или несколько списков рассылки до группы Office 365 в Outlook, а также как использовать PowerShell для одновременного обновления нескольких списков рассылки.
ms.openlocfilehash: c3acf1d47a37d79d666b1b951bea704c273ccf09
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212285"
---
# <a name="upgrade-distribution-lists-to-office-365-groups-in-outlook"></a><span data-ttu-id="54db4-103">Обновление списков рассылки до групп Office 365 в Outlook</span><span class="sxs-lookup"><span data-stu-id="54db4-103">Upgrade distribution lists to Office 365 Groups in Outlook</span></span>

<span data-ttu-id="54db4-104">Вы можете обновить списки рассылки до группы Office 365 с Outlook.</span><span class="sxs-lookup"><span data-stu-id="54db4-104">You can upgrade distribution lists to Office 365 Groups with Outlook.</span></span> <span data-ttu-id="54db4-105">Это позволит использовать все возможности и функции групп Office 365.</span><span class="sxs-lookup"><span data-stu-id="54db4-105">This is a great way to give your organization's distribution lists all the features and functionality of Office 365 groups.</span></span> [<span data-ttu-id="54db4-106">Причины для перехода со списков рассылки на группы в Outlook</span><span class="sxs-lookup"><span data-stu-id="54db4-106">Why you should upgrade your distribution lists to groups in Outlook</span></span>](https://support.office.com/article/7fb3d880-593b-4909-aafa-950dd50ce188.aspx)

<span data-ttu-id="54db4-107">Вы можете обновить один или сразу несколько списков рассылки.</span><span class="sxs-lookup"><span data-stu-id="54db4-107">You can upgrade DLs one at a time, or several at the same time.</span></span>

## <a name="upgrade-one-or-many-distribution-lists-to-office-365-groups-in-outlook"></a><span data-ttu-id="54db4-108">Обновление одного или нескольких списков рассылки до групп Office 365 в Outlook</span><span class="sxs-lookup"><span data-stu-id="54db4-108">Upgrade one or many distribution lists to Office 365 Groups in Outlook</span></span>

<span data-ttu-id="54db4-109">Для обновления списка рассылки необходимо быть глобальным администратором Office 365 или администратором Exchange.</span><span class="sxs-lookup"><span data-stu-id="54db4-109">You must be an Office 365 global admin or Exchange admin to upgrade a distribution list.</span></span> <span data-ttu-id="54db4-110">Чтобы выполнить обновление до группы Office 365, группа рассылки должна иметь владельца почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="54db4-110">To upgrade to Office 365 groups, a distribution group must have an owner with a mailbox.</span></span> 

1. <span data-ttu-id="54db4-111">Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Центр администрирования Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="54db4-111">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="54db4-112">В центре администрирования Exchange перейдите в раздел группы **получателей** \> **Groups**.</span><span class="sxs-lookup"><span data-stu-id="54db4-112">In the Exchange admin center, go to **Recipients** \> **Groups**.</span></span><br/><span data-ttu-id="54db4-113">Появится уведомление о том, у вас есть списки рассылки ( **группы рассылки** ), которые можно обновить до групп Office 365.</span><span class="sxs-lookup"><span data-stu-id="54db4-113">You'll see a notice indicating you have distribution lists (also called **distribution groups** ) that are eligible to be upgraded to Office 365 groups.</span></span><br/> <span data-ttu-id="54db4-114">![Нажмите кнопку "получить начало"](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)</span><span class="sxs-lookup"><span data-stu-id="54db4-114">![Select the Get started button](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)</span></span>

3. <span data-ttu-id="54db4-115">Выберите один или несколько списков рассылки ( **групп рассылки** ) на странице **групп**.</span><span class="sxs-lookup"><span data-stu-id="54db4-115">Select one or more distribution lists (also called a **distribution group** ) from the **groups** page.</span></span><br/><span data-ttu-id="54db4-116">![Выбор группы рассылки](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)</span><span class="sxs-lookup"><span data-stu-id="54db4-116">![Select a distribution group](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)</span></span>

4. <span data-ttu-id="54db4-117">Выберите значок обновление.</span><span class="sxs-lookup"><span data-stu-id="54db4-117">Select the upgrade icon.</span></span><br/>![Значок обновления до Office 365 Groups](../../media/1e28cb3d-bff3-4be3-8329-1902d2d54720.png)

5. <span data-ttu-id="54db4-119">В диалоговом окне сведения нажмите **кнопку Да** , чтобы подтвердить обновление.</span><span class="sxs-lookup"><span data-stu-id="54db4-119">On the information dialog, select **Yes** to confirm the upgrade.</span></span> <span data-ttu-id="54db4-120">Процесс начинается немедленно.</span><span class="sxs-lookup"><span data-stu-id="54db4-120">The process begins immediately.</span></span> <span data-ttu-id="54db4-121">В зависимости от размера и количества обновляемых списков документов процесс может занять несколько минут или часов.</span><span class="sxs-lookup"><span data-stu-id="54db4-121">Depending on the size and number of DLs you're upgrading, the process can take minutes or hours.</span></span><br/><span data-ttu-id="54db4-122">Если список рассылки не может быть обновлен, появится диалоговое окно с сообщением.</span><span class="sxs-lookup"><span data-stu-id="54db4-122">If the distribution list can't be upgraded, a dialog appears saying so.</span></span> <span data-ttu-id="54db4-123">Сведения о [том, какие списки рассылки невозможно обновить?](#which-distribution-lists-cannot-be-upgraded).</span><span class="sxs-lookup"><span data-stu-id="54db4-123">See [Which distribution lists cannot be upgraded?](#which-distribution-lists-cannot-be-upgraded).</span></span>

6. <span data-ttu-id="54db4-124">Если вы обновляете несколько списков рассылки, используйте раскрывающийся список, чтобы отфильтровать, какие списки рассылки были обновлены.</span><span class="sxs-lookup"><span data-stu-id="54db4-124">If you're upgrading multiple distribution lists, use the drop-down list to filter which distribution lists have been upgraded.</span></span> <span data-ttu-id="54db4-125">Если список не заполнен, подождите некоторое время, а затем нажмите кнопку **Обновить** , чтобы увидеть, что Обновлено успешно.</span><span class="sxs-lookup"><span data-stu-id="54db4-125">If the list isn't complete, wait a while longer and then select **Refresh** to see what's been successfully upgraded.</span></span><br/><span data-ttu-id="54db4-p106">Уведомление об окончании обновления для всех выбранных списков рассылки не выводится. То, какие списки были обновлены, можно узнать по разделам **Доступны для обновления** и **Обновленные списки рассылки**.</span><span class="sxs-lookup"><span data-stu-id="54db4-p106">There's no notice that tells you when the upgrade process has completed for all DLs you selected. You can figure this out by looking to see what's listed under **Available for upgrade** or **Upgraded DLs**.</span></span>

7. <span data-ttu-id="54db4-p107">Если вы выбрали список рассылки для обновления, но оно по-прежнему отображается на странице "Доступны для обновления", его не удалось обновить. См. раздел [Что делать, если возникает ошибка обновления](#what-to-do-if-the-upgrade-doesnt-work).</span><span class="sxs-lookup"><span data-stu-id="54db4-p107">If you selected a DL for upgrade, but it's still appears on the page as Available to upgrade, then it failed to upgrade. See [What to do if the upgrade doesn't work](#what-to-do-if-the-upgrade-doesnt-work).</span></span>

> [!NOTE]
> <span data-ttu-id="54db4-p108">Если вы получаете письма с дайджестом сообщений группы, то могли заметить, что в них (в самом низу) иногда предлагается обновить списки рассылки, владельцем которых вы являетесь. Дополнительные сведения о письмах с дайджестом см. в статье [Групповые беседы в Outlook](https://support.office.com/article/a0482e24-a769-4e39-a5ba-a7c56e828b22.aspx).</span><span class="sxs-lookup"><span data-stu-id="54db4-p108">If you're getting the groups digest emails you may notice at the bottom that it will sometimes offer to let you upgrade any eligible distribution lists that you're the owner of. See [Have a group conversation in Outlook](https://support.office.com/article/a0482e24-a769-4e39-a5ba-a7c56e828b22.aspx) for more information about digest emails.</span></span>


## <a name="what-to-do-if-the-upgrade-doesnt-work"></a><span data-ttu-id="54db4-132">Что делать, если возникает ошибка обновления</span><span class="sxs-lookup"><span data-stu-id="54db4-132">What to do if the upgrade doesn't work</span></span>

<span data-ttu-id="54db4-133">Списки рассылки, которые не удалось обновить, остаются без изменений.</span><span class="sxs-lookup"><span data-stu-id="54db4-133">Distribution lists that fail to upgrade remain unchanged.</span></span>

<span data-ttu-id="54db4-p109">Если не удалось обновить **поддерживаемый** список рассылки, отправьте [запрос в службу поддержки](../contact-support-for-business-products.md). Об этой проблеме необходимо сообщить команде технических специалистов по Группам.</span><span class="sxs-lookup"><span data-stu-id="54db4-p109">If one or more **eligible** distribution lists fail to be upgraded, open a [Support ticket](../contact-support-for-business-products.md). The issue will need to be escalated to the Groups Engineering team for them to figure out the problem.</span></span>

<span data-ttu-id="54db4-p110">Возможно, список рассылки не удалось обновить из-за сбоя службы, но такое случается довольно редко. Попробуйте подождать немного и повторить попытку.</span><span class="sxs-lookup"><span data-stu-id="54db4-p110">It's possible that the distribution list didn't get upgraded because of a service outage, but pretty unlikely. If you want, wait a while and then try to upgrade the DL again.</span></span>

## <a name="how-to-use-powershell-to-upgrade-several-distribution-lists-at-the-same-time"></a><span data-ttu-id="54db4-138">Обновление нескольких списков рассылки одновременно с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="54db4-138">How to use PowerShell to upgrade several distribution lists at the same time</span></span>

<span data-ttu-id="54db4-139">Если вы хорошо знакомы с PowerShell, можно воспользоваться этим средством вместо пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="54db4-139">If you're experienced at using PowerShell, you might want to go this route instead of using the UI.</span></span> <span data-ttu-id="54db4-140">У нас есть набор командлетов, которые помогут вам обновить списки рассылки.</span><span class="sxs-lookup"><span data-stu-id="54db4-140">We have a set of cmdlets that will help you upgrade distribution lists.</span></span> <span data-ttu-id="54db4-141">См. ниже.</span><span class="sxs-lookup"><span data-stu-id="54db4-141">See below.</span></span>

### <a name="upgrade-a-single-dl"></a><span data-ttu-id="54db4-142">Обновление одного списка рассылки</span><span class="sxs-lookup"><span data-stu-id="54db4-142">Upgrade a single DL</span></span>

<span data-ttu-id="54db4-143">Чтобы обновить один DL, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="54db4-143">To upgrade a single DL run the following command:</span></span>

`Upgrade-DistributionGroup -DlIdentities \<Dl SMTP address\>`

<span data-ttu-id="54db4-144">Например, если вы хотите обновить списки рассылки с помощью SMTP-адреса dl1@contoso.com, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="54db4-144">For example, if you want to upgrade a DLs with SMTP address dl1@contoso.com, run the following command:</span></span>

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com`

> [!NOTE]
> <span data-ttu-id="54db4-145">Вы также можете обновить один список рассылки до группы Office 365 с помощью командлета PowerShell [New – UnifiedGroup](https://go.microsoft.com/fwlink/?LinkID=786379) .</span><span class="sxs-lookup"><span data-stu-id="54db4-145">You can also upgrade a single distribution list to an Office 365 group using the [New-UnifiedGroup](https://go.microsoft.com/fwlink/?LinkID=786379) PowerShell cmdlet</span></span>

### <a name="upgrade-multiple-dls-in-a-batch"></a><span data-ttu-id="54db4-146">Обновление нескольких списков рассылки в пакете</span><span class="sxs-lookup"><span data-stu-id="54db4-146">Upgrade multiple DLs in a batch</span></span>

<span data-ttu-id="54db4-147">Вы также можете передать несколько списков рассылки в виде пакета и обновить их вместе:</span><span class="sxs-lookup"><span data-stu-id="54db4-147">You can also pass multiple DLs as a batch and upgrade them together:</span></span>

```
Upgrade-DistributionGroup -DlIdentities \<DL SMTP address1\>, \< DL SMTP address2\>,

\< DL SMTP address3\>, \< DL SMTP address 4\>
```

<span data-ttu-id="54db4-148">Например, если вы хотите обновить пять списков рассылки с `dl1@contoso.com` SMTP-адресом `dl2@contoso.com`и `dl3@contoso.com`, `dl4@contoso.com` , `dl5@contoso.com`и, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="54db4-148">For example, if you want to upgrade five DLs with SMTP address `dl1@contoso.com` and `dl2@contoso.com`, `dl3@contoso.com`, `dl4@contoso.com` and `dl5@contoso.com`, run the following command:</span></span>

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com, dl2@contoso.com, dl3@contoso.com, dl4@contoso.com, dl5@contoso.com`

### <a name="upgrade-all-eligible-dls"></a><span data-ttu-id="54db4-149">Обновление всех подходящих списков рассылки</span><span class="sxs-lookup"><span data-stu-id="54db4-149">Upgrade all eligible DLs</span></span>

<span data-ttu-id="54db4-150">Существует два способа обновления всех подходящих списков рассылки.</span><span class="sxs-lookup"><span data-stu-id="54db4-150">There are two ways in which you can upgrade all the eligible DLs.</span></span>

> [!NOTE]
> <span data-ttu-id="54db4-151">Командлет Upgrade – DistributionGroup не получает данные из конвейера по этой причине, поэтому для успешного выполнения необходимо использовать оператор ForEach — Object{}.</span><span class="sxs-lookup"><span data-stu-id="54db4-151">The Upgrade-DistributionGroup cmdlet doesn't receive data from the pipeline, for this reason it's required to use "foreach-object{}" operator to run successfully.</span></span>

1. <span data-ttu-id="54db4-152">Получите подходящие списки рассылки в клиенте и обновите их с помощью команды Upgrade:</span><span class="sxs-lookup"><span data-stu-id="54db4-152">Get the eligible DLs in the tenant and upgrade them using the upgrade command:</span></span>

```
Get-EligibleDistributionGroupForMigration | Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

2. <span data-ttu-id="54db4-153">Получение списка всех списков рассылки и обновление только соответствующих списков рассылки:</span><span class="sxs-lookup"><span data-stu-id="54db4-153">Get the list of all DLs and upgrade only the eligible DLs:</span></span>

```
Get-DistributionGroup| Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

## <a name="faq-about-upgrading-distribution-lists-to-office-365-groups-in-outlook"></a><span data-ttu-id="54db4-154">Вопросы и ответы об обновлении списков рассылки до групп Office 365 в Outlook</span><span class="sxs-lookup"><span data-stu-id="54db4-154">FAQ about upgrading distribution lists to Office 365 Groups in Outlook</span></span>

### <a name="which-distribution-lists-cannot-be-upgraded"></a><span data-ttu-id="54db4-155">Какие списки рассылки невозможно обновить?</span><span class="sxs-lookup"><span data-stu-id="54db4-155">Which distribution lists cannot be upgraded?</span></span>

<span data-ttu-id="54db4-156">Обновлять можно только простые облачные списки рассылки, не являющиеся вложенными.</span><span class="sxs-lookup"><span data-stu-id="54db4-156">You can only upgrade cloud-managed, simple, non-nested distribution lists.</span></span> <span data-ttu-id="54db4-157">В приведенной ниже таблице перечислены списки рассылки, которые **не могут** быть обновлены.</span><span class="sxs-lookup"><span data-stu-id="54db4-157">The table below lists distribution lists that **CANNOT** be upgraded.</span></span>

|<span data-ttu-id="54db4-158">**Описание**</span><span class="sxs-lookup"><span data-stu-id="54db4-158">**Property**</span></span>|<span data-ttu-id="54db4-159">**Поддерживается?**</span><span class="sxs-lookup"><span data-stu-id="54db4-159">**Eligible?**</span></span>|
|:-----|:-----|
|<span data-ttu-id="54db4-160">Список рассылки с локальным управлением.</span><span class="sxs-lookup"><span data-stu-id="54db4-160">On-premises managed distribution list.</span></span>  <br/> |<span data-ttu-id="54db4-161">Нет</span><span class="sxs-lookup"><span data-stu-id="54db4-161">No</span></span>  <br/> |
|<span data-ttu-id="54db4-p113">Вложенные списки рассылки. Список рассылки имеет дочерние группы или входит в другую группу.</span><span class="sxs-lookup"><span data-stu-id="54db4-p113">Nested distribution lists. Distribution list either has child groups or is a member of another group.</span></span>  <br/> |<span data-ttu-id="54db4-164">Нет</span><span class="sxs-lookup"><span data-stu-id="54db4-164">No</span></span>  <br/> |
|<span data-ttu-id="54db4-165">Списки рассылки с членами **RecipientTypeDetails** , отличными от **UserMailbox**, **SharedMailbox**, **TeamMailbox**, **MailUser**</span><span class="sxs-lookup"><span data-stu-id="54db4-165">Distribution lists with member **RecipientTypeDetails** other than **UserMailbox**, **SharedMailbox**, **TeamMailbox**, **MailUser**</span></span>  <br/> |<span data-ttu-id="54db4-166">Нет</span><span class="sxs-lookup"><span data-stu-id="54db4-166">No</span></span>  <br/> |
|<span data-ttu-id="54db4-167">Список рассылки с более чем 100 владельцами</span><span class="sxs-lookup"><span data-stu-id="54db4-167">Distribution list which has more than 100 owners</span></span>  <br/> |<span data-ttu-id="54db4-168">Нет</span><span class="sxs-lookup"><span data-stu-id="54db4-168">No</span></span>  <br/> |
|<span data-ttu-id="54db4-169">Список рассылки, у которого нет владельцев.</span><span class="sxs-lookup"><span data-stu-id="54db4-169">Distribution list which only has members but no owner</span></span>  <br/> |<span data-ttu-id="54db4-170">Нет</span><span class="sxs-lookup"><span data-stu-id="54db4-170">No</span></span>  <br/> |
|<span data-ttu-id="54db4-171">Список рассылки, в псевдониме которого есть специальные знаки.</span><span class="sxs-lookup"><span data-stu-id="54db4-171">Distribution list which has alias containing special characters</span></span>  <br/> |<span data-ttu-id="54db4-172">Нет</span><span class="sxs-lookup"><span data-stu-id="54db4-172">No</span></span>  <br/> |
|<span data-ttu-id="54db4-173">Список рассылки, настроенный в качестве адреса перенаправления для общего почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="54db4-173">If the distribution list is configured to be a forwarding address for Shared Mailbox</span></span>  <br/> |<span data-ttu-id="54db4-174">Нет</span><span class="sxs-lookup"><span data-stu-id="54db4-174">No</span></span>  <br/> |
|<span data-ttu-id="54db4-175">Если DL является частью **ограничения отправителя** в другом списке рассылки.</span><span class="sxs-lookup"><span data-stu-id="54db4-175">If the DL is part of **Sender Restriction** in another DL.</span></span>  <br/> |<span data-ttu-id="54db4-176">Нет</span><span class="sxs-lookup"><span data-stu-id="54db4-176">No</span></span>  <br/> |
|<span data-ttu-id="54db4-177">Группы безопасности</span><span class="sxs-lookup"><span data-stu-id="54db4-177">Security groups</span></span>  <br/> |<span data-ttu-id="54db4-178">Нет</span><span class="sxs-lookup"><span data-stu-id="54db4-178">No</span></span>  <br/> |
|<span data-ttu-id="54db4-179">Динамические списки рассылки.</span><span class="sxs-lookup"><span data-stu-id="54db4-179">Dynamic Distribution lists</span></span>  <br/> |<span data-ttu-id="54db4-180">Нет</span><span class="sxs-lookup"><span data-stu-id="54db4-180">No</span></span>  <br/> |
|<span data-ttu-id="54db4-181">Списки рассылки, которые были преобразованы в **румлистс**</span><span class="sxs-lookup"><span data-stu-id="54db4-181">Distribution lists which were converted to **RoomLists**</span></span>  <br/> |<span data-ttu-id="54db4-182">Нет</span><span class="sxs-lookup"><span data-stu-id="54db4-182">No</span></span>  <br/> |
|<span data-ttu-id="54db4-183">Списки рассылки, в которых **мембержоинрестриктион** и/или **мембердепартрестриктион** **закрыт**</span><span class="sxs-lookup"><span data-stu-id="54db4-183">Distribution lists where **MemberJoinRestriction** and/or **MemberDepartRestriction** is **Closed**</span></span>  <br/> |<span data-ttu-id="54db4-184">Нет</span><span class="sxs-lookup"><span data-stu-id="54db4-184">No</span></span>  <br/> |

### <a name="how-do-i-check-which-dls-are-eligible-for-upgrade"></a><span data-ttu-id="54db4-185">Как проверить, какие списки рассылки подходят для обновления?</span><span class="sxs-lookup"><span data-stu-id="54db4-185">How do I check which DLs are eligible for upgrade?</span></span>

<span data-ttu-id="54db4-186">Если вы хотите проверить, подходит ли DL, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="54db4-186">If you want to check whether a DL is eligible or not, you can run the below command:</span></span>

`Get-DistributionGroup \<DL SMTP address\> | Get-EligibleDistributionGroupForMigration`

<span data-ttu-id="54db4-187">Чтобы проверить, какие списки рассылки могут быть обновлены, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="54db4-187">If you want to check which DLs are eligible for upgrade just run the following command:</span></span>

`Get-EligibleDistributionGroupForMigration`

### <a name="who-can-run-the-upgrade-scripts"></a><span data-ttu-id="54db4-188">Кто может выполнять сценарии обновления?</span><span class="sxs-lookup"><span data-stu-id="54db4-188">Who can run the upgrade scripts?</span></span>

<span data-ttu-id="54db4-189">Пользователи с правами глобального администратора Office 365 или администратора Exchange.</span><span class="sxs-lookup"><span data-stu-id="54db4-189">People with Office 365 global admin or Exchange admin rights.</span></span>

### <a name="why-is-the-contact-card-still-showing-a-distribution-list-what-should-i-do-to-prevent-a-upgraded-distribution-list-from-showing-up-in-my-auto-suggest-list"></a><span data-ttu-id="54db4-190">Почему карточка контакта по-прежнему отображается в списке рассылки?</span><span class="sxs-lookup"><span data-stu-id="54db4-190">Why is the contact card still showing a distribution list?</span></span> <span data-ttu-id="54db4-191">Что сделать, чтобы обновленный список рассылки не отображался в списке автозаполнения?</span><span class="sxs-lookup"><span data-stu-id="54db4-191">What should I do to prevent a upgraded distribution list from showing up in my auto suggest list?</span></span>

- <span data-ttu-id="54db4-192">Для Outlook: когда кто-то пытается отправить электронное письмо в Outlook, введя имя группы Office 365 после миграции, получатель будет разрешаться как список рассылки, а не как группа.</span><span class="sxs-lookup"><span data-stu-id="54db4-192">For Outlook: When someone tries to send an email in Outlook by typing the Office 365 group name after migration, the recipient will be resolved as the distribution list instead of the group.</span></span> <span data-ttu-id="54db4-193">Карточка контакта этого получателя останется в списке рассылки.</span><span class="sxs-lookup"><span data-stu-id="54db4-193">The contact card of the recipient will be the distribution lists contact card.</span></span> <span data-ttu-id="54db4-194">Это связано с кэшем получателей или кэшем псевдонимов в Outlook.</span><span class="sxs-lookup"><span data-stu-id="54db4-194">This is because of the recipient cache or nick name cache in Outlook.</span></span> <span data-ttu-id="54db4-195">Сообщение электронной почты будет успешно отправлено в группу, но может привести к путанице отправителя.</span><span class="sxs-lookup"><span data-stu-id="54db4-195">The email will be sent successfully to the group, but might cause confusion to the sender.</span></span><br/><span data-ttu-id="54db4-196">Для решения этой проблемы вам нужно сбросить кэш, выполнив действия, описанные в статье [Сведения о списке автозаполнения в Outlook](https://go.microsoft.com/fwlink/?LinkID=798736).</span><span class="sxs-lookup"><span data-stu-id="54db4-196">You can perform the steps in this topic, [Information about the Outlook AutoComplete list](https://go.microsoft.com/fwlink/?LinkID=798736) to reset the cache, which will fix this issue.</span></span>

- <span data-ttu-id="54db4-197">Для Outlook в Интернете: в случае Outlook в Интернете получатель списка рассылки останется в кэше.</span><span class="sxs-lookup"><span data-stu-id="54db4-197">For Outlook on the web: In case of Outlook on the web, the distribution list recipient will still remain in the cache.</span></span> <span data-ttu-id="54db4-198">Вы можете выполнить действия, описанные в статье [Удаление предлагаемого имени или адреса электронной почты из списка автозавершения](https://support.office.com/article/9E1419D9-E88F-445B-B07F-F558B8A37C58.aspx) , чтобы обновить кэш, чтобы увидеть карточку контакта группы.</span><span class="sxs-lookup"><span data-stu-id="54db4-198">You can follow the steps in [Remove suggested name or email address from the Auto-Complete List](https://support.office.com/article/9E1419D9-E88F-445B-B07F-F558B8A37C58.aspx) to refresh the cache to see the group contact card.</span></span>

### <a name="do-new-group-members-get-a-welcome-email-in-their-inbox"></a><span data-ttu-id="54db4-199">Получат ли участники группы приветственные сообщения?</span><span class="sxs-lookup"><span data-stu-id="54db4-199">Do new group members get a welcome email in their inbox?</span></span>

<span data-ttu-id="54db4-p117">Нет. По умолчанию параметру, который отвечает за отправку таких сообщений, присвоено значение false. Этот параметр относится как к существующим, так и к новым участникам группы, которые могут присоединиться к ней после переноса. Если владелец группы разрешит гостевым пользователям присоединяться к ней, они не будут получать приветственные сообщения. Несмотря на это они смогут использовать группу.</span><span class="sxs-lookup"><span data-stu-id="54db4-p117">No. The setting to enable welcome messages is set to false by default. This setting affects both existing and new group members who may join after the migration is complete. If the group owner later allows guest users, guest users won't receive a welcome email in their inbox. Guest members can continue working with the group.</span></span>

### <a name="what-if-one-or-some-of-the-dls-are-not-upgraded"></a><span data-ttu-id="54db4-205">Что делать, если один или несколько списков рассылки не обновляются?</span><span class="sxs-lookup"><span data-stu-id="54db4-205">What if one or some of the DLs are not upgraded?</span></span>

<span data-ttu-id="54db4-206">Существует несколько случаев, когда DL является допустимым, но его не удалось обновить.</span><span class="sxs-lookup"><span data-stu-id="54db4-206">There are some cases in which though DL is eligible but could not be upgraded.</span></span> <span data-ttu-id="54db4-207">Список рассылки не обновляется и остается в виде списка рассылки.</span><span class="sxs-lookup"><span data-stu-id="54db4-207">The DL does not get upgraded and remains as a DL.</span></span>

- <span data-ttu-id="54db4-208">Если администратор применил **политику адресов электронной почты** групп для групп в Организации и пытается обновить списки рассылки, которые не удовлетворяют этим условиям, список рассылки не обновляется.</span><span class="sxs-lookup"><span data-stu-id="54db4-208">Where admin has applied **Group Email Address Policy** for the groups in an organization and they try to upgrade DLs which doesn't fulfill the criteria, the DL does not get upgraded</span></span>

- <span data-ttu-id="54db4-209">Списки рассылки с **мембержоинрестриктион** или **мембердепартрестриктион** , для которых задано значение **Closed**, не удалось обновить</span><span class="sxs-lookup"><span data-stu-id="54db4-209">DLs with **MemberJoinRestriction** or **MemberDepartRestriction** set to **Closed**, could not be upgraded</span></span>

### <a name="what-happens-to-the-dl-if-the-upgrade-from-eac-fails"></a><span data-ttu-id="54db4-210">Что происходит со списком рассылки при сбое обновления, запущенного через EAC?</span><span class="sxs-lookup"><span data-stu-id="54db4-210">What happens to the DL if the upgrade from EAC fails?</span></span>

<span data-ttu-id="54db4-p119">Обновление происходит только после отправки вызова на сервер. Если обновление завершится сбоем, список рассылки не будет изменен. Он будет работать, как прежде.</span><span class="sxs-lookup"><span data-stu-id="54db4-p119">The upgrade will happen only when the call is submitted to the server. If the upgrade fails, your DLs will be intact. They will work like they used to.</span></span>


