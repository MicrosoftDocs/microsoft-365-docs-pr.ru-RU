---
title: Просмотр отчетов, передаваемых пользователями в Майкрософт, с помощью правил для потока обработки почты
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: Администраторы могут научиться использовать правила потока почты (также известные как правила транспорта) для получения копий сообщений, которые пользователи сообщают корпорации Майкрософт.
ms.openlocfilehash: ec7145b68548bb5e1d6841387a18e86b74ec2a78
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751575"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a><span data-ttu-id="28fbf-103">Просмотр отчетов, передаваемых пользователями в Майкрософт, с помощью правил для потока обработки почты</span><span class="sxs-lookup"><span data-stu-id="28fbf-103">Use mail flow rules to see what your users are reporting to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="28fbf-104">В организациях Microsoft 365 с почтовыми ящиками в Организациях Exchange Online или автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online существует несколько способов передачи сообщений в корпорацию Майкрософт для анализа, как описано в отчете о сообщениях и файлах в [корпорацию Майкрософт.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="28fbf-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there are multiple ways for users to report messages to Microsoft for analysis as described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

<span data-ttu-id="28fbf-105">Можно создать правило потока почты (также известное как правило транспорта), которое ищет сообщения, которые пользователи сообщают корпорации Майкрософт, и настроить получателей копии этих сообщений.</span><span class="sxs-lookup"><span data-stu-id="28fbf-105">You can create a mail flow rule (also known as a transport rule) that looks for messages that users report to Microsoft, and you can configure Bcc recipients to receive copies of these reported messages.</span></span>

<span data-ttu-id="28fbf-106">Правило потока обработки почты можно создать в Центре администрирования Exchange (EAC) и PowerShell (Exchange Online PowerShell для организаций Microsoft 365 с почтовыми ящиками в Exchange Online; автономный EOP PowerShell для организаций без почтовых ящиков Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="28fbf-106">You can create the mail flow rule in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="28fbf-107">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="28fbf-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="28fbf-108">Для этого необходимы соответствующие разрешения в Exchange Online или Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="28fbf-108">You need to be assigned permissions in Exchange Online or Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="28fbf-109">В частности, необходима  роль правил транспорта, назначенная по умолчанию группам ролей "Управление  организацией", "Управление соответствием требованиям" **(глобальным** администраторам) и "Управление записями".</span><span class="sxs-lookup"><span data-stu-id="28fbf-109">Specifically, you need the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management** (global admins), and **Records Management** role groups by default.</span></span>

  <span data-ttu-id="28fbf-110">Дополнительную информацию см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="28fbf-110">For more information, see the following topics:</span></span>

  - [<span data-ttu-id="28fbf-111">Разрешения в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="28fbf-111">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)
  - [<span data-ttu-id="28fbf-112">Разрешения в автономном EOP</span><span class="sxs-lookup"><span data-stu-id="28fbf-112">Permissions in standalone EOP</span></span>](feature-permissions-in-eop.md)
  - [<span data-ttu-id="28fbf-113">Изменение списка участников в группах ролей с помощью EAC</span><span class="sxs-lookup"><span data-stu-id="28fbf-113">Use the EAC modify the list of members in role groups</span></span>](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- <span data-ttu-id="28fbf-114">Чтобы открыть Центр администрирования Exchange в Exchange Online, см. центр [администрирования Exchange в Exchange Online.](https://docs.microsoft.com/Exchange/exchange-admin-center)</span><span class="sxs-lookup"><span data-stu-id="28fbf-114">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span> <span data-ttu-id="28fbf-115">Чтобы открыть Центр администрирования Exchange в режиме автономных EOP, см. центр администрирования [Exchange в режиме автономных EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="28fbf-115">To open the EAC in standalone EOP, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="28fbf-116">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="28fbf-116">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="28fbf-117">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="28fbf-117">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="28fbf-118">Дополнительные сведения о правилах потока почты в Exchange Online и автономных EOP см. в следующих темах:</span><span class="sxs-lookup"><span data-stu-id="28fbf-118">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>
  - [<span data-ttu-id="28fbf-119">Правила потока обработки почты (правила транспорта) в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="28fbf-119">Mail flow rules (transport rules) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)
  - [<span data-ttu-id="28fbf-120">Условия и исключения правил потока почты (предикаты) в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="28fbf-120">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)
  - [<span data-ttu-id="28fbf-121">Действия правил потока почты в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="28fbf-121">Mail flow rule actions in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="28fbf-122">Создание правила потока почты для получения копий сообщений с помощью EAC</span><span class="sxs-lookup"><span data-stu-id="28fbf-122">Use the EAC to create a mail flow rule to receive copies of reported messages</span></span>

1. <span data-ttu-id="28fbf-123">В Центре администрирования Exchange перейдите в раздел **Поток обработки почты** \> **Правила**.</span><span class="sxs-lookup"><span data-stu-id="28fbf-123">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="28fbf-124">Щелкните **значок** ![ "Добавить", ](../../media/ITPro-EAC-AddIcon.png) а затем выберите **"Создать новое правило".**</span><span class="sxs-lookup"><span data-stu-id="28fbf-124">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="28fbf-125">На открывшейся странице **Новое правило** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="28fbf-125">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="28fbf-126">**Name**: Enter a unique, descriptive name for the rule.</span><span class="sxs-lookup"><span data-stu-id="28fbf-126">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="28fbf-127">Например, "Сообщения в ск", которые были подались в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="28fbf-127">For example, Bcc Messages Reported to Microsoft.</span></span>

   - <span data-ttu-id="28fbf-128">Нажмите кнопку **Дополнительные параметры**.</span><span class="sxs-lookup"><span data-stu-id="28fbf-128">Click **More Options**.</span></span>

   - <span data-ttu-id="28fbf-129">Примените это правило, если **:** **Выберите** адрес получателя включает любое из этих слов: в отображемом диалоговом окке "Укажите слова или фразы" введите одно из следующих значений, нажмите кнопку "Добавить значок добавления" и повторите это, пока не введите все \>    ![ ](../../media/ITPro-EAC-AddIcon.png) значения.</span><span class="sxs-lookup"><span data-stu-id="28fbf-129">**Apply this rule if**: Select **The recipient** \> **address includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `not_junk@office365.microsoft.com`

     <span data-ttu-id="28fbf-130">Чтобы изменить запись, выберите  ее и нажмите значок ![ ](../../media/ITPro-EAC-EditIcon.png) редактирования.</span><span class="sxs-lookup"><span data-stu-id="28fbf-130">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="28fbf-131">Чтобы удалить запись, выберите ее и нажмите **значок "Удалить** ![ ](../../media/ITPro-EAC-DeleteIcon.png) удалить".</span><span class="sxs-lookup"><span data-stu-id="28fbf-131">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

     <span data-ttu-id="28fbf-132">После этого нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="28fbf-132">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="28fbf-133">**Сделайте следующее:** выберите **"Добавить получателей** \> **в поле "СК".**</span><span class="sxs-lookup"><span data-stu-id="28fbf-133">**Do the following**: Select **Add recipients** \> **to the Bcc box**.</span></span> <span data-ttu-id="28fbf-134">В отобратом диалоговом окте найдите и выберите получателей, которые нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="28fbf-134">In the dialog that appears, find and select the recipients that you want to add.</span></span> <span data-ttu-id="28fbf-135">После этого нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="28fbf-135">When you're finished, click **OK**.</span></span>

4. <span data-ttu-id="28fbf-136">Вы можете внести дополнительные параметры для аудита правила, проверить правило, активировать правило в течение определенного периода времени и другие параметры.</span><span class="sxs-lookup"><span data-stu-id="28fbf-136">You can make additional selections to audit the rule, test the rule, activate the rule during a specific time period, and other settings.</span></span> <span data-ttu-id="28fbf-137">Мы рекомендуем тестировать правило перед его выполнением.</span><span class="sxs-lookup"><span data-stu-id="28fbf-137">We recommend testing the rule before you enforce it.</span></span>

5. <span data-ttu-id="28fbf-138">Когда закончите, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="28fbf-138">When you're finished, click **Save**.</span></span>

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="28fbf-139">Создание правила потока почты для получения копий сообщений с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="28fbf-139">Use PowerShell to create a mail flow rule to receive copies of reported messages</span></span>

<span data-ttu-id="28fbf-140">В этом примере создается новое правило потока почты с именем Bcc Messages Reported to Microsoft, которое ищет сообщения электронной почты, которые сообщаются корпорации Майкрософт с помощью методов, описанных в этой статье, и добавляет пользователей laura@contoso.com и julia@contoso.com в качестве получателей ск.</span><span class="sxs-lookup"><span data-stu-id="28fbf-140">This example creates a new mail flow rule named Bcc Messages Reported to Microsoft that looks for email messages that are reported to Microsoft by using the methods described in this article, and adds the users laura@contoso.com and julia@contoso.com as Bcc recipients.</span></span>

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

<span data-ttu-id="28fbf-141">Дополнительные сведения о синтаксисе и параметрах см. в статье [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span><span class="sxs-lookup"><span data-stu-id="28fbf-141">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="28fbf-142">Как убедиться, что все получилось?</span><span class="sxs-lookup"><span data-stu-id="28fbf-142">How do you know this worked?</span></span>

<span data-ttu-id="28fbf-143">Чтобы убедиться, что вы настроили правила потока почты для получения копий сообщений с сообщениями, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="28fbf-143">To verify that you've configured a mail flow rules to receive copies of reported messages, do any of the following steps:</span></span>

- <span data-ttu-id="28fbf-144">В EAC перейдите к **правилу потока** обработки почты, выберите правило, щелкните значок редактирования и проверьте \>  \> \>  ![ ](../../media/ITPro-EAC-EditIcon.png) параметры.</span><span class="sxs-lookup"><span data-stu-id="28fbf-144">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="28fbf-145">В PowerShell запустите следующую команду, чтобы проверить параметры:</span><span class="sxs-lookup"><span data-stu-id="28fbf-145">In PowerShell, run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- <span data-ttu-id="28fbf-146">Отправьте тестовые сообщения на один из адресов электронной почты отчетов и проверьте результаты.</span><span class="sxs-lookup"><span data-stu-id="28fbf-146">Send a test messages to one of the reporting email addresses and verify the results.</span></span>
