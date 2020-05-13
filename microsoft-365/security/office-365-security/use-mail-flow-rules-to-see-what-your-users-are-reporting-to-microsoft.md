---
title: Просмотр отчетов, передаваемых пользователями в Майкрософт, с помощью правил для потока обработки почты
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: Администраторы могут узнать, как использовать правила поток обработки почты (также называемые правилами транспорта), чтобы получать копии сообщений, отправляемых пользователями в корпорацию Майкрософт.
ms.openlocfilehash: faafd8fb750259c192807349b63eee14279179de
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208577"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a><span data-ttu-id="e8d60-103">Просмотр отчетов, передаваемых пользователями в Майкрософт, с помощью правил для потока обработки почты</span><span class="sxs-lookup"><span data-stu-id="e8d60-103">Use mail flow rules to see what your users are reporting to Microsoft</span></span>

<span data-ttu-id="e8d60-104">В организациях Microsoft 365 с почтовыми ящиками в организациях Exchange Online или Exchange Online Protection (EOP) без почтовых ящиков Exchange Online пользователи могут отчитываться о сообщениях в Майкрософт для анализа, как описано в [статье Reports and Files to Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="e8d60-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there are multiple ways for users to report messages to Microsoft for analysis as described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

<span data-ttu-id="e8d60-105">Вы можете создать правило для процесса обработки почты (также называемое правилом транспорта), которое будет искать сообщения, отправляемые пользователями в корпорацию Майкрософт, и настраивать получателей скрытой копии для получения копий этих сообщений.</span><span class="sxs-lookup"><span data-stu-id="e8d60-105">You can create a mail flow rule (also known as a transport rule) that looks for messages that users report to Microsoft, and you can configure Bcc recipients to receive copies of these reported messages.</span></span>

<span data-ttu-id="e8d60-106">Вы можете создать правило для почтового процесса в центре администрирования Exchange и PowerShell (Exchange Online PowerShell для Microsoft 365 организации с почтовыми ящиками в Exchange Online; изолированный EOP PowerShell для организаций без почтовых ящиков Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="e8d60-106">You can create the mail flow rule in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e8d60-107">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="e8d60-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e8d60-108">Прежде чем выполнять эти процедуры, необходимо назначить разрешения в Exchange Online или EOP.</span><span class="sxs-lookup"><span data-stu-id="e8d60-108">You need to be assigned permissions in Exchange Online or EOP before you can do these procedures.</span></span> <span data-ttu-id="e8d60-109">В частности, необходимо назначить роль " **правила транспорта** ", которая назначается для ролей управления **организацией**, **управления соответствием требованиям**и управления **записями** по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e8d60-109">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="e8d60-110">Дополнительные сведения см. в статье [Управление группами ролей в Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span><span class="sxs-lookup"><span data-stu-id="e8d60-110">For more information, see [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

- <span data-ttu-id="e8d60-111">Чтобы открыть центр администрирования Exchange, ознакомьтесь со статьей [центр администрирования Exchange в Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center) или [центр администрирования Exchange в автономной EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="e8d60-111">To open the EAC, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center) or [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="e8d60-112">Сведения о подключении к Exchange Online PowerShell см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="e8d60-112">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="e8d60-113">Сведения о подключении к автономной службе Exchange Online Protection PowerShell см. в статье [Подключение к PowerShell для Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="e8d60-113">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="e8d60-114">Дополнительные сведения о правилах обработки почтового ящика в Exchange Online и отдельном EOP содержатся в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="e8d60-114">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>

  - [<span data-ttu-id="e8d60-115">Правила потока обработки почты (правила транспорта) в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e8d60-115">Mail flow rules (transport rules) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="e8d60-116">Условия и исключения правила для обработки почтового процесса (предикаты) в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e8d60-116">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="e8d60-117">Действия правил обработки почты в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e8d60-117">Mail flow rule actions in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="e8d60-118">Использование центра администрирования Exchange для создания правила обработки почтового ящика для получения копий отчетных сообщений</span><span class="sxs-lookup"><span data-stu-id="e8d60-118">Use the EAC to create a mail flow rule to receive copies of reported messages</span></span>

1. <span data-ttu-id="e8d60-119">В Центре администрирования Exchange перейдите в раздел **Поток обработки почты** \> **Правила**.</span><span class="sxs-lookup"><span data-stu-id="e8d60-119">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="e8d60-120">Щелкните **Добавить** ![ значок Добавить ](../../media/ITPro-EAC-AddIcon.png) , а затем выберите **создать новое правило**.</span><span class="sxs-lookup"><span data-stu-id="e8d60-120">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="e8d60-121">На открывшейся странице **Новое правило** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="e8d60-121">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="e8d60-122">**Name**: введите уникальное описательное имя правила.</span><span class="sxs-lookup"><span data-stu-id="e8d60-122">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="e8d60-123">Например, сообщения скрытой копии в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="e8d60-123">For example, Bcc Messages Reported to Microsoft.</span></span>

   - <span data-ttu-id="e8d60-124">Нажмите кнопку **Дополнительные параметры**.</span><span class="sxs-lookup"><span data-stu-id="e8d60-124">Click **More Options**.</span></span>

   - <span data-ttu-id="e8d60-125">**Применять это правило, если**: выберите адрес **получателя** \> **содержит любое из этих слов**: в появившемся диалоговом окне **Укажите слова или фразы** введите одно из следующих значений, нажмите **Добавить** ![ значок "Добавить" ](../../media/ITPro-EAC-AddIcon.png) и повторяйте до тех пор, пока не ввели все значения.</span><span class="sxs-lookup"><span data-stu-id="e8d60-125">**Apply this rule if**: Select **The recipient** \> **address includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `false_positive@messaging.microsoft.com`

     <span data-ttu-id="e8d60-126">Чтобы изменить запись, выберите ее и нажмите кнопку **изменить** ![ значок редактирования ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="e8d60-126">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="e8d60-127">Чтобы удалить запись, выберите ее и нажмите кнопку **Удалить** ![ значок "Удалить" ](../../media/ITPro-EAC-DeleteIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="e8d60-127">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

     <span data-ttu-id="e8d60-128">После этого нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e8d60-128">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="e8d60-129">**Выполните следующие**действия: выберите **добавить получателей** \> **в поле "СК**".</span><span class="sxs-lookup"><span data-stu-id="e8d60-129">**Do the following**: Select **Add recipients** \> **to the Bcc box**.</span></span> <span data-ttu-id="e8d60-130">В появившемся диалоговом окне найдите и выберите получателей, которых вы хотите добавить.</span><span class="sxs-lookup"><span data-stu-id="e8d60-130">In the dialog that appears, find and select the recipients that you want to add.</span></span> <span data-ttu-id="e8d60-131">После этого нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e8d60-131">When you're finished, click **OK**.</span></span>

4. <span data-ttu-id="e8d60-132">Вы можете выбрать дополнительные параметры для аудита правила, проверки правила, активации правила в течение определенного периода времени и других параметров.</span><span class="sxs-lookup"><span data-stu-id="e8d60-132">You can make additional selections to audit the rule, test the rule, activate the rule during a specific time period, and other settings.</span></span> <span data-ttu-id="e8d60-133">Рекомендуем проверить правило перед его применением.</span><span class="sxs-lookup"><span data-stu-id="e8d60-133">We recommend testing the rule before you enforce it.</span></span>

5. <span data-ttu-id="e8d60-134">Выполнив необходимые действия, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="e8d60-134">When you're finished, click **Save**.</span></span>

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="e8d60-135">Создание правила для обработки почтового сообщения для получения копий отчетов с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="e8d60-135">Use PowerShell to create a mail flow rule to receive copies of reported messages</span></span>

<span data-ttu-id="e8d60-136">В этом примере создается правило для почтового процесса с именем BCC messages, отправленное в корпорацию Майкрософт, которое ищет сообщения электронной почты, сообщаемые в корпорацию Майкрософт, с помощью методов, описанных в этом разделе, и добавляет пользователей laura@contoso.com и julia@contoso.com как получателей скрытой копии.</span><span class="sxs-lookup"><span data-stu-id="e8d60-136">This example creates a new mail flow rule named Bcc Messages Reported to Microsoft that looks for email messages that are reported to Microsoft by using the methods described in this topic, and adds the users laura@contoso.com and julia@contoso.com as Bcc recipients.</span></span>

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

<span data-ttu-id="e8d60-137">Дополнительные сведения о синтаксисе и параметрах см. в статье [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).</span><span class="sxs-lookup"><span data-stu-id="e8d60-137">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="e8d60-138">Как убедиться, что все получилось?</span><span class="sxs-lookup"><span data-stu-id="e8d60-138">How do you know this worked?</span></span>

<span data-ttu-id="e8d60-139">Чтобы убедиться, что вы настроили правила обработки почты для получения копий сообщений, выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="e8d60-139">To verify that you've configured a mail flow rules to receive copies of reported messages, do any of the following steps:</span></span>

- <span data-ttu-id="e8d60-140">В центре администрирования Exchange перейдите к разделу правила для обработки **почтового ящика** , \> **Rules** \> выберите правило \> щелкните **изменить** ![ значок редактирования ](../../media/ITPro-EAC-EditIcon.png) и проверьте параметры.</span><span class="sxs-lookup"><span data-stu-id="e8d60-140">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="e8d60-141">В PowerShell выполните следующую команду, чтобы проверить параметры:</span><span class="sxs-lookup"><span data-stu-id="e8d60-141">In PowerShell, run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- <span data-ttu-id="e8d60-142">Отправьте тестовые сообщения на один из электронных адресов отчетов и проверьте результаты.</span><span class="sxs-lookup"><span data-stu-id="e8d60-142">Send a test messages to one of the reporting email addresses and verify the results.</span></span>
