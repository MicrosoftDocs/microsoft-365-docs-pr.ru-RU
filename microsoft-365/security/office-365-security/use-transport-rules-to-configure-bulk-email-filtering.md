---
title: Использование правил потока почты для фильтрации массовых рассылок
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
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: Администраторы могут научиться использовать правила потока почты (правила транспорта) для идентификации и фильтрации массовой почты (серой почты) в Exchange Online Protection (EOP).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b029e805147218551ba6ff80fb5abfda3fbfef7f
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658641"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-eop"></a><span data-ttu-id="ea4fa-103">Использование правил потока почты для фильтрации массовой рассылки в EOP</span><span class="sxs-lookup"><span data-stu-id="ea4fa-103">Use mail flow rules to filter bulk email in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="ea4fa-104">В организациях Microsoft 365 с почтовыми ящиками в Организациях Exchange Online или автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online EOP использует политики защиты от нежелательной почты (также известные как политики фильтрации нежелательной почты или политики фильтрации содержимого) для проверки входящих сообщений на спам и массовой рассылки (также известной как серая почта).</span><span class="sxs-lookup"><span data-stu-id="ea4fa-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP uses anti-spam policies (also known as spam filter policies or content filter policies) to scan inbound messages for spam and bulk mail (also known as gray mail).</span></span> <span data-ttu-id="ea4fa-105">Дополнительные сведения см. в статье [Настройка политик защиты от спама в EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="ea4fa-105">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="ea4fa-106">Если вам нужны дополнительные параметры фильтрации массовой почты, можно создать правила потока почты (также известные как правила транспорта) для поиска текстовых шаблонов или фраз, которые часто используются в массовой рассылке, и пометить эти сообщения как нежелательные.</span><span class="sxs-lookup"><span data-stu-id="ea4fa-106">If you want more options to filter bulk mail, you can create mail flow rules (also known as transport rules) to search for text patterns or phrases that are frequently found in bulk mail, and mark those messages as spam.</span></span> <span data-ttu-id="ea4fa-107">Дополнительные сведения о массовой рассылке см. в сведениях о различиях между нежелательной почтой и массовой рассылкой [электронной почты?](what-s-the-difference-between-junk-email-and-bulk-email.md) И уровень жалоб на массовую рассылку [(BCL) в EOP.](bulk-complaint-level-values.md)</span><span class="sxs-lookup"><span data-stu-id="ea4fa-107">For more information about bulk mail, see [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md) and [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span></span>

<span data-ttu-id="ea4fa-108">В этом разделе объясняется, как создавать эти правила потока обработки почты в Центре администрирования Exchange (EAC) и PowerShell (Exchange Online PowerShell для организаций Microsoft 365 с почтовыми ящиками в Exchange Online; автономный EOP PowerShell для организаций без почтовых ящиков Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="ea4fa-108">This topic explains how create these mail flow rules in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ea4fa-109">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="ea4fa-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ea4fa-110">Для этого необходимы соответствующие разрешения в Exchange Online или Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="ea4fa-110">You need to be assigned permissions in Exchange Online or Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="ea4fa-111">В частности, необходима  роль правил транспорта, назначенная по умолчанию группам ролей "Управление  организацией", "Управление соответствием требованиям" **(глобальным** администраторам) и "Управление записями".</span><span class="sxs-lookup"><span data-stu-id="ea4fa-111">Specifically, you need the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management** (global admins), and **Records Management** role groups by default.</span></span>

  <span data-ttu-id="ea4fa-112">Дополнительную информацию см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="ea4fa-112">For more information, see the following topics:</span></span>

  - [<span data-ttu-id="ea4fa-113">Разрешения в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ea4fa-113">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)
  - [<span data-ttu-id="ea4fa-114">Разрешения в автономном EOP</span><span class="sxs-lookup"><span data-stu-id="ea4fa-114">Permissions in standalone EOP</span></span>](feature-permissions-in-eop.md)
  - [<span data-ttu-id="ea4fa-115">Изменение списка участников в группах ролей с помощью EAC</span><span class="sxs-lookup"><span data-stu-id="ea4fa-115">Use the EAC modify the list of members in role groups</span></span>](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- <span data-ttu-id="ea4fa-116">Чтобы открыть Центр администрирования Exchange в Exchange Online, см. центр [администрирования Exchange в Exchange Online.](https://docs.microsoft.com/Exchange/exchange-admin-center)</span><span class="sxs-lookup"><span data-stu-id="ea4fa-116">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span> <span data-ttu-id="ea4fa-117">Чтобы открыть Центр администрирования Exchange в режиме автономных EOP, см. центр администрирования [Exchange в режиме автономных EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="ea4fa-117">To open the EAC in standalone EOP, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="ea4fa-118">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="ea4fa-118">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="ea4fa-119">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="ea4fa-119">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="ea4fa-120">Дополнительные сведения о правилах потока почты в Exchange Online и автономных EOP см. в следующих темах:</span><span class="sxs-lookup"><span data-stu-id="ea4fa-120">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>

  - [<span data-ttu-id="ea4fa-121">Правила потока обработки почты (правила транспорта) в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ea4fa-121">Mail flow rules (transport rules) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="ea4fa-122">Условия и исключения правил потока почты (предикаты) в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ea4fa-122">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="ea4fa-123">Действия правил потока почты в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ea4fa-123">Mail flow rule actions in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- <span data-ttu-id="ea4fa-124">Список слов и текстовых шаблонов, используемых для определения массовой рассылки в примерах, не является исчерпывающим; при необходимости можно добавлять и удалять записи.</span><span class="sxs-lookup"><span data-stu-id="ea4fa-124">The list of words and text patterns that are used to identify bulk mail in the examples aren't exhaustive; you can add and remove entries as necessary.</span></span> <span data-ttu-id="ea4fa-125">Тем не менее, они являются хорошей отправной точкой.</span><span class="sxs-lookup"><span data-stu-id="ea4fa-125">However, they are a good starting point.</span></span>

- <span data-ttu-id="ea4fa-p107">Поиск слов и текстовых шаблонов в теме или других полях заголовка сообщения выполняется *после* расшифровки сообщения, к которому применялся метод кодирования для передачи сообщений MIME. Этот метод используется для передачи двоичных сообщений между SMTP-серверами с преобразованием их в текст ASCII. Вы не можете применять условия или исключения для поиска необработанных закодированных значений (обычно в формате Base64) в теме или других полях заголовка сообщения.</span><span class="sxs-lookup"><span data-stu-id="ea4fa-p107">The search for words or text patterns in the subject or other header fields in the message occurs *after* the message has been decoded from the MIME content transfer encoding method that was used to transmit the binary message between SMTP servers in ASCII text. You can't use conditions or exceptions to search for the raw (typically, Base64) encoded values of the subject or other header fields in messages.</span></span>

- <span data-ttu-id="ea4fa-128">Следующие процедуры пометят массовое сообщение как нежелательное для всей организации.</span><span class="sxs-lookup"><span data-stu-id="ea4fa-128">The following procedures mark a bulk message as spam for your entire organization.</span></span> <span data-ttu-id="ea4fa-129">Однако вы можете добавить еще одно условие, чтобы применить эти правила только к определенным получателям, чтобы можно было использовать агрессивное фильтрацию для нескольких пользователей с высокой ориентацией, тогда как остальные пользователи (которые в основном получают массовые сообщения электронной почты, для которых они подписаны) не влияют.</span><span class="sxs-lookup"><span data-stu-id="ea4fa-129">However, you can add another condition to apply these rules only to specific recipients, so you can use aggressive filtering on a few, highly targeted users, while the rest of your users (who mostly get the bulk email they signed up for) aren't impacted.</span></span>

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="ea4fa-130">Использование EAC для создания правил потока почты, фильтруя массовые рассылки</span><span class="sxs-lookup"><span data-stu-id="ea4fa-130">Use the EAC to create mail flow rules that filter bulk email</span></span>

1. <span data-ttu-id="ea4fa-131">В Центре администрирования Exchange перейдите в раздел **Поток обработки почты** \> **Правила**.</span><span class="sxs-lookup"><span data-stu-id="ea4fa-131">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="ea4fa-132">Нажмите **значок** ![ "Добавить", а затем выберите ](../../media/ITPro-EAC-AddIcon.png) **"Создать новое правило".**</span><span class="sxs-lookup"><span data-stu-id="ea4fa-132">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="ea4fa-133">На открывшейся странице **Новое правило** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="ea4fa-133">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="ea4fa-134">**Name**: Enter a unique, descriptive name for the rule.</span><span class="sxs-lookup"><span data-stu-id="ea4fa-134">**Name**: Enter a unique, descriptive name for the rule.</span></span>

   - <span data-ttu-id="ea4fa-135">Нажмите кнопку **Дополнительные параметры**.</span><span class="sxs-lookup"><span data-stu-id="ea4fa-135">Click **More Options**.</span></span>

   - <span data-ttu-id="ea4fa-136">**Применяет это правило, если:** настройте один из следующих параметров, чтобы искать содержимое в сообщениях с помощью регулярных выражений (RegEx) или слов или фраз:</span><span class="sxs-lookup"><span data-stu-id="ea4fa-136">**Apply this rule if**: Configure one of the following settings to look for content in messages using regular expressions (RegEx) or words or phrases:</span></span>

     - <span data-ttu-id="ea4fa-137">**Тема или тело** \> **тема** или текст соответствует этим текстовым  шаблонам: в диалоговом окке "Укажите  слова или фразы" введите одно из следующих значений, нажмите кнопку "Добавить значок добавления" и повторяйте их, пока не введите все ![ ](../../media/ITPro-EAC-AddIcon.png) значения.</span><span class="sxs-lookup"><span data-stu-id="ea4fa-137">**The subject or body** \> **subject or body matches these text patterns**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

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

      <span data-ttu-id="ea4fa-138">Чтобы изменить запись, выберите  ее и нажмите значок ![ ](../../media/ITPro-EAC-EditIcon.png) редактирования.</span><span class="sxs-lookup"><span data-stu-id="ea4fa-138">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="ea4fa-139">Чтобы удалить запись, выберите ее и нажмите **значок "Удалить** ![ ](../../media/ITPro-EAC-DeleteIcon.png) удалить".</span><span class="sxs-lookup"><span data-stu-id="ea4fa-139">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="ea4fa-140">После этого нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ea4fa-140">When you're finished, click **OK**.</span></span>

     - <span data-ttu-id="ea4fa-141">**Тема или тело** \> **тема** или тело содержит любое из  этих слов: в диалоговом окке "Укажите  слова или фразы" введите одно из следующих значений, нажмите кнопку "Добавить значок добавления" и повторите это, пока не введите все ![ ](../../media/ITPro-EAC-AddIcon.png) значения.</span><span class="sxs-lookup"><span data-stu-id="ea4fa-141">**The subject or body** \> **subject or body includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

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

      <span data-ttu-id="ea4fa-142">Чтобы изменить запись, выберите  ее и нажмите значок ![ ](../../media/ITPro-EAC-EditIcon.png) редактирования.</span><span class="sxs-lookup"><span data-stu-id="ea4fa-142">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="ea4fa-143">Чтобы удалить запись, выберите ее и нажмите **значок "Удалить** ![ ](../../media/ITPro-EAC-DeleteIcon.png) удалить".</span><span class="sxs-lookup"><span data-stu-id="ea4fa-143">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="ea4fa-144">После этого нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ea4fa-144">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="ea4fa-145">**Сделайте следующее:** выберите **"Изменить свойства сообщения",** чтобы установить уровень достоверности \> **нежелательной почты (SCL).**</span><span class="sxs-lookup"><span data-stu-id="ea4fa-145">**Do the following**: Select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span> <span data-ttu-id="ea4fa-146">В **отозваемом** диалоговом окле "Указание SCL" настройте один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="ea4fa-146">In the **Specify SCL** dialog that appears, configure one of the following settings:</span></span>

     - <span data-ttu-id="ea4fa-147">Чтобы пометить сообщения как **нежелательные,** выберите **6.**</span><span class="sxs-lookup"><span data-stu-id="ea4fa-147">To mark messages as **Spam**, select **6**.</span></span> <span data-ttu-id="ea4fa-148">Действие, настроенное для принятия решения о фильтрации нежелательной почты в политиках борьбы с нежелательной почтой, применяется к сообщениям (значение по умолчанию — Переместить сообщение в папку нежелательной **почты).** </span><span class="sxs-lookup"><span data-stu-id="ea4fa-148">The action that you've configured for **Spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

     - <span data-ttu-id="ea4fa-149">Чтобы пометить сообщения как нежелательные с высокой **достоверности,** выберите **9.**</span><span class="sxs-lookup"><span data-stu-id="ea4fa-149">To mark messages as **High confidence spam** select **9**.</span></span> <span data-ttu-id="ea4fa-150">Действие, настроенное для принятия решения о фильтрации нежелательной почты с высокой достоверности в политиках борьбы с нежелательной почтой, применяется к сообщениям (значение по умолчанию — Переместить сообщение в папку нежелательной **почты).** </span><span class="sxs-lookup"><span data-stu-id="ea4fa-150">The action that you've configured for **High confidence spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

    <span data-ttu-id="ea4fa-151">Дополнительные сведения о значениях SCL см. в сведениях о доверии нежелательной почты [(SCL) в EOP.](spam-confidence-levels.md)</span><span class="sxs-lookup"><span data-stu-id="ea4fa-151">For more information about SCL values, see [Spam confidence level (SCL) in EOP](spam-confidence-levels.md).</span></span>

   <span data-ttu-id="ea4fa-152">По завершению нажмите кнопку **"Сохранить"**</span><span class="sxs-lookup"><span data-stu-id="ea4fa-152">When you're finished, click **Save**</span></span>

## <a name="use-powershell-to-create-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="ea4fa-153">Использование PowerShell для создания правил потока почты, фильтруя массовые рассылки</span><span class="sxs-lookup"><span data-stu-id="ea4fa-153">Use PowerShell to create mail flow rules that filter bulk email</span></span>

<span data-ttu-id="ea4fa-154">Используйте следующий синтаксис для создания одного или обоих правил потока почты (регулярных выражений и слов):</span><span class="sxs-lookup"><span data-stu-id="ea4fa-154">Use the following syntax to create one or both of the mail flow rules (regular expressions vs. words):</span></span>

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPhrase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

<span data-ttu-id="ea4fa-155">В этом примере создается новое правило с именем "Массовая фильтрация электронной почты — RegEx", использующее тот же список регулярных выражений, что и ранее в этой теме, для того, чтобы сделать сообщения **нежелательными.**</span><span class="sxs-lookup"><span data-stu-id="ea4fa-155">This example creates a new rule named "Bulk email filtering - RegEx" that uses the same list of regular expressions from earlier in the topic to set messages as **Spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? src=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

<span data-ttu-id="ea4fa-156">В этом примере создается новое правило с именем "Массовая фильтрация электронной почты — слова", которое использует тот же список слов из предыдущей темы, чтобы сделать сообщения нежелательными с высокой **достоверности.**</span><span class="sxs-lookup"><span data-stu-id="ea4fa-156">This example creates a new rule named "Bulk email filtering - Words" that uses the same list of words from earlier in the topic to set messages as **High confidence spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

<span data-ttu-id="ea4fa-157">Дополнительные сведения о синтаксисе и параметрах см. в статье [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span><span class="sxs-lookup"><span data-stu-id="ea4fa-157">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="ea4fa-158">Как убедиться, что все получилось?</span><span class="sxs-lookup"><span data-stu-id="ea4fa-158">How do you know this worked?</span></span>

<span data-ttu-id="ea4fa-159">Чтобы убедиться, что вы настроили правила потока почты для фильтрации массовых рассылок, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="ea4fa-159">To verify that you've configured mail flow rules to filter bulk email, do any of the following steps:</span></span>

- <span data-ttu-id="ea4fa-160">В EAC перейдите к **правилу потока** обработки почты, выберите правило, щелкните значок редактирования и проверьте \>  \> \>  ![ ](../../media/ITPro-EAC-EditIcon.png) параметры.</span><span class="sxs-lookup"><span data-stu-id="ea4fa-160">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="ea4fa-161">В PowerShell замените имя правила и запустите следующую команду, чтобы \<Rule Name\> проверить параметры:</span><span class="sxs-lookup"><span data-stu-id="ea4fa-161">In PowerShell, replace \<Rule Name\> with the name of the rule, and run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- <span data-ttu-id="ea4fa-162">Из внешней учетной записи отправьте тестовые сообщения затронутого получателя, который содержит одну из фраз или текстовых шаблонов, и проверьте результаты.</span><span class="sxs-lookup"><span data-stu-id="ea4fa-162">From an external account, send a test messages to an affected recipient that contains one of the phrases or text patterns, and verify the results.</span></span>
