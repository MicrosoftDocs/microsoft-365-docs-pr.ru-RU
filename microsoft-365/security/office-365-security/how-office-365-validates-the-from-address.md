---
title: Как Office 365 проверяет адрес отправителя для предотвращения фишинга
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
ms.date: 10/11/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- OWC150
- MET150
ms.assetid: eef8408b-54d3-4d7d-9cf7-ad2af10b2e0e
ms.collection:
- M365-security-compliance
description: Чтобы защититься от фишинга, Office 365 и Outlook.com теперь требуют соответствия требованиям RFC для адресов:.
ms.openlocfilehash: da1728b59ce100d988538d572a24ca1a44fa9a7b
ms.sourcegitcommit: 96cbcfe8b02a5efc2d5a4fc070753ea96f298fda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/28/2019
ms.locfileid: "37749161"
---
# <a name="how-office-365-validates-the-from-address-to-prevent-phishing"></a><span data-ttu-id="cc752-103">Как Office 365 проверяет адрес отправителя для предотвращения фишинга</span><span class="sxs-lookup"><span data-stu-id="cc752-103">How Office 365 validates the From address to prevent phishing</span></span>

<span data-ttu-id="cc752-104">Учетные записи электронной почты Office 365 и Outlook.com получают большое количество фишинговых атак.</span><span class="sxs-lookup"><span data-stu-id="cc752-104">Office 365 and Outlook.com email accounts receive an increasingly large number of phishing attacks.</span></span> <span data-ttu-id="cc752-105">Одним из фишинговых фишингов является отправка сообщений, которые содержат значения для адреса From:, не соответствующие [RFC 5322](https://tools.ietf.org/html/rfc5322).</span><span class="sxs-lookup"><span data-stu-id="cc752-105">One technique phishers use is to send messages that have values for the From: address that are not compliant with [RFC 5322](https://tools.ietf.org/html/rfc5322).</span></span> <span data-ttu-id="cc752-106">Адрес "от:" также называется адресом 5322. from.</span><span class="sxs-lookup"><span data-stu-id="cc752-106">The From: address is also called the 5322.From address.</span></span> <span data-ttu-id="cc752-107">Чтобы предотвратить такой тип фишинга, в Office 365 и Outlook.com необходимо, чтобы сообщения, полученные службой, включали в себя адрес, соответствующий спецификации RFC, как описано в этой статье.</span><span class="sxs-lookup"><span data-stu-id="cc752-107">To help prevent this type of phishing, Office 365 and Outlook.com require messages received by the service to include an RFC-compliant From: address as described in this article.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cc752-108">Сведения, приведенные в этой статье, требуют базового представления общего формата адресов электронной почты.</span><span class="sxs-lookup"><span data-stu-id="cc752-108">The information in this article requires you to have a basic understanding of the general format of email addresses.</span></span> <span data-ttu-id="cc752-109">Для получения дополнительных сведений ознакомьтесь со статьей [rfc 5322](https://tools.ietf.org/html/rfc5322) (в частности, разделами 3.2.3, 3,4 и 3.4.1), [RFC 5321](https://tools.ietf.org/html/rfc5321), а также [RFC 3696](https://tools.ietf.org/html/rfc3696).</span><span class="sxs-lookup"><span data-stu-id="cc752-109">For more information, see [RFC 5322](https://tools.ietf.org/html/rfc5322) (particularly sections 3.2.3, 3.4, and 3.4.1), [RFC 5321](https://tools.ietf.org/html/rfc5321), as well as [RFC 3696](https://tools.ietf.org/html/rfc3696).</span></span> <span data-ttu-id="cc752-110">В этой статье описывается применение политик для адреса 5322. from.</span><span class="sxs-lookup"><span data-stu-id="cc752-110">This article is about policy enforcement for the 5322.From address.</span></span> <span data-ttu-id="cc752-111">Эта статья не относится к 5321. MailFrom Address.</span><span class="sxs-lookup"><span data-stu-id="cc752-111">This article is not about the 5321.MailFrom address.</span></span> 
  
<span data-ttu-id="cc752-112">К сожалению, по-прежнему существуют некоторые устаревшие почтовые серверы в Интернете, которые продолжают отправлять "безопасные" сообщения электронной почты, отсутствующие или неправильно сформированные: адрес.</span><span class="sxs-lookup"><span data-stu-id="cc752-112">Unfortunately, there are still some legacy email servers on the Internet that continue to send "legitimate" email messages that have a missing or malformed From: address.</span></span> <span data-ttu-id="cc752-113">Если вы регулярно получаете электронную почту от организаций, использующих эти устаревшие системы, рекомендуйте этим организациям обновлять свои почтовые серверы, чтобы соответствовать современным стандартам безопасности.</span><span class="sxs-lookup"><span data-stu-id="cc752-113">If you regularly receive email from organizations that use these legacy systems, encourage those organizations to update their mail servers to comply with modern security standards.</span></span>
  
<span data-ttu-id="cc752-114">Корпорация Майкрософт начнет разбивать применение политик, описанных в этой статье, на 9 ноября 2017 г.</span><span class="sxs-lookup"><span data-stu-id="cc752-114">Microsoft will start rolling out enforcement of the policies described in this article on November 9, 2017.</span></span>
  
## <a name="how-office-365-enforces-the-use-of-a-valid-from-address-to-prevent-phishing-attacks"></a><span data-ttu-id="cc752-115">Как Office 365 обеспечивает использование допустимого адреса от: для предотвращения фишинговых атак</span><span class="sxs-lookup"><span data-stu-id="cc752-115">How Office 365 enforces the use of a valid From: address to prevent phishing attacks</span></span>

<span data-ttu-id="cc752-116">Office 365 вносит изменения в способ применения адреса "от:" в сообщениях, которые он получает для лучшей защиты от фишинговых атак.</span><span class="sxs-lookup"><span data-stu-id="cc752-116">Office 365 is making changes to the way it enforces the use of the From: address in messages it receives in order to better protect you from phishing attacks.</span></span> <span data-ttu-id="cc752-117">В этой статье</span><span class="sxs-lookup"><span data-stu-id="cc752-117">In this article:</span></span>
  
- [<span data-ttu-id="cc752-118">Все сообщения должны включать допустимый адрес от:</span><span class="sxs-lookup"><span data-stu-id="cc752-118">All messages must include a valid From: address</span></span>](how-office-365-validates-the-from-address.md#MustIncludeFromAddress)
    
- [<span data-ttu-id="cc752-119">Формат адреса "от:", если вы не укажете отображаемое имя</span><span class="sxs-lookup"><span data-stu-id="cc752-119">Format of the From: address if you don't include a display name</span></span>](how-office-365-validates-the-from-address.md#FormatNoDisplayName)
    
- [<span data-ttu-id="cc752-120">Формат адреса "от:", если вы включаете отображаемое имя</span><span class="sxs-lookup"><span data-stu-id="cc752-120">Format of the From: address if you include a display name</span></span>](how-office-365-validates-the-from-address.md#FormatDisplayName)
    
- [<span data-ttu-id="cc752-121">Дополнительные примеры допустимых и недопустимых адресов from:</span><span class="sxs-lookup"><span data-stu-id="cc752-121">Additional examples of valid and invalid From: addresses</span></span>](how-office-365-validates-the-from-address.md#Examples)
    
- [<span data-ttu-id="cc752-122">Отмена автоматического ответа на личный домен без нарушения политики "от:"</span><span class="sxs-lookup"><span data-stu-id="cc752-122">Suppress auto-replies to your custom domain without breaking the From: policy</span></span>](how-office-365-validates-the-from-address.md#SuppressAutoReply)
    
- [<span data-ttu-id="cc752-123">Переопределение Office 365 from: политика принудительного применения адресов</span><span class="sxs-lookup"><span data-stu-id="cc752-123">Overriding the Office 365 From: address enforcement policy</span></span>](how-office-365-validates-the-from-address.md#Override)
    
- [<span data-ttu-id="cc752-124">Другие способы предотвращения и защиты циберкримес в Office 365</span><span class="sxs-lookup"><span data-stu-id="cc752-124">Other ways to prevent and protect against cybercrimes in Office 365</span></span>](how-office-365-validates-the-from-address.md#OtherProtection)
    
<span data-ttu-id="cc752-125">На отправку от имени другого пользователя не влияет это изменение, для получения дополнительных сведений ознакомьтесь с раззинком "[что мы имеем в виду" отправителя сообщения электронной почты?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)".</span><span class="sxs-lookup"><span data-stu-id="cc752-125">Sending on behalf of another user is not affected by this change, for more details, read Terry Zink's blog "[What do we mean when we refer to the 'sender' of an email?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)".</span></span>
  
### <a name="all-messages-must-include-a-valid-from-address"></a><span data-ttu-id="cc752-126">Все сообщения должны включать допустимый адрес от:</span><span class="sxs-lookup"><span data-stu-id="cc752-126">All messages must include a valid From: address</span></span>
<span data-ttu-id="cc752-127"><a name="MustIncludeFromAddress"> </a></span><span class="sxs-lookup"><span data-stu-id="cc752-127"></span></span>

<span data-ttu-id="cc752-128">Некоторые автоматические сообщения не включают адрес отправителя при отправке.</span><span class="sxs-lookup"><span data-stu-id="cc752-128">Some automated messages don't include a From: address when they are sent.</span></span> <span data-ttu-id="cc752-129">В прошлое, когда Office 365 или Outlook.com получил сообщение без адреса "от:", служба добавила к сообщению следующий адрес по умолчанию: адрес, чтобы сделать его конечным.</span><span class="sxs-lookup"><span data-stu-id="cc752-129">In the past, when Office 365 or Outlook.com received a message without a From: address, the service added the following default From: address to the message in order to make it deliverable:</span></span>
  
```
From: <>
```

<span data-ttu-id="cc752-130">Начиная с 9 ноября 2017, Office 365 будет выполнять развертывание изменений в центрах обработки данных и почтовых серверах, которые приведут к применению нового правила, в котором сообщения без адреса "от:" не будут приниматься в Office 365 или Outlook.com.</span><span class="sxs-lookup"><span data-stu-id="cc752-130">Starting November 9, 2017, Office 365 will be rolling out changes to its datacenters and mail servers which will enforce a new rule where messages without a From: address will no longer be accepted by Office 365 or Outlook.com.</span></span> <span data-ttu-id="cc752-131">Вместо этого все сообщения, получаемые в Office 365, должны иметь действительный адрес от:.</span><span class="sxs-lookup"><span data-stu-id="cc752-131">Instead, all messages received by Office 365 must already contain a valid From: address.</span></span> <span data-ttu-id="cc752-132">В противном случае сообщение будет отправлено в папки "Нежелательная почта" или "Удаленные" в Outlook.com и Office 365.</span><span class="sxs-lookup"><span data-stu-id="cc752-132">Otherwise, the message will be sent to either the Junk Email or Deleted Items folders in Outlook.com and Office 365.</span></span> 
  
### <a name="syntax-overview-valid-format-for-the-from-address-for-office-365"></a><span data-ttu-id="cc752-133">Обзор синтаксиса: допустимый формат для адреса "от:" для Office 365</span><span class="sxs-lookup"><span data-stu-id="cc752-133">Syntax overview: Valid format for the From: address for Office 365</span></span>
<span data-ttu-id="cc752-134"><a name="SyntaxOverviewFromAddress"> </a></span><span class="sxs-lookup"><span data-stu-id="cc752-134"></span></span>

<span data-ttu-id="cc752-135">Формат значения адреса "от:" в нескольких документах RFC определен в подробностях.</span><span class="sxs-lookup"><span data-stu-id="cc752-135">The format for the value of the From: address is defined in detail across several RFCs.</span></span> <span data-ttu-id="cc752-136">Существует множество вариантов адресации, которые могут считаться действительными или недопустимыми.</span><span class="sxs-lookup"><span data-stu-id="cc752-136">There are many variations on addressing and what may be considered valid or invalid.</span></span> <span data-ttu-id="cc752-137">Для простоты Корпорация Майкрософт рекомендует использовать следующий формат и определения:</span><span class="sxs-lookup"><span data-stu-id="cc752-137">To keep it simple, Microsoft recommends that you use the following format and definitions:</span></span>
  
```
From: "displayname " <emailaddress >
```

<span data-ttu-id="cc752-138">Где:</span><span class="sxs-lookup"><span data-stu-id="cc752-138">Where:</span></span>
  
- <span data-ttu-id="cc752-139">Необязательно  *DisplayName* — это фраза, описывающая владельца адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="cc752-139">(Optional)  *displayname*  is a phrase that describes the owner of the email address.</span></span> <span data-ttu-id="cc752-140">Например, это может быть более понятное имя, описывающее отправителя по сравнению с именем почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="cc752-140">For example, this might be a more user-friendly name to describe the sender than the name of the mailbox.</span></span> <span data-ttu-id="cc752-141">Использование отображаемого имени не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="cc752-141">Using a display name is optional.</span></span> <span data-ttu-id="cc752-142">Тем не менее, если вы решили использовать отображаемое имя, корпорация Майкрософт рекомендует всегда заключать его в кавычки, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="cc752-142">However, if you choose to use a display name, Microsoft recommends that you always enclose it within quotation marks as shown.</span></span> 
    
- <span data-ttu-id="cc752-143">Потребоваться  *EmailAddress* состоит из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="cc752-143">(Required)  *emailaddress*  is made up of:</span></span> 
    
  ```
  local-part @domain
  ```

    <span data-ttu-id="cc752-144">Где:</span><span class="sxs-lookup"><span data-stu-id="cc752-144">Where:</span></span>
    
  - <span data-ttu-id="cc752-145">Потребоваться  *Local-Part* — это строка, которая определяет почтовый ящик, связанный с адресом.</span><span class="sxs-lookup"><span data-stu-id="cc752-145">(Required)  *local-part*  is a string that identifies the mailbox associated with the address.</span></span> <span data-ttu-id="cc752-146">Это значение уникально в пределах домена.</span><span class="sxs-lookup"><span data-stu-id="cc752-146">This is unique within the domain.</span></span> <span data-ttu-id="cc752-147">Часто имя пользователя или GUID владельца почтового ящика используются в качестве значения для локальной части.</span><span class="sxs-lookup"><span data-stu-id="cc752-147">Often, the mailbox owner's username or GUID is used as the value for the local-part.</span></span> 
    
  - <span data-ttu-id="cc752-148">Потребоваться  *domain* — полное доменное имя (FQDN) почтового сервера, на котором размещается почтовый ящик, определенный локальной частью адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="cc752-148">(Required)  *domain*  is the fully-qualified domain name (FQDN) of the mail server that hosts the mailbox identified by the local-part of the email address.</span></span> 
    
### <a name="format-of-the-from-address-if-you-dont-include-a-display-name"></a><span data-ttu-id="cc752-149">Формат адреса "от:", если вы не укажете отображаемое имя</span><span class="sxs-lookup"><span data-stu-id="cc752-149">Format of the From: address if you don't include a display name</span></span>
<span data-ttu-id="cc752-150"><a name="FormatNoDisplayName"> </a></span><span class="sxs-lookup"><span data-stu-id="cc752-150"></span></span>

<span data-ttu-id="cc752-151">Правильно отформатированный адрес от: адрес, который не содержит отображаемого имени, включает только один адрес электронной почты с угловыми скобками или без них.</span><span class="sxs-lookup"><span data-stu-id="cc752-151">A properly formatted From: address that does not include a display name includes only a single email address with or without angle brackets.</span></span> <span data-ttu-id="cc752-152">Корпорация Майкрософт рекомендует не разделять угловые скобки пробелами.</span><span class="sxs-lookup"><span data-stu-id="cc752-152">Microsoft recommends that you do not separate the angle brackets with spaces.</span></span> <span data-ttu-id="cc752-153">Кроме того, не включайте что-либо после адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="cc752-153">In addition, don't include anything after the email address.</span></span>
  
<span data-ttu-id="cc752-154">Допустимы следующие примеры:</span><span class="sxs-lookup"><span data-stu-id="cc752-154">The following examples are valid:</span></span>
  
```
From: sender@contoso.com
```

```
From: <sender@contoso.com>
```

<span data-ttu-id="cc752-155">Приведенный ниже пример является допустимым, но не рекомендуемым, так как содержит пробелы между угловыми скобками и адресом электронной почты:</span><span class="sxs-lookup"><span data-stu-id="cc752-155">The following example is valid but not recommended because it contains spaces between the angle brackets and the email address:</span></span>
  
```
From: < sender@contoso.com >
```

<span data-ttu-id="cc752-156">Следующий пример является недопустимым, так как он содержит текст после адреса электронной почты:</span><span class="sxs-lookup"><span data-stu-id="cc752-156">The following example is invalid because it contains text after the email address:</span></span>
  
```
From: "Office 365" <sender@contoso.com> (Sent by a process)
```

### <a name="format-of-the-from-address-if-you-include-a-display-name"></a><span data-ttu-id="cc752-157">Формат адреса "от:", если вы включаете отображаемое имя</span><span class="sxs-lookup"><span data-stu-id="cc752-157">Format of the From: address if you include a display name</span></span>
<span data-ttu-id="cc752-158"><a name="FormatDisplayName"> </a></span><span class="sxs-lookup"><span data-stu-id="cc752-158"></span></span>

<span data-ttu-id="cc752-159">Для: адреса, включающие значение для отображаемого имени, применяются следующие правила.</span><span class="sxs-lookup"><span data-stu-id="cc752-159">For From: addresses that include a value for the display name, the following rules apply:</span></span>
  
- <span data-ttu-id="cc752-160">Если адрес отправителя включает отображаемое имя, а отображаемое имя содержит запятую, отображаемое имя необходимо заключить в кавычки.</span><span class="sxs-lookup"><span data-stu-id="cc752-160">If the sender address includes a display name, and the display name includes a comma, then the display name must be enclosed within quotation marks.</span></span> <span data-ttu-id="cc752-161">Пример:</span><span class="sxs-lookup"><span data-stu-id="cc752-161">For example:</span></span>
    
    <span data-ttu-id="cc752-162">Приведенный ниже пример является допустимым:</span><span class="sxs-lookup"><span data-stu-id="cc752-162">The following example is valid:</span></span>
    
  ```
  From: "Sender, Example" <sender.example@contoso.com>
  ```

    <span data-ttu-id="cc752-163">Следующий пример является недопустимым:</span><span class="sxs-lookup"><span data-stu-id="cc752-163">The following example is not valid:</span></span>
    
  ```
  From: Sender, Example <sender.example@contoso.com>
  ```

    <span data-ttu-id="cc752-164">Не заключайте отображаемое имя в кавычки, если это отображаемое имя включает запятую в соответствии со спецификацией RFC 5322.</span><span class="sxs-lookup"><span data-stu-id="cc752-164">Not enclosing the display name in quotation marks if that display name includes a comma is invalid according to RFC 5322.</span></span>
    
    <span data-ttu-id="cc752-165">Рекомендуется заключить отображаемое имя в кавычки независимо от того, есть ли в отображаемом имени запятая.</span><span class="sxs-lookup"><span data-stu-id="cc752-165">As a best practice, put quote marks around the display name regardless of whether or not there is a comma within the display name.</span></span>
    
- <span data-ttu-id="cc752-166">Если адрес отправителя включает отображаемое имя, адрес электронной почты должен быть заключен в угловые скобки.</span><span class="sxs-lookup"><span data-stu-id="cc752-166">If the sender address includes a display name, then the email address must be enclosed within angle brackets.</span></span>
    
    <span data-ttu-id="cc752-167">Рекомендуется вставлять пробел между отображаемым именем и адресом электронной почты.</span><span class="sxs-lookup"><span data-stu-id="cc752-167">As a best practice, Microsoft strongly recommends that you insert a space between the display name and the email address.</span></span>
    
### <a name="additional-examples-of-valid-and-invalid-from-addresses"></a><span data-ttu-id="cc752-168">Дополнительные примеры допустимых и недопустимых адресов from:</span><span class="sxs-lookup"><span data-stu-id="cc752-168">Additional examples of valid and invalid From: addresses</span></span>
<span data-ttu-id="cc752-169"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="cc752-169"></span></span>

- <span data-ttu-id="cc752-170">Верно</span><span class="sxs-lookup"><span data-stu-id="cc752-170">Valid:</span></span>
    
  ```
  From: "Office 365" <sender@contoso.com>
  ```

- <span data-ttu-id="cc752-171">Недопустимый.</span><span class="sxs-lookup"><span data-stu-id="cc752-171">Invalid.</span></span> <span data-ttu-id="cc752-172">Адрес электронной почты не заключен в угловые скобки:</span><span class="sxs-lookup"><span data-stu-id="cc752-172">The email address is not enclosed with angle brackets:</span></span>
    
  ```
  From: Office 365 sender@contoso.com
  ```

- <span data-ttu-id="cc752-173">Допустимый, но не рекомендуемый.</span><span class="sxs-lookup"><span data-stu-id="cc752-173">Valid, but not recommended.</span></span> <span data-ttu-id="cc752-174">Отображаемое имя не находится в кавычках.</span><span class="sxs-lookup"><span data-stu-id="cc752-174">The display name is not in quotes.</span></span> <span data-ttu-id="cc752-175">Рекомендуется заключить отображаемое имя в кавычки:</span><span class="sxs-lookup"><span data-stu-id="cc752-175">As a best practice, always put quotation marks around the display name:</span></span>
    
  ```
  From: Office 365 <sender@contoso.com>
  ```

- <span data-ttu-id="cc752-176">Недопустимый.</span><span class="sxs-lookup"><span data-stu-id="cc752-176">Invalid.</span></span> <span data-ttu-id="cc752-177">Все заключено в кавычки, а не только отображаемое имя:</span><span class="sxs-lookup"><span data-stu-id="cc752-177">Everything is enclosed within quotation marks, not just the display name:</span></span>
    
  ```
  From: "Office 365 <sender@contoso.com>"
  ```

- <span data-ttu-id="cc752-178">Недопустимый.</span><span class="sxs-lookup"><span data-stu-id="cc752-178">Invalid.</span></span> <span data-ttu-id="cc752-179">Адреса электронной почты не заключены в угловые скобки:</span><span class="sxs-lookup"><span data-stu-id="cc752-179">There are no angle brackets around the email address:</span></span>
    
  ```
  From: "Office 365 <sender@contoso.com>" sender@contoso.com
  ```

- <span data-ttu-id="cc752-180">Недопустимый.</span><span class="sxs-lookup"><span data-stu-id="cc752-180">Invalid.</span></span> <span data-ttu-id="cc752-181">Между отображаемым именем и левой угловой скобкой нет пробелов:</span><span class="sxs-lookup"><span data-stu-id="cc752-181">There is no space between the display name and left angle bracket:</span></span>
    
  ```
  From: Office 365<sender@contoso.com>
  ```

- <span data-ttu-id="cc752-182">Недопустимый.</span><span class="sxs-lookup"><span data-stu-id="cc752-182">Invalid.</span></span> <span data-ttu-id="cc752-183">Между закрывающей кавычкой и левой угловой скобкой нет пробела.</span><span class="sxs-lookup"><span data-stu-id="cc752-183">There is no space between the closing quotation mark around the display name and the left angle bracket.</span></span>
    
  ```
  From: "Office 365"<sender@contoso.com>
  ```

### <a name="suppress-auto-replies-to-your-custom-domain-without-breaking-the-from-policy"></a><span data-ttu-id="cc752-184">Отмена автоматического ответа на личный домен без нарушения политики "от:"</span><span class="sxs-lookup"><span data-stu-id="cc752-184">Suppress auto-replies to your custom domain without breaking the From: policy</span></span>
<span data-ttu-id="cc752-185"><a name="SuppressAutoReply"> </a></span><span class="sxs-lookup"><span data-stu-id="cc752-185"></span></span>

<span data-ttu-id="cc752-186">С помощью применения политики "создать из: политика" вы больше не можете использовать \< \> : для отключения автоответов.</span><span class="sxs-lookup"><span data-stu-id="cc752-186">With the new From: policy enforcement, you can no longer use From: \<\> to suppress auto-replies.</span></span> <span data-ttu-id="cc752-187">Вместо этого необходимо настроить пустую запись MX для личного домена.</span><span class="sxs-lookup"><span data-stu-id="cc752-187">Instead, you need to set up a null MX record for your custom domain.</span></span>
  
<span data-ttu-id="cc752-188">Запись почтового обменника (MX) — это запись ресурса в DNS, которая определяет почтовый сервер, который получает почту для вашего домена.</span><span class="sxs-lookup"><span data-stu-id="cc752-188">The mail exchanger (MX) record is a resource record in DNS that identifies the mail server that receives mail for your domain.</span></span> <span data-ttu-id="cc752-189">Автоматические ответы (и все ответы) подавляются, так как отсутствует опубликованный адрес, на который отвечающий сервер может отправлять сообщения.</span><span class="sxs-lookup"><span data-stu-id="cc752-189">Auto-replies (and all replies) are naturally suppressed because there is no published address to which the responding server can send messages.</span></span>
  
<span data-ttu-id="cc752-190">При настройке пустой записи MX для личного домена:</span><span class="sxs-lookup"><span data-stu-id="cc752-190">When you set up a null MX record for your custom domain:</span></span>
  
- <span data-ttu-id="cc752-191">Выберите домен, из которого отправляются сообщения, которые не принимают (получают) сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="cc752-191">Choose a domain from which to send messages that doesn't accept (receive) email.</span></span> <span data-ttu-id="cc752-192">Например, если ваш основной домен — contoso.com, вы можете выбрать noreply.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="cc752-192">For example, if your primary domain is contoso.com, you might choose noreply.contoso.com.</span></span>
    
- <span data-ttu-id="cc752-193">Настройте пустую запись MX для вашего домена.</span><span class="sxs-lookup"><span data-stu-id="cc752-193">Set up the null MX record for your domain.</span></span> <span data-ttu-id="cc752-194">Пустая запись MX состоит из одной точки, например:</span><span class="sxs-lookup"><span data-stu-id="cc752-194">A null MX record consists of a single dot, for example:</span></span>
    
  ```
  noreply.contoso.com IN MX .
  ```

<span data-ttu-id="cc752-195">Дополнительные сведения о публикации пустых MX приведены в статье [RFC 7505](https://tools.ietf.org/html/rfc7505).</span><span class="sxs-lookup"><span data-stu-id="cc752-195">For more information about publishing a null MX, see [RFC 7505](https://tools.ietf.org/html/rfc7505).</span></span>
  
### <a name="overriding-the-office-365-from-address-enforcement-policy"></a><span data-ttu-id="cc752-196">Переопределение Office 365 from: политика принудительного применения адресов</span><span class="sxs-lookup"><span data-stu-id="cc752-196">Overriding the Office 365 From: address enforcement policy</span></span>
<span data-ttu-id="cc752-197"><a name="Override"> </a></span><span class="sxs-lookup"><span data-stu-id="cc752-197"></span></span>

<span data-ttu-id="cc752-198">После завершения развертывания новой политики можно обходить эту политику только для входящей почты, получаемой из Office 365, с помощью одного из следующих методов:</span><span class="sxs-lookup"><span data-stu-id="cc752-198">Once roll out of the new policy is complete, you can only bypass this policy for inbound mail you receive from Office 365 by using one of the following methods:</span></span> 
  
- <span data-ttu-id="cc752-199">Списки разрешенных IP-адресов</span><span class="sxs-lookup"><span data-stu-id="cc752-199">IP allow lists</span></span>
    
- <span data-ttu-id="cc752-200">Правила для почтового процесса Exchange Online</span><span class="sxs-lookup"><span data-stu-id="cc752-200">Exchange Online mail flow rules</span></span>
    
<span data-ttu-id="cc752-201">Корпорация Майкрософт настоятельно рекомендует переопределять принудительное применение политики "от:".</span><span class="sxs-lookup"><span data-stu-id="cc752-201">Microsoft strongly recommends against overriding the enforcement of the From: policy.</span></span> <span data-ttu-id="cc752-202">Переопределение этой политики может привести к снижению риска предоставления нежелательной почты, фишинга и других циберкримес в Организации.</span><span class="sxs-lookup"><span data-stu-id="cc752-202">Overriding this policy can increase your organization's risk of exposure to spam, phishing, and other cybercrimes.</span></span>
  
<span data-ttu-id="cc752-203">Вы не можете переопределить эту политику для исходящей почты, отправляемой в Office 365.</span><span class="sxs-lookup"><span data-stu-id="cc752-203">You cannot override this policy for outbound mail you send in Office 365.</span></span> <span data-ttu-id="cc752-204">Кроме того, Outlook.com запрещает переопределение любого вида даже через поддержку.</span><span class="sxs-lookup"><span data-stu-id="cc752-204">In addition, Outlook.com will not allow overrides of any kind, even through support.</span></span> 
  
### <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-office-365"></a><span data-ttu-id="cc752-205">Другие способы предотвращения и защиты циберкримес в Office 365</span><span class="sxs-lookup"><span data-stu-id="cc752-205">Other ways to prevent and protect against cybercrimes in Office 365</span></span>
<span data-ttu-id="cc752-206"><a name="OtherProtection"> </a></span><span class="sxs-lookup"><span data-stu-id="cc752-206"></span></span>

<span data-ttu-id="cc752-207">Дополнительные сведения о том, как можно усилить Организацию для циберкримес, например фишинга, нежелательной почты, нарушений данных и других угроз, приведены в статье [рекомендации по обеспечению безопасности для Office 365](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data).</span><span class="sxs-lookup"><span data-stu-id="cc752-207">For more information on how you can strengthen your organization against cybercrimes like phishing, spamming, data breaches, and other threats, see [Security best practices for Office 365](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="cc752-208">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="cc752-208">Related Topics</span></span>

[<span data-ttu-id="cc752-209">Подложные уведомления о недоставленном сообщении и EOP</span><span class="sxs-lookup"><span data-stu-id="cc752-209">Backscatter messages and EOP</span></span>](https://technet.microsoft.com/en-us/library/dn499795%28v=exchg.150%29.aspx)
  

