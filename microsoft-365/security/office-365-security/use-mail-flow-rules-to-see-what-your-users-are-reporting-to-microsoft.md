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
description: Администраторы могут узнать, как использовать правила потока обработки почты (также называемые правилами транспорта) для получения копий сообщений, подказываемых пользователями в корпорацию Майкрософт.
ms.openlocfilehash: 1612adeefff21fa9f149de6537917dd9b8c50b00
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827389"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a><span data-ttu-id="c9f4f-103">Просмотр отчетов, передаваемых пользователями в Майкрософт, с помощью правил для потока обработки почты</span><span class="sxs-lookup"><span data-stu-id="c9f4f-103">Use mail flow rules to see what your users are reporting to Microsoft</span></span>

<span data-ttu-id="c9f4f-104">В организациях Microsoft 365 с почтовыми ящиками в Exchange Online или в автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online пользователи могут сообщать в корпорацию Майкрософт для анализа сообщения для анализа в соответствии с описанием в [отчетах о сообщениях и файлах в корпорацию Майкрософт.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="c9f4f-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there are multiple ways for users to report messages to Microsoft for analysis as described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

<span data-ttu-id="c9f4f-105">Вы можете создать правило потока обработки почты (также называемое правилом транспорта), которое будет искать сообщения, о которых пользователи передавают отчеты в корпорацию Майкрософт, и настроить получателей в поле "СК" на получение копий этих сообщений.</span><span class="sxs-lookup"><span data-stu-id="c9f4f-105">You can create a mail flow rule (also known as a transport rule) that looks for messages that users report to Microsoft, and you can configure Bcc recipients to receive copies of these reported messages.</span></span>

<span data-ttu-id="c9f4f-106">Вы можете создать правило потока обработки почты в Центре администрирования Exchange и PowerShell (Exchange Online PowerShell для организаций Microsoft 365 с почтовыми ящиками в Exchange Online; автономная оболочка PowerShell EOP для организаций без почтовых ящиков Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="c9f4f-106">You can create the mail flow rule in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c9f4f-107">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="c9f4f-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c9f4f-108">Для выполнения этих процедур необходимы права в Exchange Online или EOP.</span><span class="sxs-lookup"><span data-stu-id="c9f4f-108">You need to be assigned permissions in Exchange Online or EOP before you can do these procedures.</span></span> <span data-ttu-id="c9f4f-109">В частности, вам должна быть назначена роль **правил транспорта,** которая по умолчанию назначается **ролям управления**организацией, **Compliance Management** **управлением** соответствием требованиям и записями.</span><span class="sxs-lookup"><span data-stu-id="c9f4f-109">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="c9f4f-110">Дополнительные сведения см. в статье [Управление группами ролей в Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span><span class="sxs-lookup"><span data-stu-id="c9f4f-110">For more information, see [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

- <span data-ttu-id="c9f4f-111">Сведения о том, как открыть [Центр администрирования Exchange, см. в Центре администрирования Exchange в](https://docs.microsoft.com/Exchange/exchange-admin-center) Exchange Online или Центре администрирования Exchange в [автономной службе EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="c9f4f-111">To open the EAC, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center) or [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="c9f4f-112">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="c9f4f-112">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="c9f4f-113">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="c9f4f-113">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="c9f4f-114">Дополнительные сведения о правилах для потока обработки почты в Exchange Online и автономной службе EOP см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="c9f4f-114">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>

  - [<span data-ttu-id="c9f4f-115">Правила потока обработки почты (правила транспорта) в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="c9f4f-115">Mail flow rules (transport rules) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="c9f4f-116">Условия и исключения (предикаты) правил потока обработки почты в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="c9f4f-116">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="c9f4f-117">Действия правил обработки почтового потока в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="c9f4f-117">Mail flow rule actions in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="c9f4f-118">Создание правила потока обработки почты для получения копий отчетных сообщений с помощью Центра администрирования Exchange</span><span class="sxs-lookup"><span data-stu-id="c9f4f-118">Use the EAC to create a mail flow rule to receive copies of reported messages</span></span>

1. <span data-ttu-id="c9f4f-119">В Центре администрирования Exchange перейдите в раздел **Поток обработки почты** \> **Правила**.</span><span class="sxs-lookup"><span data-stu-id="c9f4f-119">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="c9f4f-120">Нажмите **кнопку** ![ "Добавить ](../../media/ITPro-EAC-AddIcon.png) значок "Добавить" и **выберите пункт "Создать правило".**</span><span class="sxs-lookup"><span data-stu-id="c9f4f-120">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="c9f4f-121">На открывшейся странице **Новое правило** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="c9f4f-121">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="c9f4f-122">**Имя:** введите уникальное, понятное имя правила.</span><span class="sxs-lookup"><span data-stu-id="c9f4f-122">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="c9f4f-123">Например, "Отправленные копии сообщения, отправленные в корпорацию Майкрософт".</span><span class="sxs-lookup"><span data-stu-id="c9f4f-123">For example, Bcc Messages Reported to Microsoft.</span></span>

   - <span data-ttu-id="c9f4f-124">Нажмите кнопку **Дополнительные параметры**.</span><span class="sxs-lookup"><span data-stu-id="c9f4f-124">Click **More Options**.</span></span>

   - <span data-ttu-id="c9f4f-125">**Правило применяется, если:** **выберите** адрес получателя, который содержит любое из следующих слов: в появившемся диалоговом окне "Укажите слова или фразы" введите одно из \> **address includes any of these words**следующих значений, нажмите **кнопку Добавить** **Specify words or phrases** ![ ](../../media/ITPro-EAC-AddIcon.png) значок и повторяйте, пока не введите все значения.</span><span class="sxs-lookup"><span data-stu-id="c9f4f-125">**Apply this rule if**: Select **The recipient** \> **address includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `false_positive@messaging.microsoft.com`

     <span data-ttu-id="c9f4f-126">Чтобы изменить запись, выберите ее и нажмите **значок** ![ ](../../media/ITPro-EAC-EditIcon.png) редактирования.</span><span class="sxs-lookup"><span data-stu-id="c9f4f-126">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="c9f4f-127">Чтобы удалить запись, выберите ее и нажмите **значок** ![ ](../../media/ITPro-EAC-DeleteIcon.png) "Удалить".</span><span class="sxs-lookup"><span data-stu-id="c9f4f-127">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

     <span data-ttu-id="c9f4f-128">После этого нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c9f4f-128">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="c9f4f-129">**Выполните следующие действия:** выберите **"Добавить** \> **получателей в поле "СК".**</span><span class="sxs-lookup"><span data-stu-id="c9f4f-129">**Do the following**: Select **Add recipients** \> **to the Bcc box**.</span></span> <span data-ttu-id="c9f4f-130">В появившемся диалоговом окне найдите и выберите нужных получателей.</span><span class="sxs-lookup"><span data-stu-id="c9f4f-130">In the dialog that appears, find and select the recipients that you want to add.</span></span> <span data-ttu-id="c9f4f-131">После этого нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c9f4f-131">When you're finished, click **OK**.</span></span>

4. <span data-ttu-id="c9f4f-132">Можно выбрать дополнительные параметры для аудита и проверки правила, его активации в течение определенного периода, а также настроить другие параметры.</span><span class="sxs-lookup"><span data-stu-id="c9f4f-132">You can make additional selections to audit the rule, test the rule, activate the rule during a specific time period, and other settings.</span></span> <span data-ttu-id="c9f4f-133">Рекомендуется протестировать правило перед его применением.</span><span class="sxs-lookup"><span data-stu-id="c9f4f-133">We recommend testing the rule before you enforce it.</span></span>

5. <span data-ttu-id="c9f4f-134">Выполнив необходимые действия, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="c9f4f-134">When you're finished, click **Save**.</span></span>

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="c9f4f-135">Создание правила потока обработки почты для получения копий отчетов с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="c9f4f-135">Use PowerShell to create a mail flow rule to receive copies of reported messages</span></span>

<span data-ttu-id="c9f4f-136">В этом примере показано, как создать новое правило для потока обработки почты, «Bcc Messages Reported to Microsoft», которое ищет электронные сообщения, о которых сообщаются корпорации Майкрософт, по средством, описанным в этой статье, а затем пользователи laura@contoso.com и julia@contoso.com в качестве получателей с книжкой.</span><span class="sxs-lookup"><span data-stu-id="c9f4f-136">This example creates a new mail flow rule named Bcc Messages Reported to Microsoft that looks for email messages that are reported to Microsoft by using the methods described in this topic, and adds the users laura@contoso.com and julia@contoso.com as Bcc recipients.</span></span>

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

<span data-ttu-id="c9f4f-137">Дополнительные сведения о синтаксисе и параметрах см. в статье [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span><span class="sxs-lookup"><span data-stu-id="c9f4f-137">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="c9f4f-138">Как убедиться, что все получилось?</span><span class="sxs-lookup"><span data-stu-id="c9f4f-138">How do you know this worked?</span></span>

<span data-ttu-id="c9f4f-139">Чтобы убедиться, что вы настроили правила потока обработки почты для получения копий сообщений из них, выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="c9f4f-139">To verify that you've configured a mail flow rules to receive copies of reported messages, do any of the following steps:</span></span>

- <span data-ttu-id="c9f4f-140">В Центре администрирования Exchange перейдите в раздел **"Правила** \> **потока обработки** \> почты" и \> выберите правило на значок **Edit** ![ "Изменить ](../../media/ITPro-EAC-EditIcon.png) изменить" и проверьте параметры.</span><span class="sxs-lookup"><span data-stu-id="c9f4f-140">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="c9f4f-141">В PowerShell выполните следующую команду, чтобы проверить параметры:</span><span class="sxs-lookup"><span data-stu-id="c9f4f-141">In PowerShell, run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- <span data-ttu-id="c9f4f-142">Отправьте тестовые сообщения на один из электронных адресов в отчетах и проверьте результаты.</span><span class="sxs-lookup"><span data-stu-id="c9f4f-142">Send a test messages to one of the reporting email addresses and verify the results.</span></span>
