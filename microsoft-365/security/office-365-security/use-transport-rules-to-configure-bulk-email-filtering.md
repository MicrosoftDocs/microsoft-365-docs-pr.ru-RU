---
title: Настройка фильтрации массовых сообщений электронной почты в Exchange Online Protection с помощью правил для обработки почтового процесса
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: Администраторы могут узнать, как использовать правила обработки почтового ящика в Exchange Online Protection для фильтрации массовых сообщений электронной почты.
ms.openlocfilehash: e354bb137e114a7d11bff97be0c1109becb54f84
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37091163"
---
# <a name="use-mail-flow-rules-to-configure-bulk-email-filtering-in-exchange-online-protection"></a><span data-ttu-id="741a4-103">Настройка фильтрации массовых сообщений электронной почты в Exchange Online Protection с помощью правил для обработки почтового процесса</span><span class="sxs-lookup"><span data-stu-id="741a4-103">Use mail flow rules to configure bulk email filtering in Exchange Online Protection</span></span>

<span data-ttu-id="741a4-p101">Вы можете настроить фильтры содержимого на уровне всей компании для нежелательной почты и массовых сообщений электронной почты, используя политики фильтрации содержимого нежелательной почты по умолчанию. Сведения о настройке политик фильтрации содержимого см. в разделах [Настройте политики защиты от спама](configure-your-spam-filter-policies.md) и [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="741a4-p101">You can set company-wide content filters for spam and bulk email using the default spam content-filter policies. Check out [Configure your spam filter policies](configure-your-spam-filter-policies.md) and [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy?view=exchange-ps) on how to set the content filter policies.</span></span> 
  
<span data-ttu-id="741a4-106">Если вы хотите дополнительно отфильтровать массовые сообщения, вы можете создать правила для поток обработки почты (также называемые правилами транспорта), чтобы искать текстовые шаблоны или фразы, которые часто встречаются в массовых сообщениях.</span><span class="sxs-lookup"><span data-stu-id="741a4-106">If you want to more options to filter bulk messages, you can create mail flow rules (also known as transport rules) to search for text patterns or phrases frequently found in bulk emails.</span></span> <span data-ttu-id="741a4-107">Каждое сообщение, обладающее этими характеристиками, будет отмечено как нежелательное.</span><span class="sxs-lookup"><span data-stu-id="741a4-107">Any message containing these characteristics will be marked as spam.</span></span> <span data-ttu-id="741a4-108">Использование этих правил может сократить объем нежелательных сообщений, которые получает ваша организация.</span><span class="sxs-lookup"><span data-stu-id="741a4-108">Using these rules can help reduce the amount of unwanted bulk email your organization receives.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="741a4-109">Прежде чем создавать правила для почтовых ящиков, описанные в этой статье, мы рекомендуем сначала ознакомиться [с различиями между нежелательной почтой и групповой почтой?](what-s-the-difference-between-junk-email-and-bulk-email.md) и [значениями уровня жалоби массовых жалоб](bulk-complaint-level-values.md).</span><span class="sxs-lookup"><span data-stu-id="741a4-109">Before creating the mail flow rules documented this topic, we recommend that you first read [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md) and [Bulk Complaint Level values](bulk-complaint-level-values.md).</span></span><br><span data-ttu-id="741a4-p103">Следующие процедуры отмечают сообщение как нежелательное для всей организации. Однако можно добавить другое условие, чтобы применить эти правила только к определенным получателям в вашей организации. Таким образом агрессивные параметры фильтрации массовой электронной почты могут применяться к нескольким пользователям, которые часто становятся адресатом нежелательной почты, не затрагивая других пользователей (которые, в основном, получают массовые сообщения, на которые они подписаны).</span><span class="sxs-lookup"><span data-stu-id="741a4-p103"> The following procedures mark a message as spam for your entire organization. However, you can add another condition to apply these rules only to specific recipients in your organization. This way, the aggressive bulk email filtering settings can apply to a few users who are highly targeted, while the rest of your users (who mostly get the bulk email they signed up for) aren't impacted.</span></span> 
  
## <a name="create-a-mail-flow-rule-to-filter-bulk-email-messages-based-on-text-patterns"></a><span data-ttu-id="741a4-113">Создание правила для почтового процесса для фильтрации массовых сообщений электронной почты на основе текстовых шаблонов</span><span class="sxs-lookup"><span data-stu-id="741a4-113">Create a mail flow rule to filter bulk email messages based on text patterns</span></span>

1. <span data-ttu-id="741a4-114">В Центре администрирования Exchange перейдите в раздел **Поток обработки почты** \> **Правила**.</span><span class="sxs-lookup"><span data-stu-id="741a4-114">In the Exchange admin center (EAC), go to **Mail flow** \> **Rules**.</span></span>
    
2. <span data-ttu-id="741a4-115">Щелкните **Добавить** ![значок](../media/ITPro-EAC-AddIcon.gif) добавить, а затем выберите **создать новое правило**.</span><span class="sxs-lookup"><span data-stu-id="741a4-115">Click **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif) and then select **Create a new rule**.</span></span>
    
3. <span data-ttu-id="741a4-116">Укажите имя правила.</span><span class="sxs-lookup"><span data-stu-id="741a4-116">Specify a name for the rule.</span></span>
    
4. <span data-ttu-id="741a4-p104">Нажмите кнопку **Дополнительные параметры**. В разделе **Применить это правило, если** выберите **Тема или текст** \> **соответствует этим текстовым шаблонам**.</span><span class="sxs-lookup"><span data-stu-id="741a4-p104">Click **More options**. Under **Apply this rule if**, select **The subject or body** \> **subject or body matches these text patterns**.</span></span>
    
5. <span data-ttu-id="741a4-119">В диалоговом окне **Задайте слова или фразы** добавьте следующие регулярные выражения, которые часто используются в массовых сообщениях, по одному и затем нажмите кнопку **ОК**:</span><span class="sxs-lookup"><span data-stu-id="741a4-119">In the **specify words or phrases** dialog box, add the following regular expressions commonly found in bulk emails, one at a time, and click **ok** when you're done:</span></span> 
    
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
    
   <span data-ttu-id="741a4-120">Приведенный выше список не является исчерпывающим набором регулярных выражений, найденных в массовых сообщениях электронной почты; При необходимости можно добавить или удалить дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="741a4-120">The above list isn't an exhaustive set of regular expressions found in bulk emails; more can be added or removed as needed.</span></span> <span data-ttu-id="741a4-121">Однако это хорошая отправная точка.</span><span class="sxs-lookup"><span data-stu-id="741a4-121">However, it's a good starting point.</span></span><br><span data-ttu-id="741a4-122">Поиск слов или текстовых шаблонов в теме или других полях заголовков сообщения происходит *после* декодирования сообщения из метода кодирования передачи содержимого MIME, который использовался для передачи двоичного сообщения между SMTP-серверами в ASCII-тексте.</span><span class="sxs-lookup"><span data-stu-id="741a4-122">The search for words or text patterns in the subject or other header fields in the message occurs  *after*  the message has been decoded from the MIME content transfer encoding method that was used to transmit the binary message between SMTP servers in ASCII text.</span></span> <span data-ttu-id="741a4-123">Вы не можете использовать условия или исключения для поиска необработанных значений в формате "Тема" или других полей заголовков в сообщениях.</span><span class="sxs-lookup"><span data-stu-id="741a4-123">You can't use conditions or exceptions to search for the raw (typically, Base64) encoded values of the subject or other header fields in messages.</span></span> 
    
6. <span data-ttu-id="741a4-124">В разделе **Выполните следующее** выберите пункт **Изменить свойства сообщения** \> **задать значение для вероятности нежелательной почты (SCL)**.</span><span class="sxs-lookup"><span data-stu-id="741a4-124">Under **Do the following**, select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span>
    
7. <span data-ttu-id="741a4-125">В диалоговом окне **Укажите вероятность нежелательной почты** выберите для SCL значение **5**, **6** или **9** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="741a4-125">In the **specify SCL** dialog box, set the SCL to **5**, **6**, or **9**, and click **ok**.</span></span>
    
   <span data-ttu-id="741a4-p107">Выбор для SCL значения 5 или 6 приводит к выполнению действия **Нежелательная почта**. Выбор значения 9 приводит к выполнению действия **Нежелательное сообщение высокого уровня** согласно настройке политики фильтрации содержимого. Служба выполняет действие, указанное в политике фильтрации содержимого. По умолчанию это действие  доставка сообщения в папку получателя "Нежелательная почта", однако можно настроить и другие действия, как описано в разделе [Настройте политики защиты от спама](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="741a4-p107">Setting the SCL to 5 or 6 takes the **Spam** action, while setting the SCL to 9 takes the **High confidence spam** action, as configured in the content filter policy. The service will perform the action set in the content filter policy. The default action is to deliver the message to the recipients' Junk Email folder, but different actions can be configured as described in [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
    
   <span data-ttu-id="741a4-129">Если настроенное действие предназначено для помещения сообщения в карантин, а не отправки его в папку нежелательной почты получателей, сообщение будет отправлено в карантин администратора в качестве правила для почтового процесса, и оно будет недоступно в карантине нежелательной почты конечного пользователя или с помощью конечного пользователя уведомления о нежелательной почте.</span><span class="sxs-lookup"><span data-stu-id="741a4-129">If your configured action is to quarantine the message rather than send it to the recipients' Junk Email folder, the message will be sent to the administrator quarantine as a mail flow rule match, and it will not be available in the end user spam quarantine or via end-user spam notifications.</span></span> 
  
   <span data-ttu-id="741a4-130">Дополнительные сведения о значениях SCL в службе см. в статье [Вероятность нежелательной почты](spam-confidence-levels.md).</span><span class="sxs-lookup"><span data-stu-id="741a4-130">For more information about SCL values in the service, see [Spam confidence levels](spam-confidence-levels.md).</span></span>
    
8. <span data-ttu-id="741a4-131">Сохраните правило.</span><span class="sxs-lookup"><span data-stu-id="741a4-131">Save the rule.</span></span>
    
## <a name="create-a-mail-flow-rule-to-filter-bulk-email-messages-based-on-phrases"></a><span data-ttu-id="741a4-132">Создание правила для почтового процесса для фильтрации массовых сообщений электронной почты на основе фраз</span><span class="sxs-lookup"><span data-stu-id="741a4-132">Create a mail flow rule to filter bulk email messages based on phrases</span></span>

1. <span data-ttu-id="741a4-133">В Центре администрирования Exchange перейдите в раздел **Поток обработки почты** \> **Правила**.</span><span class="sxs-lookup"><span data-stu-id="741a4-133">In the EAC, go to **Mail flow** \> **Rules**.</span></span>
    
2. <span data-ttu-id="741a4-134">Щелкните **Добавить** ![значок](../media/ITPro-EAC-AddIcon.gif) добавить, а затем выберите **создать новое правило**.</span><span class="sxs-lookup"><span data-stu-id="741a4-134">Click **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif) and then select **Create a new rule**.</span></span>
    
3. <span data-ttu-id="741a4-135">Укажите имя правила.</span><span class="sxs-lookup"><span data-stu-id="741a4-135">Specify a name for the rule.</span></span>
    
4. <span data-ttu-id="741a4-p108">Нажмите кнопку **Дополнительные параметры**. В разделе **Применить это правило, если** выберите **Тема или текст** \> **тема включает любое из этих слов**.</span><span class="sxs-lookup"><span data-stu-id="741a4-p108">Click **More options**. Under **Apply this rule if**, select **The subject or body** \> **subject or body includes any of these words**.</span></span>
    
5. <span data-ttu-id="741a4-138">В диалоговом окне **Задайте слова или фразы** добавьте следующие фразы, которые часто используются в массовых сообщениях, по одному и затем нажмите кнопку **ОК**:</span><span class="sxs-lookup"><span data-stu-id="741a4-138">In the **specify words or phrases** dialog box, add the following phrases commonly found in bulk emails, one at a time, and click **ok** when you're done:</span></span> 
    
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
    
   <span data-ttu-id="741a4-139">Этот список не является исчерпывающим набором фраз, найденных в массовых сообщениях электронной почты; При необходимости можно добавить или удалить дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="741a4-139">This list isn't an exhaustive set of phrases found in bulk emails; more can be added or removed as needed.</span></span> <span data-ttu-id="741a4-140">Однако это хорошая отправная точка.</span><span class="sxs-lookup"><span data-stu-id="741a4-140">However, it's a good starting point.</span></span>
    
6. <span data-ttu-id="741a4-141">В разделе **Выполните следующее** выберите пункт **Изменить свойства сообщения** \> **задать значение для вероятности нежелательной почты (SCL)**.</span><span class="sxs-lookup"><span data-stu-id="741a4-141">Under **Do the following**, select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span>
    
7. <span data-ttu-id="741a4-142">В диалоговом окне **Укажите вероятность нежелательной почты** выберите для SCL значение **5**, **6** или **9** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="741a4-142">In the **specify SCL** dialog box, set the SCL to **5**, **6**, or **9**, and click **ok**.</span></span>
    
   <span data-ttu-id="741a4-p110">Выбор для SCL значения 5 или 6 приводит к выполнению действия **Нежелательная почта**. Выбор значения 9 приводит к выполнению действия **Нежелательное сообщение высокого уровня** согласно настройке политики фильтрации содержимого. Служба выполняет действие, указанное в политике фильтрации содержимого. По умолчанию это действие  доставка сообщения в папку получателя "Нежелательная почта", однако можно настроить и другие действия, как описано в разделе [Настройте политики защиты от спама](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="741a4-p110">Setting the SCL to 5 or 6 takes the **Spam** action, while setting the SCL to 9 takes the **High confidence spam** action, as configured in the content filter policy. The service will perform the action set in the content filter policy. The default action is to deliver the message to the recipients' Junk Email folder, but different actions can be configured as described in [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
    
   <span data-ttu-id="741a4-146">Если настроенное действие предназначено для помещения сообщения в карантин, а не отправки его в папку нежелательной почты получателей, сообщение будет отправлено в карантин администратора в качестве правила для почтового процесса, и оно будет недоступно в карантине нежелательной почты конечного пользователя или с помощью конечного пользователя уведомления о нежелательной почте.</span><span class="sxs-lookup"><span data-stu-id="741a4-146">If your configured action is to quarantine the message rather than send it to the recipients' Junk Email folder, the message will be sent to the administrator quarantine as a mail flow rule match, and it will not be available in the end user spam quarantine or via end-user spam notifications.</span></span> 
  
   <span data-ttu-id="741a4-147">Дополнительные сведения о значениях SCL в службе см. в статье [Вероятность нежелательной почты](spam-confidence-levels.md).</span><span class="sxs-lookup"><span data-stu-id="741a4-147">For more information about SCL values in the service, see [Spam confidence levels](spam-confidence-levels.md).</span></span>

8. <span data-ttu-id="741a4-148">Сохраните правило.</span><span class="sxs-lookup"><span data-stu-id="741a4-148">Save the rule.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="741a4-149">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="741a4-149">For more information</span></span>

[<span data-ttu-id="741a4-150">В чем разница между нежелательной почтой и массовыми сообщениями электронной почты?</span><span class="sxs-lookup"><span data-stu-id="741a4-150">What's the difference between junk email and bulk email?</span></span>](what-s-the-difference-between-junk-email-and-bulk-email.md)

[<span data-ttu-id="741a4-151">Уровни жалоб на массовые сообщения</span><span class="sxs-lookup"><span data-stu-id="741a4-151">Bulk Complaint Level values</span></span>](bulk-complaint-level-values.md)

[<span data-ttu-id="741a4-152">Настройте политики защиты от спама</span><span class="sxs-lookup"><span data-stu-id="741a4-152">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)

[<span data-ttu-id="741a4-153">Параметры расширенной фильтрации нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="741a4-153">Advanced spam filtering  options</span></span>](advanced-spam-filtering-asf-options.md)
