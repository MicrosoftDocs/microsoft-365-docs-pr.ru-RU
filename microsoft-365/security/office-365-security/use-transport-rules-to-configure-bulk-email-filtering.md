---
title: Использование правил обработки почтового процесса для фильтрации массовых сообщений электронной почты в Office 365
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
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: Администраторы могут узнать, как использовать правила обработки почтового ящика в Exchange Online Protection для фильтрации массовых сообщений электронной почты.
ms.openlocfilehash: 2ac81d798af957f23f95b92f633b93bdda677991
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895051"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-office-365"></a><span data-ttu-id="c5005-103">Использование правил обработки почтового процесса для фильтрации массовых сообщений электронной почты в Office 365</span><span class="sxs-lookup"><span data-stu-id="c5005-103">Use mail flow rules to filter bulk email in Office 365</span></span>

<span data-ttu-id="c5005-104">Если вы являетесь клиентом Office 365 с почтовыми ящиками в Exchange Online или отдельном клиенте Exchange Online Protection (EOP) без почтовых ящиков Exchange Online, EOP использует политики защиты от нежелательной почты (также называемые политиками фильтрации нежелательной почты или фильтрами содержимого) для сканирования входящие сообщения для нежелательной почты и массовой почты (также называемой серой почтой).</span><span class="sxs-lookup"><span data-stu-id="c5005-104">If you're an Office 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, EOP uses anti-spam policies (also known as spam filter policies or content filter policies) to scan inbound messages for spam and bulk mail (also known as gray mail).</span></span> <span data-ttu-id="c5005-105">Дополнительные сведения см. в разделе [Настройка политик защиты от спама в Office 365](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="c5005-105">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="c5005-106">Если вы хотите дополнительно отфильтровать массовую почту, вы можете создать правила для поток обработки почты (также называемые правилами транспорта), чтобы искать текстовые шаблоны или фразы, которые часто встречаются в массовой почте, и помечать эти сообщения как спам.</span><span class="sxs-lookup"><span data-stu-id="c5005-106">If you want more options to filter bulk mail, you can create mail flow rules (also known as transport rules) to search for text patterns or phrases that are frequently found in bulk mail, and mark those messages as spam.</span></span> <span data-ttu-id="c5005-107">Для получения дополнительных сведений об массовой рассылке почты посмотрите, [что такое различие между нежелательной почтой и групповой почтой](what-s-the-difference-between-junk-email-and-bulk-email.md) и [уровнем жалоб (BCL) в Office 365](bulk-complaint-level-values.md).</span><span class="sxs-lookup"><span data-stu-id="c5005-107">For more information about bulk mail, see [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md) and [Bulk complaint level (BCL) in Office 365](bulk-complaint-level-values.md).</span></span>

<span data-ttu-id="c5005-108">В этом разделе объясняется, как создавать эти правила для этих почтовых ящиков в центре администрирования Exchange и PowerShell (Exchange Online PowerShell для Office 365 и клиентов). Exchange Online Protection PowerShell для автономных клиентов EOP).</span><span class="sxs-lookup"><span data-stu-id="c5005-108">This topic explains how create these mail flow rules in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Office 365 customers; Exchange Online Protection PowerShell for standalone EOP customers).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c5005-109">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="c5005-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c5005-110">Прежде чем выполнять эти процедуры, вам необходимо назначить разрешения в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c5005-110">You need to be assigned permissions in Exchange Online before you can do these procedures.</span></span> <span data-ttu-id="c5005-111">В частности, необходимо назначить роль " **правила транспорта** ", которая назначается для ролей управления **организацией**, **управления соответствием требованиям**и управления **записями** по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c5005-111">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="c5005-112">Дополнительные сведения см. в статье [Управление группами ролей в Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span><span class="sxs-lookup"><span data-stu-id="c5005-112">For more information, see [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

- <span data-ttu-id="c5005-113">Чтобы открыть центр администрирования Exchange в Exchange Online, обратитесь к [центру администрирования Exchange в Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="c5005-113">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span>

- <span data-ttu-id="c5005-114">Сведения о подключении к Exchange Online PowerShell см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="c5005-114">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="c5005-115">Чтобы подключиться к автономной службе Exchange Online Protection PowerShell, ознакомьтесь со статьей [Подключение к PowerShell для Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="c5005-115">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="c5005-116">Дополнительные сведения о правилах обработки почтового ящика в Exchange Online и отдельном EOP содержатся в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="c5005-116">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>

  - [<span data-ttu-id="c5005-117">Правила потока обработки почты (правила транспорта) в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="c5005-117">Mail flow rules (transport rules) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="c5005-118">Условия и исключения правила для обработки почтового процесса (предикаты) в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="c5005-118">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="c5005-119">Действия правил обработки почты в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="c5005-119">Mail flow rule actions in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- <span data-ttu-id="c5005-120">Список слов и текстовых шаблонов, используемых для идентификации массовой почты в примерах, не является исчерпывающим; При необходимости вы можете добавлять и удалять записи.</span><span class="sxs-lookup"><span data-stu-id="c5005-120">The list of words and text patterns that are used to identify bulk mail in the examples aren't exhaustive; you can add and remove entries as necessary.</span></span> <span data-ttu-id="c5005-121">Однако они являются хорошей отправной точкой.</span><span class="sxs-lookup"><span data-stu-id="c5005-121">However, they are a good starting point.</span></span>

- <span data-ttu-id="c5005-p106">Поиск слов и текстовых шаблонов в теме или других полях заголовка сообщения выполняется *после* расшифровки сообщения, к которому применялся метод кодирования для передачи сообщений MIME. Этот метод используется для передачи двоичных сообщений между SMTP-серверами с преобразованием их в текст ASCII. Вы не можете применять условия или исключения для поиска необработанных закодированных значений (обычно в формате Base64) в теме или других полях заголовка сообщения.</span><span class="sxs-lookup"><span data-stu-id="c5005-p106">The search for words or text patterns in the subject or other header fields in the message occurs *after* the message has been decoded from the MIME content transfer encoding method that was used to transmit the binary message between SMTP servers in ASCII text. You can't use conditions or exceptions to search for the raw (typically, Base64) encoded values of the subject or other header fields in messages.</span></span>

- <span data-ttu-id="c5005-124">В приведенных ниже процедурах отмечаются массовые сообщения в качестве нежелательной почты для всей Организации.</span><span class="sxs-lookup"><span data-stu-id="c5005-124">The following procedures mark a bulk message as spam for your entire organization.</span></span> <span data-ttu-id="c5005-125">Однако вы можете добавить еще одно условие, чтобы применить эти правила только к определенным получателям, поэтому вы можете использовать агрессивную фильтрацию для нескольких пользователей с большим количеством целевых пользователей, а остальные пользователи (которые обычно получают массовые сообщения, на которые они подписаны) не затрагиваются.</span><span class="sxs-lookup"><span data-stu-id="c5005-125">However, you can add another condition to apply these rules only to specific recipients, so you can use aggressive filtering on a few, highly targeted users, while the rest of your users (who mostly get the bulk email they signed up for) aren't impacted.</span></span>

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="c5005-126">Использование центра администрирования Exchange для создания правил обработки сообщений, которые отфильтровывают групповые сообщения</span><span class="sxs-lookup"><span data-stu-id="c5005-126">Use the EAC to create mail flow rules that filter bulk email</span></span>

1. <span data-ttu-id="c5005-127">В Центре администрирования Exchange перейдите в раздел **Поток обработки почты** \> **Правила**.</span><span class="sxs-lookup"><span data-stu-id="c5005-127">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="c5005-128">Щелкните **Добавить** ![значок](../../media/ITPro-EAC-AddIcon.png) добавить, а затем выберите **создать новое правило**.</span><span class="sxs-lookup"><span data-stu-id="c5005-128">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="c5005-129">На открывшейся странице **Новое правило** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="c5005-129">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="c5005-130">**Name**: введите уникальное описательное имя правила.</span><span class="sxs-lookup"><span data-stu-id="c5005-130">**Name**: Enter a unique, descriptive name for the rule.</span></span>

   - <span data-ttu-id="c5005-131">Нажмите кнопку **Дополнительные параметры**.</span><span class="sxs-lookup"><span data-stu-id="c5005-131">Click **More Options**.</span></span>

   - <span data-ttu-id="c5005-132">**Применять это правило, если**: Настройте один из следующих параметров для поиска содержимого в сообщениях с помощью регулярных выражений (Regex) или слов или фраз:</span><span class="sxs-lookup"><span data-stu-id="c5005-132">**Apply this rule if**: Configure one of the following settings to look for content in messages using regular expressions (RegEx) or words or phrases:</span></span>

     - <span data-ttu-id="c5005-133">Тема **или** \> текст темы или текст сообщения **соответствует следующим текстовым шаблонам**: в появившемся диалоговом окне **Укажите слова или фразы** введите одно из следующих значений, нажмите **Добавить** ![значок](../../media/ITPro-EAC-AddIcon.png)"Добавить" и повторяйте столько раз, сколько необходимо.</span><span class="sxs-lookup"><span data-stu-id="c5005-133">**The subject or body** \> **subject or body matches these text patterns**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat as many times as necessary.</span></span>

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

      <span data-ttu-id="c5005-134">Чтобы изменить запись, выберите ее и нажмите кнопку **изменить** ![значок](../../media/ITPro-EAC-EditIcon.png)редактирования.</span><span class="sxs-lookup"><span data-stu-id="c5005-134">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="c5005-135">Чтобы удалить запись, выберите ее и нажмите кнопку **Удалить** ![значок](../../media/ITPro-EAC-DeleteIcon.png)"Удалить".</span><span class="sxs-lookup"><span data-stu-id="c5005-135">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="c5005-136">После этого нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c5005-136">When you're finished, click **OK**.</span></span>

     - <span data-ttu-id="c5005-137">**Тема или основной текст** \> **содержит любое из этих слов**: в появившемся диалоговом окне **Укажите слова или фразы** введите одно из следующих значений, нажмите **Добавить** ![значок](../../media/ITPro-EAC-AddIcon.png)"Добавить" и повторяйте столько раз, сколько необходимо.</span><span class="sxs-lookup"><span data-stu-id="c5005-137">**The subject or body** \> **subject or body includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat as many times as necessary.</span></span>

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

      <span data-ttu-id="c5005-138">Чтобы изменить запись, выберите ее и нажмите кнопку **изменить** ![значок](../../media/ITPro-EAC-EditIcon.png)редактирования.</span><span class="sxs-lookup"><span data-stu-id="c5005-138">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="c5005-139">Чтобы удалить запись, выберите ее и нажмите кнопку **Удалить** ![значок](../../media/ITPro-EAC-DeleteIcon.png)"Удалить".</span><span class="sxs-lookup"><span data-stu-id="c5005-139">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="c5005-140">После этого нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c5005-140">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="c5005-141">**Выполните следующие**действия: выберите **изменить свойства** \> сообщения **установите уровень вероятности нежелательной почты (SCL)**.</span><span class="sxs-lookup"><span data-stu-id="c5005-141">**Do the following**: Select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span> <span data-ttu-id="c5005-142">В появившемся диалоговом окне **Указание вероятности** настройте один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="c5005-142">In the **Specify SCL** dialog that appears, configure one of the following settings:</span></span>

     - <span data-ttu-id="c5005-143">Чтобы пометить сообщения как **Нежелательная почта**, выберите **6**.</span><span class="sxs-lookup"><span data-stu-id="c5005-143">To mark messages as **Spam**, select **6**.</span></span> <span data-ttu-id="c5005-144">Действие, настроенное для фильтрации **нежелательной почты** вердиктс в политиках защиты от нежелательной почты, применяется к сообщениям (значение по умолчанию — **Перемещение сообщения в папку нежелательной почты**).</span><span class="sxs-lookup"><span data-stu-id="c5005-144">The action that you've configured for **Spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

     - <span data-ttu-id="c5005-145">Чтобы пометить сообщения как **Нежелательная почта высокой надежности** , выберите **9**.</span><span class="sxs-lookup"><span data-stu-id="c5005-145">To mark messages as **High confidence spam** select **9**.</span></span> <span data-ttu-id="c5005-146">Действие, настроенное для фильтрации нежелательной **почты высокой надежности** , вердиктс в политиках защиты от нежелательной почты применяется к сообщениям (значение по умолчанию — **Перемещение сообщения в папку нежелательной почты**).</span><span class="sxs-lookup"><span data-stu-id="c5005-146">The action that you've configured for **High confidence spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

    <span data-ttu-id="c5005-147">Для получения дополнительных сведений о значениях ВЕРОЯТНОсти нежелательной почты [(SCL) в Office 365](spam-confidence-levels.md).</span><span class="sxs-lookup"><span data-stu-id="c5005-147">For more information about SCL values, see [Spam confidence level (SCL) in Office 365](spam-confidence-levels.md).</span></span>

   <span data-ttu-id="c5005-148">Когда все будет готово, нажмите кнопку **сохранить**</span><span class="sxs-lookup"><span data-stu-id="c5005-148">When you're finished, click **Save**</span></span>

## <a name="use-powershell-to-create-a-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="c5005-149">Создание правил для почтового процесса, которые отфильтровывают групповые сообщения, с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="c5005-149">Use PowerShell to create a mail flow rules that filter bulk email</span></span>

<span data-ttu-id="c5005-150">Используйте следующий синтаксис для создания одного или обоих правил для почтового процесса (регулярных выражений и слов):</span><span class="sxs-lookup"><span data-stu-id="c5005-150">Use the following syntax to create one or both of the mail flow rules (regular expressions vs. words):</span></span>

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPrhase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

<span data-ttu-id="c5005-151">В этом примере создается новое правило с именем "BULK Filtering Filtering — RegEx", которое использует тот же список регулярных выражений, начиная с предыдущего раздела, для настройки сообщений как **спама**.</span><span class="sxs-lookup"><span data-stu-id="c5005-151">This example creates a new rule named "Bulk email filtering - RegEx" that uses the same list of regular expressions from earlier in the topic to set messages as **Spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? sr\c=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

<span data-ttu-id="c5005-152">В этом примере создается новое правило с именем "массовая фильтрация электронной почты — слова", которая использует тот же список слов из предыдущего раздела, чтобы установить сообщения в качестве **нежелательной почты высокой достоверности**.</span><span class="sxs-lookup"><span data-stu-id="c5005-152">This example creates a new rule named "Bulk email filtering - Words" that uses the same list of words from earlier in the topic to set messages as **High confidence spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

<span data-ttu-id="c5005-153">Дополнительные сведения о синтаксисе и параметрах см. в статье [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).</span><span class="sxs-lookup"><span data-stu-id="c5005-153">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="c5005-154">Как убедиться, что все получилось?</span><span class="sxs-lookup"><span data-stu-id="c5005-154">How do you know this worked?</span></span>

<span data-ttu-id="c5005-155">Чтобы убедиться, что вы настроили правила обработки почты для фильтрации массовых сообщений электронной почты, выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="c5005-155">To verify that you've configured mail flow rules to filter bulk email, do any of the following steps:</span></span>

- <span data-ttu-id="c5005-156">В центре администрирования Exchange перейдите к разделу **правила** \> для обработки **почтового ящика** \> ,](../../media/ITPro-EAC-EditIcon.png)выберите правило \> щелкните **изменить** ![значок редактирования и проверьте параметры.</span><span class="sxs-lookup"><span data-stu-id="c5005-156">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="c5005-157">В PowerShell замените \<имя\> правила именем правила и выполните следующую команду, чтобы проверить параметры:</span><span class="sxs-lookup"><span data-stu-id="c5005-157">In PowerShell, replace \<Rule Name\> with the name of the rule, and run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- <span data-ttu-id="c5005-158">С внешней учетной записи отправьте тестовые сообщения затронутому получателю, который содержит одну из фраз или текстовых шаблонов, и проверьте результаты.</span><span class="sxs-lookup"><span data-stu-id="c5005-158">From an external account, send a test messages to an affected recipient that contains one of the phrases or text patterns, and verify the results.</span></span>
