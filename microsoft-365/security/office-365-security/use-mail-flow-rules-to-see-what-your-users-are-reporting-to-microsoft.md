---
title: Просмотр отчетов, передаваемых пользователями в Майкрософт, с помощью правил для потока обработки почты
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: Администраторы могут узнать, как использовать правила потока почты (также известные как правила транспорта) для получения копий сообщений, которые пользователи сообщают Корпорации Майкрософт.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 34857c368fc910eeb43f6a78c490b9ad7568db1c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918634"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a><span data-ttu-id="79640-103">Просмотр отчетов, передаваемых пользователями в Майкрософт, с помощью правил для потока обработки почты</span><span class="sxs-lookup"><span data-stu-id="79640-103">Use mail flow rules to see what your users are reporting to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="79640-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="79640-104">**Applies to**</span></span>
- [<span data-ttu-id="79640-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="79640-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="79640-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="79640-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="79640-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="79640-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="79640-108">В организациях Microsoft 365 с почтовыми ящиками в Exchange Online или автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online пользователи могут отправлять сообщения в Корпорацию Майкрософт для анализа, как описано в сообщениях и файлах Отчета в [Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="79640-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there are multiple ways for users to report messages to Microsoft for analysis as described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

<span data-ttu-id="79640-109">Можно создать правило потока почты (также известное как правило транспорта), которое ищет сообщения, которые пользователи сообщают Корпорации Майкрософт, и можно настроить получателей Bcc для получения копий этих сообщений.</span><span class="sxs-lookup"><span data-stu-id="79640-109">You can create a mail flow rule (also known as a transport rule) that looks for messages that users report to Microsoft, and you can configure Bcc recipients to receive copies of these reported messages.</span></span>

<span data-ttu-id="79640-110">Правило потока почты можно создать в центре администрирования Exchange (EAC) и PowerShell (Exchange Online PowerShell для организаций Microsoft 365 с почтовыми ящиками в Exchange Online; автономные EOP PowerShell для организаций без почтовых ящиков Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="79640-110">You can create the mail flow rule in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="79640-111">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="79640-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="79640-112">Вам необходимо получить разрешения в Exchange Online или Exchange Online Protection, прежде чем вы сможете сделать процедуры в этой статье.</span><span class="sxs-lookup"><span data-stu-id="79640-112">You need to be assigned permissions in Exchange Online or Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="79640-113">В частности, вам  нужна роль Правил транспорта, которая по умолчанию назначена группам  ролей **"Управление** организацией",  "Управление соответствием требованиям" (глобальные администраторы) и "Управление записями".</span><span class="sxs-lookup"><span data-stu-id="79640-113">Specifically, you need the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management** (global admins), and **Records Management** role groups by default.</span></span>

  <span data-ttu-id="79640-114">Дополнительную информацию см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="79640-114">For more information, see the following topics:</span></span>

  - [<span data-ttu-id="79640-115">Разрешения в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="79640-115">Permissions in Exchange Online</span></span>](/exchange/permissions-exo/permissions-exo)
  - [<span data-ttu-id="79640-116">Разрешения в автономном EOP</span><span class="sxs-lookup"><span data-stu-id="79640-116">Permissions in standalone EOP</span></span>](feature-permissions-in-eop.md)
  - [<span data-ttu-id="79640-117">Использование EAC измените список участников в группах ролей</span><span class="sxs-lookup"><span data-stu-id="79640-117">Use the EAC modify the list of members in role groups</span></span>](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- <span data-ttu-id="79640-118">Чтобы открыть центр администрирования в Exchange Online, см. в центре [администрирования Exchange в Exchange Online.](/Exchange/exchange-admin-center)</span><span class="sxs-lookup"><span data-stu-id="79640-118">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](/Exchange/exchange-admin-center).</span></span> <span data-ttu-id="79640-119">Чтобы открыть EAC в автономных EOP, см. в центре администрирования Exchange в режиме [автономный EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="79640-119">To open the EAC in standalone EOP, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="79640-120">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="79640-120">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="79640-121">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="79640-121">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="79640-122">Дополнительные сведения о правилах потока почты в Exchange Online и автономных EOP см. в следующих темах:</span><span class="sxs-lookup"><span data-stu-id="79640-122">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>
  - [<span data-ttu-id="79640-123">Правила потока обработки почты (правила транспорта) в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="79640-123">Mail flow rules (transport rules) in Exchange Online</span></span>](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)
  - [<span data-ttu-id="79640-124">Условия и исключения правил потока почты (предикаты) в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="79640-124">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)
  - [<span data-ttu-id="79640-125">Действия правила потока почты в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="79640-125">Mail flow rule actions in Exchange Online</span></span>](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="79640-126">Используйте EAC для создания правила потока почты для получения копий сообщений</span><span class="sxs-lookup"><span data-stu-id="79640-126">Use the EAC to create a mail flow rule to receive copies of reported messages</span></span>

1. <span data-ttu-id="79640-127">В Центре администрирования Exchange перейдите в раздел **Поток обработки почты** \> **Правила**.</span><span class="sxs-lookup"><span data-stu-id="79640-127">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="79640-128">Нажмите **кнопку Добавить** ![ значок Добавить, ](../../media/ITPro-EAC-AddIcon.png) а затем выберите Создать новое **правило**.</span><span class="sxs-lookup"><span data-stu-id="79640-128">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="79640-129">На открывшейся странице **Новое правило** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="79640-129">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="79640-130">**Имя.** Введите уникальное, описательное имя для правила.</span><span class="sxs-lookup"><span data-stu-id="79640-130">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="79640-131">Например, Bcc Messages Reported to Microsoft.</span><span class="sxs-lookup"><span data-stu-id="79640-131">For example, Bcc Messages Reported to Microsoft.</span></span>

   - <span data-ttu-id="79640-132">Нажмите кнопку **Дополнительные параметры**.</span><span class="sxs-lookup"><span data-stu-id="79640-132">Click **More Options**.</span></span>

   - <span data-ttu-id="79640-133">Применяйте это правило, если : Выберите адрес получателя включает любое из этих слов. В диалоговом окантовке "Укажите слова или фразы", введите одно из следующих значений, нажмите кнопку Добавить значок добавить и повторите, пока не введите все  \>    ![ ](../../media/ITPro-EAC-AddIcon.png) значения.</span><span class="sxs-lookup"><span data-stu-id="79640-133">**Apply this rule if**: Select **The recipient** \> **address includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `not_junk@office365.microsoft.com`

     <span data-ttu-id="79640-134">Чтобы изменить запись, выберите ее и нажмите **кнопку Изменить значок Изменить** ![ ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="79640-134">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="79640-135">Чтобы удалить запись, выберите ее и нажмите **кнопку Удалить значок Удалить** ![ ](../../media/ITPro-EAC-DeleteIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="79640-135">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

     <span data-ttu-id="79640-136">После этого нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="79640-136">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="79640-137">**Сделайте следующее:** **Выберите добавление получателей** \> **в поле Bcc**.</span><span class="sxs-lookup"><span data-stu-id="79640-137">**Do the following**: Select **Add recipients** \> **to the Bcc box**.</span></span> <span data-ttu-id="79640-138">В диалоговом окантове, который отображается, найдите и выберите получателей, которые необходимо добавить.</span><span class="sxs-lookup"><span data-stu-id="79640-138">In the dialog that appears, find and select the recipients that you want to add.</span></span> <span data-ttu-id="79640-139">После этого нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="79640-139">When you're finished, click **OK**.</span></span>

4. <span data-ttu-id="79640-140">Вы можете сделать дополнительные выборы для аудита правила, проверки правила, активации правила в течение определенного периода времени и других параметров.</span><span class="sxs-lookup"><span data-stu-id="79640-140">You can make additional selections to audit the rule, test the rule, activate the rule during a specific time period, and other settings.</span></span> <span data-ttu-id="79640-141">Мы рекомендуем тестировать правило перед его выполнением.</span><span class="sxs-lookup"><span data-stu-id="79640-141">We recommend testing the rule before you enforce it.</span></span>

5. <span data-ttu-id="79640-142">По завершении нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="79640-142">When you're finished, click **Save**.</span></span>

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="79640-143">Использование PowerShell для создания правила потока почты для получения копий сообщений с сообщениями</span><span class="sxs-lookup"><span data-stu-id="79640-143">Use PowerShell to create a mail flow rule to receive copies of reported messages</span></span>

<span data-ttu-id="79640-144">В этом примере создается новое правило потока почты с именем Bcc Messages Reported to Microsoft, которое ищет сообщения электронной почты, которые сообщаются Корпорации Майкрософт с помощью методов, описанных в этой статье, и добавляет пользователей laura@contoso.com и julia@contoso.com в качестве получателей Bcc.</span><span class="sxs-lookup"><span data-stu-id="79640-144">This example creates a new mail flow rule named Bcc Messages Reported to Microsoft that looks for email messages that are reported to Microsoft by using the methods described in this article, and adds the users laura@contoso.com and julia@contoso.com as Bcc recipients.</span></span>

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

<span data-ttu-id="79640-145">Дополнительные сведения о синтаксисе и параметрах см. в статье [New-TransportRule](/powershell/module/exchange/new-transportrule).</span><span class="sxs-lookup"><span data-stu-id="79640-145">For detailed syntax and parameter information, see [New-TransportRule](/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="79640-146">Как убедиться, что все получилось?</span><span class="sxs-lookup"><span data-stu-id="79640-146">How do you know this worked?</span></span>

<span data-ttu-id="79640-147">Чтобы убедиться, что вы настроили правила потока почты для получения копий сообщений, сделайте все следующие действия:</span><span class="sxs-lookup"><span data-stu-id="79640-147">To verify that you've configured a mail flow rules to receive copies of reported messages, do any of the following steps:</span></span>

- <span data-ttu-id="79640-148">В EAC перейдите к **правилу потока почты** выберите правило \>  \> \> нажмите кнопку Изменить значок **Редактирование** ![ и проверьте ](../../media/ITPro-EAC-EditIcon.png) параметры.</span><span class="sxs-lookup"><span data-stu-id="79640-148">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="79640-149">В PowerShell запустите следующую команду для проверки параметров:</span><span class="sxs-lookup"><span data-stu-id="79640-149">In PowerShell, run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- <span data-ttu-id="79640-150">Отправьте тестовые сообщения на один из адресов электронной почты отчетов и убедитесь в результатах.</span><span class="sxs-lookup"><span data-stu-id="79640-150">Send a test messages to one of the reporting email addresses and verify the results.</span></span>