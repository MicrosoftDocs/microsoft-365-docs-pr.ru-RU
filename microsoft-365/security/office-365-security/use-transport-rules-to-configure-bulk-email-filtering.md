---
title: Использование правил потока почты для фильтрации массовой электронной почты
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
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: Администраторы могут узнать, как использовать правила потока почты (правила транспорта) для идентификации и фильтрации массовой почты (серой почты) в Exchange Online Protection (EOP).
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c86f229d6c7371854878a67937cc38374ed00961
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206068"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-eop"></a><span data-ttu-id="49368-103">Использование правил потока почты для фильтрации массовой рассылки в EOP</span><span class="sxs-lookup"><span data-stu-id="49368-103">Use mail flow rules to filter bulk email in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="49368-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="49368-104">**Applies to**</span></span>
- [<span data-ttu-id="49368-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="49368-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="49368-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="49368-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="49368-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="49368-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="49368-108">В организациях Microsoft 365 с почтовыми ящиками в Exchange Online или автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online EOP использует политики защиты от нежелательной почты (также известные как политики фильтра спама или политики фильтрации контента) для сканирования входящих сообщений для нежелательной почты и массовой почты (также известной как серая почта).</span><span class="sxs-lookup"><span data-stu-id="49368-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP uses anti-spam policies (also known as spam filter policies or content filter policies) to scan inbound messages for spam and bulk mail (also known as gray mail).</span></span> <span data-ttu-id="49368-109">Дополнительные сведения см. в статье [Настройка политик защиты от спама в EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="49368-109">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="49368-110">Если вы хотите использовать дополнительные параметры для фильтрации массовой почты, можно создать правила потока почты (также известные как правила транспорта) для поиска текстовых шаблонов или фраз, которые часто находятся в массовой почте, и пометить эти сообщения как спам.</span><span class="sxs-lookup"><span data-stu-id="49368-110">If you want more options to filter bulk mail, you can create mail flow rules (also known as transport rules) to search for text patterns or phrases that are frequently found in bulk mail, and mark those messages as spam.</span></span> <span data-ttu-id="49368-111">Дополнительные сведения о массовой почте см. в дополнительных сведениях о разнице между нежелательной электронной почтой и массовой электронной [почтой?](what-s-the-difference-between-junk-email-and-bulk-email.md) и уровнем массовой [жалобы (BCL) в EOP.](bulk-complaint-level-values.md)</span><span class="sxs-lookup"><span data-stu-id="49368-111">For more information about bulk mail, see [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md) and [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span></span>

<span data-ttu-id="49368-112">В этом разделе объясняется, как создавать эти правила потока почты в центре администрирования Exchange (EAC) и PowerShell (Exchange Online PowerShell для организаций Microsoft 365 с почтовыми ящиками в Exchange Online; автономные EOP PowerShell для организаций без почтовых ящиков Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="49368-112">This topic explains how create these mail flow rules in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="49368-113">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="49368-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="49368-114">Вам необходимо получить разрешения в Exchange Online или Exchange Online Protection, прежде чем вы сможете сделать процедуры в этой статье.</span><span class="sxs-lookup"><span data-stu-id="49368-114">You need to be assigned permissions in Exchange Online or Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="49368-115">В частности, вам  нужна роль Правил транспорта, которая по умолчанию назначена группам  ролей **"Управление** организацией",  "Управление соответствием требованиям" (глобальные администраторы) и "Управление записями".</span><span class="sxs-lookup"><span data-stu-id="49368-115">Specifically, you need the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management** (global admins), and **Records Management** role groups by default.</span></span>

  <span data-ttu-id="49368-116">Дополнительную информацию см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="49368-116">For more information, see the following topics:</span></span>

  - [<span data-ttu-id="49368-117">Разрешения в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="49368-117">Permissions in Exchange Online</span></span>](/exchange/permissions-exo/permissions-exo)
  - [<span data-ttu-id="49368-118">Разрешения в автономном EOP</span><span class="sxs-lookup"><span data-stu-id="49368-118">Permissions in standalone EOP</span></span>](feature-permissions-in-eop.md)
  - [<span data-ttu-id="49368-119">Использование EAC измените список участников в группах ролей</span><span class="sxs-lookup"><span data-stu-id="49368-119">Use the EAC modify the list of members in role groups</span></span>](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- <span data-ttu-id="49368-120">Чтобы открыть центр администрирования в Exchange Online, см. в центре [администрирования Exchange в Exchange Online.](/Exchange/exchange-admin-center)</span><span class="sxs-lookup"><span data-stu-id="49368-120">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](/Exchange/exchange-admin-center).</span></span> <span data-ttu-id="49368-121">Чтобы открыть EAC в автономных EOP, см. в центре администрирования Exchange в режиме [автономный EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="49368-121">To open the EAC in standalone EOP, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="49368-122">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="49368-122">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="49368-123">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="49368-123">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="49368-124">Дополнительные сведения о правилах потока почты в Exchange Online и автономных EOP см. в следующих темах:</span><span class="sxs-lookup"><span data-stu-id="49368-124">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>

  - [<span data-ttu-id="49368-125">Правила потока обработки почты (правила транспорта) в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="49368-125">Mail flow rules (transport rules) in Exchange Online</span></span>](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="49368-126">Условия и исключения правил потока почты (предикаты) в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="49368-126">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="49368-127">Действия правила потока почты в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="49368-127">Mail flow rule actions in Exchange Online</span></span>](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- <span data-ttu-id="49368-128">Список слов и текстовых шаблонов, используемых для идентификации массовой почты в примерах, не является исчерпывающим; при необходимости можно добавлять и удалять записи.</span><span class="sxs-lookup"><span data-stu-id="49368-128">The list of words and text patterns that are used to identify bulk mail in the examples aren't exhaustive; you can add and remove entries as necessary.</span></span> <span data-ttu-id="49368-129">Тем не менее, они являются хорошей отправной точкой.</span><span class="sxs-lookup"><span data-stu-id="49368-129">However, they are a good starting point.</span></span>

- <span data-ttu-id="49368-p107">Поиск слов и текстовых шаблонов в теме или других полях заголовка сообщения выполняется *после* расшифровки сообщения, к которому применялся метод кодирования для передачи сообщений MIME. Этот метод используется для передачи двоичных сообщений между SMTP-серверами с преобразованием их в текст ASCII. Вы не можете применять условия или исключения для поиска необработанных закодированных значений (обычно в формате Base64) в теме или других полях заголовка сообщения.</span><span class="sxs-lookup"><span data-stu-id="49368-p107">The search for words or text patterns in the subject or other header fields in the message occurs *after* the message has been decoded from the MIME content transfer encoding method that was used to transmit the binary message between SMTP servers in ASCII text. You can't use conditions or exceptions to search for the raw (typically, Base64) encoded values of the subject or other header fields in messages.</span></span>

- <span data-ttu-id="49368-132">Следующие процедуры отмечают массовое сообщение как спам для всей организации.</span><span class="sxs-lookup"><span data-stu-id="49368-132">The following procedures mark a bulk message as spam for your entire organization.</span></span> <span data-ttu-id="49368-133">Однако можно добавить еще одно условие, чтобы применять эти правила только к конкретным получателям, чтобы можно было использовать агрессивный фильтрацию для нескольких пользователей с высокой целевой аудиторией, в то время как остальные пользователи (которые в основном получают массовое письмо, на которое они подписались) не влияют.</span><span class="sxs-lookup"><span data-stu-id="49368-133">However, you can add another condition to apply these rules only to specific recipients, so you can use aggressive filtering on a few, highly targeted users, while the rest of your users (who mostly get the bulk email they signed up for) aren't impacted.</span></span>

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="49368-134">Используйте EAC для создания правил потока почты, фильтруя массовую электронную почту</span><span class="sxs-lookup"><span data-stu-id="49368-134">Use the EAC to create mail flow rules that filter bulk email</span></span>

1. <span data-ttu-id="49368-135">В Центре администрирования Exchange перейдите в раздел **Поток обработки почты** \> **Правила**.</span><span class="sxs-lookup"><span data-stu-id="49368-135">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="49368-136">Нажмите **кнопку Добавить** ![ значок Добавить, ](../../media/ITPro-EAC-AddIcon.png) а затем выберите Создать новое **правило**.</span><span class="sxs-lookup"><span data-stu-id="49368-136">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="49368-137">На открывшейся странице **Новое правило** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="49368-137">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="49368-138">**Имя.** Введите уникальное, описательное имя для правила.</span><span class="sxs-lookup"><span data-stu-id="49368-138">**Name**: Enter a unique, descriptive name for the rule.</span></span>

   - <span data-ttu-id="49368-139">Нажмите кнопку **Дополнительные параметры**.</span><span class="sxs-lookup"><span data-stu-id="49368-139">Click **More Options**.</span></span>

   - <span data-ttu-id="49368-140">**Применить это правило,** если: настройте один из следующих параметров, чтобы искать контент в сообщениях с помощью регулярных выражений (RegEx) или слов или фраз:</span><span class="sxs-lookup"><span data-stu-id="49368-140">**Apply this rule if**: Configure one of the following settings to look for content in messages using regular expressions (RegEx) or words or phrases:</span></span>

     - <span data-ttu-id="49368-141">**Субъект или тело** \> **тема** или тело совпадает с этими  текстовыми шаблонами. В диалоговом окте "Укажите слова или фразы", введите одно из следующих значений, нажмите кнопку **Добавить** значок добавить и повторите, пока не введите все ![ ](../../media/ITPro-EAC-AddIcon.png) значения.</span><span class="sxs-lookup"><span data-stu-id="49368-141">**The subject or body** \> **subject or body matches these text patterns**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

       - `If you are unable to view the content of this email\, please`
       - `\>(safe )?unsubscribe( here)?\</a\>`
       - `If you do not wish to receive further communications like this\, please`
       - `<img height="?1"? width="?1"? src=.?http\://`
       - `To stop receiving these+emails\:http\://`
       - `To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)`
       - `no longer (wish )?(to )?(be sent|receive) w+ email`
       - `If you are unable to view the content of this email\, please click here`
       - `To ensure you receive (your daily deals|our e-?mails)\, add`
       - `If you no longer wish to receive these emails`
       - `to change your (subscription preferences|preferences or unsubscribe)`
       - `click (here to|the) unsubscribe`

      <span data-ttu-id="49368-142">Чтобы изменить запись, выберите ее и нажмите **кнопку Изменить значок Изменить** ![ ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="49368-142">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="49368-143">Чтобы удалить запись, выберите ее и нажмите **кнопку Удалить значок Удалить** ![ ](../../media/ITPro-EAC-DeleteIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="49368-143">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="49368-144">После этого нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="49368-144">When you're finished, click **OK**.</span></span>

     - <span data-ttu-id="49368-145">**Субъект или тело** \> **тема** или тело включает любое из  этих слов. В диалоговом окантовке "Укажите слова или фразы", введите одно из следующих значений, нажмите кнопку **Добавить** значок добавить и повторите, пока не введите все ![ ](../../media/ITPro-EAC-AddIcon.png) значения.</span><span class="sxs-lookup"><span data-stu-id="49368-145">**The subject or body** \> **subject or body includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

       - `to change your preferences or unsubscribe`
       - `Modify email preferences or unsubscribe`
       - `This is a promotional email`
       - `You are receiving this email because you requested a subscription`
       - `click here to unsubscribe`
       - `You have received this email because you are subscribed`
       - `If you no longer wish to receive our email newsletter`
       - `to unsubscribe from this newsletter`
       - `If you have trouble viewing this email`
       - `This is an advertisement`
       - `you would like to unsubscribe or change your`
       - `view this email as a webpage`
       - `You are receiving this email because you are subscribed`

      <span data-ttu-id="49368-146">Чтобы изменить запись, выберите ее и нажмите **кнопку Изменить значок Изменить** ![ ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="49368-146">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="49368-147">Чтобы удалить запись, выберите ее и нажмите **кнопку Удалить значок Удалить** ![ ](../../media/ITPro-EAC-DeleteIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="49368-147">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="49368-148">После этого нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="49368-148">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="49368-149">**У следующих**: **Выберите Изменение свойств сообщения** установить уровень доверия нежелательной почты \> **(SCL).**</span><span class="sxs-lookup"><span data-stu-id="49368-149">**Do the following**: Select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span> <span data-ttu-id="49368-150">В **диалоговом окантовке Указать SCL,** который отображается, настройте один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="49368-150">In the **Specify SCL** dialog that appears, configure one of the following settings:</span></span>

     - <span data-ttu-id="49368-151">Чтобы отметить сообщения как **спам,** выберите **6**.</span><span class="sxs-lookup"><span data-stu-id="49368-151">To mark messages as **Spam**, select **6**.</span></span> <span data-ttu-id="49368-152">Действие, настроенное для вердиктов фильтрации нежелательной почты в политиках по борьбе со спамом, применяется к сообщениям (по умолчанию значение **Move message to Junk Email folder).** </span><span class="sxs-lookup"><span data-stu-id="49368-152">The action that you've configured for **Spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

     - <span data-ttu-id="49368-153">Для маркировки сообщений в качестве **нежелательной почты высокой уверенности** выберите **9**.</span><span class="sxs-lookup"><span data-stu-id="49368-153">To mark messages as **High confidence spam** select **9**.</span></span> <span data-ttu-id="49368-154">Действие, настроенное для вердиктов о фильтрации нежелательной почты с высоким уровнем доверия в политиках по борьбе со спамом, применяется к сообщениям (по умолчанию значение **Move message to Junk Email folder).** </span><span class="sxs-lookup"><span data-stu-id="49368-154">The action that you've configured for **High confidence spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

    <span data-ttu-id="49368-155">Дополнительные сведения о значениях SCL см. в сообщении уровня доверия к нежелательной почте [(SCL) в EOP.](spam-confidence-levels.md)</span><span class="sxs-lookup"><span data-stu-id="49368-155">For more information about SCL values, see [Spam confidence level (SCL) in EOP](spam-confidence-levels.md).</span></span>

   <span data-ttu-id="49368-156">По завершению нажмите кнопку **Сохранить**</span><span class="sxs-lookup"><span data-stu-id="49368-156">When you're finished, click **Save**</span></span>

## <a name="use-powershell-to-create-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="49368-157">Используйте PowerShell для создания правил потока почты, которые фильтруют массовую электронную почту</span><span class="sxs-lookup"><span data-stu-id="49368-157">Use PowerShell to create mail flow rules that filter bulk email</span></span>

<span data-ttu-id="49368-158">Используйте следующий синтаксис для создания одного или обоих правил потока почты (регулярные выражения и слова):</span><span class="sxs-lookup"><span data-stu-id="49368-158">Use the following syntax to create one or both of the mail flow rules (regular expressions vs. words):</span></span>

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPhrase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

<span data-ttu-id="49368-159">В этом примере создается новое правило с именем "Массовая фильтрация электронной почты - RegEx", которое использует тот же список регулярных выражений из более ранних разделов для набора сообщений, как **спам**.</span><span class="sxs-lookup"><span data-stu-id="49368-159">This example creates a new rule named "Bulk email filtering - RegEx" that uses the same list of regular expressions from earlier in the topic to set messages as **Spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? src=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

<span data-ttu-id="49368-160">В этом примере создается новое правило с именем "Массовая фильтрация электронной почты - слова", которое использует тот же список слов из более ранних разделов для набора сообщений, как спам высокой **уверенности**.</span><span class="sxs-lookup"><span data-stu-id="49368-160">This example creates a new rule named "Bulk email filtering - Words" that uses the same list of words from earlier in the topic to set messages as **High confidence spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

<span data-ttu-id="49368-161">Дополнительные сведения о синтаксисе и параметрах см. в статье [New-TransportRule](/powershell/module/exchange/new-transportrule).</span><span class="sxs-lookup"><span data-stu-id="49368-161">For detailed syntax and parameter information, see [New-TransportRule](/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="49368-162">Как убедиться, что все получилось?</span><span class="sxs-lookup"><span data-stu-id="49368-162">How do you know this worked?</span></span>

<span data-ttu-id="49368-163">Чтобы убедиться, что вы настроили правила потока почты для фильтрации массовой почты, сделайте все следующие действия:</span><span class="sxs-lookup"><span data-stu-id="49368-163">To verify that you've configured mail flow rules to filter bulk email, do any of the following steps:</span></span>

- <span data-ttu-id="49368-164">В EAC перейдите к **правилу потока почты** выберите правило \>  \> \> нажмите кнопку Изменить значок **Редактирование** ![ и проверьте ](../../media/ITPro-EAC-EditIcon.png) параметры.</span><span class="sxs-lookup"><span data-stu-id="49368-164">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="49368-165">В PowerShell замените имя правила и запустите следующую команду для \<Rule Name\> проверки параметров:</span><span class="sxs-lookup"><span data-stu-id="49368-165">In PowerShell, replace \<Rule Name\> with the name of the rule, and run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- <span data-ttu-id="49368-166">Из внешней учетной записи отправьте тестовые сообщения пострадавшему получателю, содержаму одну из фраз или текстовых шаблонов, и убедитесь в результатах.</span><span class="sxs-lookup"><span data-stu-id="49368-166">From an external account, send a test messages to an affected recipient that contains one of the phrases or text patterns, and verify the results.</span></span>