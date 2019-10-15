---
title: Непроверенный отправитель
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/11/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Чтобы предотвратить доступ к почтовому ящику с помощью фишинговых сообщений, Outlook.com и Outlook в Интернете убедитесь, что отправитель говорят, что они говорят о них и помечают подозрительные сообщения как нежелательная почта.
ms.openlocfilehash: 1b6c834f5d54c54a577b51edf5f135e30990a92c
ms.sourcegitcommit: 9db133b110956bff2942bc903a4484247fc7020a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "37510546"
---
# <a name="unverified-sender"></a><span data-ttu-id="76495-103">Непроверенный отправитель</span><span class="sxs-lookup"><span data-stu-id="76495-103">Unverified Sender</span></span>

> [!NOTE] 
> <span data-ttu-id="76495-104">Эти обновления выводятся сейчас и могут быть недоступны для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="76495-104">These updates are rolling out now, and might not be available yet for all users.</span></span>

<span data-ttu-id="76495-105">Чтобы предотвратить доступ к почтовому ящику с помощью фишинговых сообщений, Outlook.com и Outlook в Интернете убедитесь, что отправитель говорят, что они говорят о них и помечают подозрительные сообщения как нежелательная почта.</span><span class="sxs-lookup"><span data-stu-id="76495-105">To prevent phishing messages from reaching your mailbox, Outlook.com and Outlook on the web verify that the sender is who they say they are and mark suspicious messages as junk email.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="76495-106">Если сообщение помечено как фишинг, в Outlook.com и Outlook в Интернете отображается предупреждение в верхней части страницы, но все ссылки в сообщении все равно могут быть открыты.</span><span class="sxs-lookup"><span data-stu-id="76495-106">When a message is marked as a phishing scam, Outlook.com and Outlook on the web display a warning at the top of the page, but any links in the message can still be opened.</span></span>

## <a name="how-can-i-identify-a-suspicious-message-in-my-inbox"></a><span data-ttu-id="76495-107">Как определить подозрительные сообщения в папке "Входящие"?</span><span class="sxs-lookup"><span data-stu-id="76495-107">How can I identify a suspicious message in my inbox?</span></span>

<span data-ttu-id="76495-108">Outlook.com и Outlook в Интернете показывают индикаторы, когда отправитель сообщения не может быть идентифицирован или его удостоверение отличается от того, что отображается в адресе отправителя.</span><span class="sxs-lookup"><span data-stu-id="76495-108">Outlook.com and Outlook on the web show indicators when the sender of a message either can't be identified or their identity is different from what you see in the From address.</span></span>

## <a name="how-to-manage-which-messages-receive-the-unverified-sender-treatment"></a><span data-ttu-id="76495-109">Как управлять сообщениями, принимающими непроверенные отправители</span><span class="sxs-lookup"><span data-stu-id="76495-109">How to manage which messages receive the unverified sender treatment</span></span> 

<span data-ttu-id="76495-110">Если вы являетесь клиентом Office 365, вы можете управлять этим компонентом с помощью центра безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="76495-110">If you are an Office 365 customer you can manage this feature through the Security & Compliance Center.</span></span> 

- <span data-ttu-id="76495-111">В центре безопасности Office 365 &, глобальные администраторы и администраторы безопасности могут включать и отключать эту функцию с помощью защиты от спуфинга в политике защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="76495-111">In the Office 365 Security & Compliance Center, global or security administrators can turn the feature on or off, through anti-spoofing protection under the Anti-Phish policy.</span></span> <span data-ttu-id="76495-112">Кроме того, управлять ими можно с помощью командлета "Set – AntiPhishPolicy".</span><span class="sxs-lookup"><span data-stu-id="76495-112">Additionally, it can be managed through the ‘Set-AntiPhishPolicy’ cmdlet.</span></span> <span data-ttu-id="76495-113">Более подробную информацию можно узнать [в статье Защита от фишинга в Office 365](anti-phishing-protection.md) и [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-antiphishpolicy?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="76495-113">For more details, see [Anti-phishing protection in Office 365](anti-phishing-protection.md) and [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-antiphishpolicy?view=exchange-ps).</span></span>

    ![Изменение отправителя, не прошедшего проверку подлинности, в графическом интерфейсе.](../media/unverified-sender-article-editing-unauthenticated-senders.jpg)

- <span data-ttu-id="76495-115">Если администратор определил ложное срабатывание, а отправитель не может получить непроверенный отправитель, он может выполнить одно из следующих действий, чтобы добавить отправителя в список разрешенных поддельных поддельных поддельных поддельных поддельных подделки:</span><span class="sxs-lookup"><span data-stu-id="76495-115">If an admin has identified a false positive, and a sender should not be receiving the unverified sender treatment they can take one of the following actions to add the sender to the Spoof Intelligence spoof allow list:</span></span>
        
    - <span data-ttu-id="76495-116">Добавьте доменную связь с помощью анализа сведений о подделких.</span><span class="sxs-lookup"><span data-stu-id="76495-116">Add the domain pair through the Spoof Intelligence Insight.</span></span> <span data-ttu-id="76495-117">Для получения дополнительных сведений см. Пошаговое руководство по подделке анализа</span><span class="sxs-lookup"><span data-stu-id="76495-117">For more details, see Walkthrough: spoof intelligence insight</span></span>
                
    - <span data-ttu-id="76495-118">Добавьте доменную комбинацию с помощью командлета PhishFilterPolicy.</span><span class="sxs-lookup"><span data-stu-id="76495-118">Add the domain pair through the PhishFilterPolicy cmdlet.</span></span> <span data-ttu-id="76495-119">Дополнительные сведения: Set – PhishFilterPolicy и защита от спуфинга в Office 365</span><span class="sxs-lookup"><span data-stu-id="76495-119">For more details, see Set-PhishFilterPolicy and Anti-spoofing protection in Office 365</span></span>

<span data-ttu-id="76495-120">Кроме того, мы не применяем непроверенный отправитель, если он был доставлен в папку "Входящие" с помощью списка разрешений администратора, включая правила транспорта электронной почты (ETR), список надежных доменов (политика защиты от нежелательной почты), список надежных отправителей или пользователь установил в качестве этого пользователя "надежный отправитель". папке Входящие ".</span><span class="sxs-lookup"><span data-stu-id="76495-120">Additionally, we do not apply the unverified sender treatment if it was delivered to the inbox via an admin allow list, including Email Transport Rules (ETRs), Safe Domain List (Anti-Spam Policy), Safe Sender List or a user has set this user as a “Safe Sender” in their inbox.</span></span>

### <a name="you-see-a--in-the-sender-image"></a><span data-ttu-id="76495-121">Отображается значок "?" в изображении отправителя</span><span class="sxs-lookup"><span data-stu-id="76495-121">You see a '?' in the sender image</span></span>

<span data-ttu-id="76495-122">Когда Outlook.com и Outlook в Интернете не могут проверить подлинность отправителя с помощью методов проверки подлинности электронной почты, в фотографии отправителя отображается "?".</span><span class="sxs-lookup"><span data-stu-id="76495-122">When Outlook.com and Outlook on the web can't verify the identity of the sender using email authentication techniques, they display a '?' in the sender photo.</span></span> 

![Сообщение не прошел проверку](../media/message-did-not-pass-verification.jpg)

<span data-ttu-id="76495-124">Не все сообщения, которые не прошли проверку подлинности, являются вредоносными.</span><span class="sxs-lookup"><span data-stu-id="76495-124">Not every message that fails to authenticate is malicious.</span></span> <span data-ttu-id="76495-125">Однако следует быть внимательным при взаимодействии с сообщениями, которые не прошли проверку подлинности, если вы не распознаете отправителя.</span><span class="sxs-lookup"><span data-stu-id="76495-125">However, you should be careful about interacting with messages that don't authenticate if you don't recognize the sender.</span></span> <span data-ttu-id="76495-126">Или, если вы распознаете отправителя, который обычно не содержит "?" в изображении отправителя, но вы неожиданно видите его, это может быть подписание отправителя.</span><span class="sxs-lookup"><span data-stu-id="76495-126">Or, if you recognize a sender that normally doesn't have a '?' in the sender image, but you suddenly start seeing it, that could be a sign the sender is being spoofed.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="76495-127">Вопросы и ответы</span><span class="sxs-lookup"><span data-stu-id="76495-127">Frequently asked questions</span></span>

### <a name="what-criteria-does-outlookcom-and-outlook-on-the-web-use-to-add-the--and-the-via-properties"></a><span data-ttu-id="76495-128">Какие условия Outlook.com и Outlook в Интернете используют для добавления свойств "?" и "Via"?</span><span class="sxs-lookup"><span data-stu-id="76495-128">What criteria does Outlook.com and Outlook on the web use to add the '?' and the 'via' properties?</span></span>

<span data-ttu-id="76495-129">Для "?" в образе отправителя: Outlook.com требует, чтобы сообщение передавало либо проверку подлинности SPF, либо проверку подлинности DKIM, либо был получен либо проход dMarc, либо составной проход проверки подлинности из службы Office 365 спуфинг.</span><span class="sxs-lookup"><span data-stu-id="76495-129">For the '?' in the sender image:  Outlook.com requires that the message pass either SPF or DKIM authentication and receive either a dmarc pass, or a composite authentication pass from Office 365 Spoof Intelligence.</span></span> <span data-ttu-id="76495-130">Дополнительные сведения см. в статье [Set up SPF in Office 365, чтобы предотвратить спуфинг](set-up-spf-in-office-365-to-help-prevent-spoofing.md) и [использовать DKIM для проверки исходящей электронной почты, отправленной из личного домена в Office 365](use-dkim-to-validate-outbound-email.md).</span><span class="sxs-lookup"><span data-stu-id="76495-130">For more details, see [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) and [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span></span>

<span data-ttu-id="76495-131">Для тега Via: Если домен, указанный в адресе отправителя, отличается от домена в подписи DKIM или в SMTP-почте FROM, Outlook.com отображает домен в одном из этих двух полей (предложив подпись DKIM).</span><span class="sxs-lookup"><span data-stu-id="76495-131">For the via tag: If the domain in the From address is different from the domain in the DKIM signature or the SMTP MAIL FROM, Outlook.com displays the domain in one of those two fields (preferring the DKIM signature).</span></span>

### <a name="how-do-i-remove-the-"></a><span data-ttu-id="76495-132">Как удалить "?"</span><span class="sxs-lookup"><span data-stu-id="76495-132">How do I remove the '?'</span></span>

<span data-ttu-id="76495-133">Для "?" в изображении отправителя: в качестве отправителя необходимо проверить подлинность сообщения с помощью SPF или DKIM.</span><span class="sxs-lookup"><span data-stu-id="76495-133">For the '?' in the sender image: As a sender, you should authenticate your message with either SPF or DKIM.</span></span>

<span data-ttu-id="76495-134">Для тега Via: в качестве отправителя необходимо убедиться, что домен в подписи DKIM или SMTP-почте — то же, что и, или является поддоменом домена, в адресе отправителя.</span><span class="sxs-lookup"><span data-stu-id="76495-134">For the via tag: As a sender, you should ensure that either the domain in the DKIM signature or the SMTP MAIL FROM is the same as, or is a subdomain of, the domain in the From address.</span></span>

### <a name="does-outlookcom-and-outlook-on-the-web-show-this-for-every-message-that-doesnt-pass-authentication"></a><span data-ttu-id="76495-135">Выполняет ли Outlook.com и Outlook в Интернете показывать это значение для каждого сообщения, которое не проходит проверку подлинности?</span><span class="sxs-lookup"><span data-stu-id="76495-135">Does Outlook.com and Outlook on the web show this for every message that doesn’t pass authentication?</span></span>

<span data-ttu-id="76495-136">Не обязательно.</span><span class="sxs-lookup"><span data-stu-id="76495-136">Not necessarily.</span></span> <span data-ttu-id="76495-137">Outlook.com и Outlook в Интернете могут иметь другие свойства в сообщении для проверки подлинности отправителя.</span><span class="sxs-lookup"><span data-stu-id="76495-137">Outlook.com and Outlook on the web may have other properties within the message to authenticate the sender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="76495-138">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="76495-138">Related topics</span></span>

[<span data-ttu-id="76495-139">Защитите свою учетную запись электронной почты Outlook.com</span><span class="sxs-lookup"><span data-stu-id="76495-139">Help protect your Outlook.com email account</span></span>](https://support.office.com/article/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

[<span data-ttu-id="76495-140">Работа с нарушениями, фишингом и подменой в Outlook.com</span><span class="sxs-lookup"><span data-stu-id="76495-140">Deal with abuse, phishing, or spoofing in Outlook.com</span></span>](https://support.office.com/article/0d882ea5-eedc-4bed-aebc-079ffa1105a3)

[<span data-ttu-id="76495-141">Фильтрация нежелательной почты и спама в Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="76495-141">Filter junk email and spam in Outlook on the web</span></span>](https://support.office.com/article/db786e79-54e2-40cc-904f-d89d57b7f41d)
