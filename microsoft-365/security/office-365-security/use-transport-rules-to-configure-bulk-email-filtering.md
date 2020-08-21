---
title: Использование правил для потока обработки почты для фильтрации массовых рассылок
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
description: Администраторы могут узнать, как использовать правила потока обработки почты (правила транспорта) для определения и фильтрации массовых рассылок (серые рассылки) в Exchange Online Protection (EOP).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dfe841d3e80efc50d6ffbc702faefa1c9a971b13
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826757"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-eop"></a><span data-ttu-id="8f298-103">Используйте правила потока почты для фильтрации массовой почты в EOP</span><span class="sxs-lookup"><span data-stu-id="8f298-103">Use mail flow rules to filter bulk email in EOP</span></span>

<span data-ttu-id="8f298-104">В организациях Microsoft 365 с почтовыми ящиками в Exchange Online или в автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online для проверки входящих сообщений на спам и массовую рассылку (также называемой "серые" — eop).</span><span class="sxs-lookup"><span data-stu-id="8f298-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP uses anti-spam policies (also known as spam filter policies or content filter policies) to scan inbound messages for spam and bulk mail (also known as gray mail).</span></span> <span data-ttu-id="8f298-105">Дополнительные сведения см. в статье [Настройка политик защиты от спама в EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="8f298-105">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="8f298-106">Если вам нужны дополнительные параметры для фильтрации массовых рассылок, можно создать правила потока обработки почты (также называемые правилами транспорта) для поиска текстовых шаблонов или фраз, которые часто используются в массовых радикатных рамках, и пометить эти сообщения как нежелательные.</span><span class="sxs-lookup"><span data-stu-id="8f298-106">If you want more options to filter bulk mail, you can create mail flow rules (also known as transport rules) to search for text patterns or phrases that are frequently found in bulk mail, and mark those messages as spam.</span></span> <span data-ttu-id="8f298-107">Дополнительные сведения о массовой рассылке почты см. в статье "В чем разница между нежелательной [почтой и массовыми](what-s-the-difference-between-junk-email-and-bulk-email.md) рассылками" [и "Массовые рассылки" (BCL) в EOP.](bulk-complaint-level-values.md)</span><span class="sxs-lookup"><span data-stu-id="8f298-107">For more information about bulk mail, see [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md) and [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span></span>

<span data-ttu-id="8f298-108">В этой статье объясняется, как создать эти правила для потока обработки почты в Центр администрирования Exchange и PowerShell (Exchange Online PowerShell для организаций Microsoft 365 с почтовыми ящиками в Exchange Online, а также автономная оболочка EOP PowerShell для организаций без почтовых ящиков Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="8f298-108">This topic explains how create these mail flow rules in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="8f298-109">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="8f298-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="8f298-110">Для выполнения следующих процедур необходимы права:</span><span class="sxs-lookup"><span data-stu-id="8f298-110">You need to be assigned permissions before you can do these procedures:</span></span>

  - <span data-ttu-id="8f298-111">В Exchange Online см. запись "Поток обработки почты" в [разрешениях функций в Exchange Online.](https://docs.microsoft.com/Exchange/permissions-exo/feature-permissions)</span><span class="sxs-lookup"><span data-stu-id="8f298-111">In Exchange Online, see the "Mail flow" entry in [Feature Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/feature-permissions).</span></span>
  
  - <span data-ttu-id="8f298-112">В автономной службе EOP требуется роль правил транспорта, по умолчанию присваиваемая ролям OrganizationManagement, ComplianceManagement и RecordsManagement.</span><span class="sxs-lookup"><span data-stu-id="8f298-112">In standalone EOP, you need the Transport Rules role, which is assigned to the OrganizationManagement, ComplianceManagement, and RecordsManagement roles by default.</span></span> <span data-ttu-id="8f298-113">Дополнительные сведения см. в разделе ["Разрешения в автономной службе EOP"](feature-permissions-in-eop.md) и использовании Центра администрирования [Exchange для изменения списка членов в группах ролей.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)</span><span class="sxs-lookup"><span data-stu-id="8f298-113">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="8f298-114">Сведения о том, как открыть Центр администрирования Exchange в Exchange Online, [см. в статье Центра администрирования Exchange в Exchange Online.](https://docs.microsoft.com/Exchange/exchange-admin-center)</span><span class="sxs-lookup"><span data-stu-id="8f298-114">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span> <span data-ttu-id="8f298-115">Сведения о том, как открыть Центр администрирования Exchange в автономной службе EOP, см. в [статье Центр администрирования Exchange в автономной службе EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="8f298-115">To open the EAC in standalone EOP, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="8f298-116">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="8f298-116">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="8f298-117">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="8f298-117">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="8f298-118">Дополнительные сведения о правилах для потока обработки почты в Exchange Online и автономной службе EOP см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="8f298-118">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>

  - [<span data-ttu-id="8f298-119">Правила потока обработки почты (правила транспорта) в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="8f298-119">Mail flow rules (transport rules) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="8f298-120">Условия и исключения (предикаты) правил потока обработки почты в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="8f298-120">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="8f298-121">Действия правил обработки почтового потока в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="8f298-121">Mail flow rule actions in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- <span data-ttu-id="8f298-122">В этих примерах представлен не исключающий текст слов и текстовые шаблоны; При необходимости можно добавлять и удалять записи.</span><span class="sxs-lookup"><span data-stu-id="8f298-122">The list of words and text patterns that are used to identify bulk mail in the examples aren't exhaustive; you can add and remove entries as necessary.</span></span> <span data-ttu-id="8f298-123">Однако они хорошо служат отправной точкой.</span><span class="sxs-lookup"><span data-stu-id="8f298-123">However, they are a good starting point.</span></span>

- <span data-ttu-id="8f298-p107">Поиск слов и текстовых шаблонов в теме или других полях заголовка сообщения выполняется *после* расшифровки сообщения, к которому применялся метод кодирования для передачи сообщений MIME. Этот метод используется для передачи двоичных сообщений между SMTP-серверами с преобразованием их в текст ASCII. Вы не можете применять условия или исключения для поиска необработанных закодированных значений (обычно в формате Base64) в теме или других полях заголовка сообщения.</span><span class="sxs-lookup"><span data-stu-id="8f298-p107">The search for words or text patterns in the subject or other header fields in the message occurs *after* the message has been decoded from the MIME content transfer encoding method that was used to transmit the binary message between SMTP servers in ASCII text. You can't use conditions or exceptions to search for the raw (typically, Base64) encoded values of the subject or other header fields in messages.</span></span>

- <span data-ttu-id="8f298-126">Следующие процедуры отмечены как спам для всей организации.</span><span class="sxs-lookup"><span data-stu-id="8f298-126">The following procedures mark a bulk message as spam for your entire organization.</span></span> <span data-ttu-id="8f298-127">Однако вы можете добавить еще одно условие, чтобы применить эти правила только к определенным получателям, поэтому ее можно применять для нескольких жестко целевых пользователей, тогда как остальные пользователи (которые, в основном, получают массовые сообщения, на которые они подписаны) не затронуты.</span><span class="sxs-lookup"><span data-stu-id="8f298-127">However, you can add another condition to apply these rules only to specific recipients, so you can use aggressive filtering on a few, highly targeted users, while the rest of your users (who mostly get the bulk email they signed up for) aren't impacted.</span></span>

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="8f298-128">Создание правил потока обработки почты, фильтрующих массовые сообщения электронной почты, с помощью Центра администрирования Exchange</span><span class="sxs-lookup"><span data-stu-id="8f298-128">Use the EAC to create mail flow rules that filter bulk email</span></span>

1. <span data-ttu-id="8f298-129">В Центре администрирования Exchange перейдите в раздел **Поток обработки почты** \> **Правила**.</span><span class="sxs-lookup"><span data-stu-id="8f298-129">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="8f298-130">Нажмите **кнопку** ![ "Добавить ](../../media/ITPro-EAC-AddIcon.png) значок "Добавить" и **выберите пункт "Создать правило".**</span><span class="sxs-lookup"><span data-stu-id="8f298-130">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="8f298-131">На открывшейся странице **Новое правило** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="8f298-131">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="8f298-132">**Имя:** введите уникальное, понятное имя правила.</span><span class="sxs-lookup"><span data-stu-id="8f298-132">**Name**: Enter a unique, descriptive name for the rule.</span></span>

   - <span data-ttu-id="8f298-133">Нажмите кнопку **Дополнительные параметры**.</span><span class="sxs-lookup"><span data-stu-id="8f298-133">Click **More Options**.</span></span>

   - <span data-ttu-id="8f298-134">**Применяет это правило, если:** настройте один из следующих параметров для поиска содержимого сообщений с использованием регулярных выражений (RegEx), слов или фраз:</span><span class="sxs-lookup"><span data-stu-id="8f298-134">**Apply this rule if**: Configure one of the following settings to look for content in messages using regular expressions (RegEx) or words or phrases:</span></span>

     - <span data-ttu-id="8f298-135">**Тема или текст** \> **Тема или текст соответствует этим текстовым шаблонам:** в появившемся диалоговом окне "Укажите слова или фразы" введите одно из следующих значений, нажмите кнопку **Добавить** **Specify words or phrases** ![ ](../../media/ITPro-EAC-AddIcon.png) значок и повторяйте, пока не введите все значения.</span><span class="sxs-lookup"><span data-stu-id="8f298-135">**The subject or body** \> **subject or body matches these text patterns**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

       - `If you are unable to view the content of this email\, please`
       - `\>(safe )?unsubscribe( here)?\</a\>`
       - `If you do not wish to receive further communications like this\, please`
       - `\<img height\="?1"? width\="?1"? sr\c=.?http\://`
       - `To stop receiving these+emails\:http\://`
       - `To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)`
       - `no longer (wish )?(to )?(be sent|receive) w+ email`
       - `If you are unable to view the content of this email\, please click here`
       - `To ensure you receive (your daily deals|our e-?mails)\, add`
       - `If you no longer wish to receive these emails`
       - `to change your (subscription preferences|preferences or unsubscribe)`
       - `click (here to|the) unsubscribe`

      <span data-ttu-id="8f298-136">Чтобы изменить запись, выберите ее и нажмите **значок** ![ ](../../media/ITPro-EAC-EditIcon.png) редактирования.</span><span class="sxs-lookup"><span data-stu-id="8f298-136">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="8f298-137">Чтобы удалить запись, выберите ее и нажмите **значок** ![ ](../../media/ITPro-EAC-DeleteIcon.png) "Удалить".</span><span class="sxs-lookup"><span data-stu-id="8f298-137">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="8f298-138">После этого нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8f298-138">When you're finished, click **OK**.</span></span>

     - <span data-ttu-id="8f298-139">**Тема или текст** \> **Тема или текст включает любое из следующих**слов: в **Specify words or phrases** появившемся диалоговом окне "Укажите слова или фразы" введите одно из следующих значений, нажмите кнопку **Add** ![ Icon ](../../media/ITPro-EAC-AddIcon.png) (Добавить значок) и повторяйте, пока не введите все значения.</span><span class="sxs-lookup"><span data-stu-id="8f298-139">**The subject or body** \> **subject or body includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

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

      <span data-ttu-id="8f298-140">Чтобы изменить запись, выберите ее и нажмите **значок** ![ ](../../media/ITPro-EAC-EditIcon.png) редактирования.</span><span class="sxs-lookup"><span data-stu-id="8f298-140">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="8f298-141">Чтобы удалить запись, выберите ее и нажмите **значок** ![ ](../../media/ITPro-EAC-DeleteIcon.png) "Удалить".</span><span class="sxs-lookup"><span data-stu-id="8f298-141">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="8f298-142">После этого нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8f298-142">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="8f298-143">**Выполните следующее:** **"Изменить свойства сообщения"** задали вероятность \> **нежелательной почты (SCL).**</span><span class="sxs-lookup"><span data-stu-id="8f298-143">**Do the following**: Select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span> <span data-ttu-id="8f298-144">В **отобразившемся диалоговом окне** "Указание вероятности нежелательной почты" настройте один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="8f298-144">In the **Specify SCL** dialog that appears, configure one of the following settings:</span></span>

     - <span data-ttu-id="8f298-145">Чтобы пометить сообщения **как нежелательные,** **нажмите 6.**</span><span class="sxs-lookup"><span data-stu-id="8f298-145">To mark messages as **Spam**, select **6**.</span></span> <span data-ttu-id="8f298-146">К сообщениям применяется действие, **Spam** настроенное на использование фильтров нежелательной почты в политиках защиты от нежелательной почты (значение по умолчанию "Переместить **сообщение в папку нежелательной почты").**</span><span class="sxs-lookup"><span data-stu-id="8f298-146">The action that you've configured for **Spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

     - <span data-ttu-id="8f298-147">Чтобы пометить сообщения **как нежелательную почту с высокой** вероятностью, **нажмите 9.**</span><span class="sxs-lookup"><span data-stu-id="8f298-147">To mark messages as **High confidence spam** select **9**.</span></span> <span data-ttu-id="8f298-148">К сообщениям применяется действие, **High confidence spam** настроенное на решения фильтров нежелательной почты высокого уровня в политиках защиты от нежелательной почты (значение по умолчанию "Переместить **сообщение в папку нежелательной почты").**</span><span class="sxs-lookup"><span data-stu-id="8f298-148">The action that you've configured for **High confidence spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

    <span data-ttu-id="8f298-149">Дополнительные сведения о значениях SCL см. в статье Об уровне [вероятности нежелательной почты (SCL) в EOP.](spam-confidence-levels.md)</span><span class="sxs-lookup"><span data-stu-id="8f298-149">For more information about SCL values, see [Spam confidence level (SCL) in EOP](spam-confidence-levels.md).</span></span>

   <span data-ttu-id="8f298-150">По завершении нажмите кнопку **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="8f298-150">When you're finished, click **Save**</span></span>

## <a name="use-powershell-to-create-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="8f298-151">Создание правил потока обработки почты, которые фильтруют массовые рассылки, с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="8f298-151">Use PowerShell to create mail flow rules that filter bulk email</span></span>

<span data-ttu-id="8f298-152">Используйте следующий синтаксис для создания одного или обоих правил потока обработки почты (обычных выражений и слов):</span><span class="sxs-lookup"><span data-stu-id="8f298-152">Use the following syntax to create one or both of the mail flow rules (regular expressions vs. words):</span></span>

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPhrase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

<span data-ttu-id="8f298-153">В этом примере создается новое правило с именем "Bulk email filtering - RegEx", в котором для установки сообщений как нежелательных используется тот же список регулярных выражений, как у **приведенных ранее**в разделе.</span><span class="sxs-lookup"><span data-stu-id="8f298-153">This example creates a new rule named "Bulk email filtering - RegEx" that uses the same list of regular expressions from earlier in the topic to set messages as **Spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? sr\c=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

<span data-ttu-id="8f298-154">В этом примере создается новое правило с именем "Фильтрация массовой рассылки — Words", использующее тот же список слов, как и у предыдущего раздела, для установки сообщений с высокой **вероятностью.**</span><span class="sxs-lookup"><span data-stu-id="8f298-154">This example creates a new rule named "Bulk email filtering - Words" that uses the same list of words from earlier in the topic to set messages as **High confidence spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

<span data-ttu-id="8f298-155">Дополнительные сведения о синтаксисе и параметрах см. в статье [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span><span class="sxs-lookup"><span data-stu-id="8f298-155">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="8f298-156">Как убедиться, что все получилось?</span><span class="sxs-lookup"><span data-stu-id="8f298-156">How do you know this worked?</span></span>

<span data-ttu-id="8f298-157">Чтобы убедиться, что настроены правила потока обработки почты для фильтрации массовых рассылок, выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="8f298-157">To verify that you've configured mail flow rules to filter bulk email, do any of the following steps:</span></span>

- <span data-ttu-id="8f298-158">В Центре администрирования Exchange перейдите в раздел **"Правила** \> **потока обработки** \> почты" и \> выберите правило на значок **Edit** ![ "Изменить ](../../media/ITPro-EAC-EditIcon.png) изменить" и проверьте параметры.</span><span class="sxs-lookup"><span data-stu-id="8f298-158">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="8f298-159">В PowerShell \<Rule Name\> замените именем правила и выполните следующую команду, чтобы проверить параметры:</span><span class="sxs-lookup"><span data-stu-id="8f298-159">In PowerShell, replace \<Rule Name\> with the name of the rule, and run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- <span data-ttu-id="8f298-160">Отправьте из внешней учетной записи тестовые сообщения получателю, который содержит одну из фраз или текстовых шаблонов, и проверьте результаты.</span><span class="sxs-lookup"><span data-stu-id="8f298-160">From an external account, send a test messages to an affected recipient that contains one of the phrases or text patterns, and verify the results.</span></span>
