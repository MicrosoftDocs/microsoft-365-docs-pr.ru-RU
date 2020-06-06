---
title: Непроверенный отправитель
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: В этой статье рассказывается о том, как предотвратить достижение фишинговых сообщений для почтового ящика, Outlook.com и Outlook в Интернете.
ms.openlocfilehash: b49cc27685f62f5fb5d123a8a7aa4e51e0065e64
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2020
ms.locfileid: "44588340"
---
# <a name="unverified-sender"></a><span data-ttu-id="8f896-103">Непроверенный отправитель</span><span class="sxs-lookup"><span data-stu-id="8f896-103">Unverified Sender</span></span>

> [!NOTE]
> <span data-ttu-id="8f896-104">Эти обновления выводятся сейчас и могут быть недоступны для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="8f896-104">These updates are rolling out now, and might not be available for all users.</span></span> <span data-ttu-id="8f896-105">Эта функция поддерживается для пользователей Enterprise Outlook.com и корпоративных приложений Win32 для Outlook.</span><span class="sxs-lookup"><span data-stu-id="8f896-105">This feature is supported for Enterprise Outlook.com and Enterprise Outlook Win32 desktop users.</span></span> <span data-ttu-id="8f896-106">В настоящее время оно недоступно для пользователей Office 365.</span><span class="sxs-lookup"><span data-stu-id="8f896-106">It is not currently available for consumer Office 365 users.</span></span>

<span data-ttu-id="8f896-107">Чтобы предотвратить доступ к почтовому ящику с помощью фишинговых сообщений, Office 365 проверяет, что отправители говорят о том, что они говорят о том, что они говорят о нежелательной почте и отмечают подозрительные сообщения.</span><span class="sxs-lookup"><span data-stu-id="8f896-107">To prevent phishing messages from reaching your mailbox, Office 365 verifies that the senders are who they say they are and mark suspicious messages as junk email.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8f896-108">Если сообщение помечено как фишинг, Outlook отображает предупреждение в верхней части страницы, но все ссылки в сообщении все равно можно открыть.</span><span class="sxs-lookup"><span data-stu-id="8f896-108">When a message is marked as a phishing scam, Outlook displays a warning at the top of the page, but any links in the message can still be opened.</span></span>

## <a name="how-can-i-identify-a-suspicious-message-in-my-inbox"></a><span data-ttu-id="8f896-109">Как определить подозрительные сообщения в папке "Входящие"?</span><span class="sxs-lookup"><span data-stu-id="8f896-109">How can I identify a suspicious message in my inbox?</span></span>

<span data-ttu-id="8f896-110">В Outlook отображаются индикаторы, когда отправитель сообщения не может быть идентифицирован или его удостоверение отличается от того, которое отображается в адресе отправителя.</span><span class="sxs-lookup"><span data-stu-id="8f896-110">Outlook shows indicators when the sender of a message either can't be identified or their identity is different from what you see in the From address.</span></span>

## <a name="you-see-a--in-the-sender-image"></a><span data-ttu-id="8f896-111">Отображается значок "?" в изображении отправителя</span><span class="sxs-lookup"><span data-stu-id="8f896-111">You see a '?' in the sender image</span></span>

<span data-ttu-id="8f896-112">Когда Office 365 не удается проверить подлинность отправителя с помощью методик проверки подлинности электронной почты, в изображении отправителя отображается "?".</span><span class="sxs-lookup"><span data-stu-id="8f896-112">When Office 365 can't verify the identity of the sender using email authentication techniques, a '?' is displayed in the sender image.</span></span>

![Сообщение не прошел проверку](../../media/message-did-not-pass-verification.jpg)

<span data-ttu-id="8f896-114">Не все сообщения, которые не прошли проверку подлинности, являются вредоносными.</span><span class="sxs-lookup"><span data-stu-id="8f896-114">Not every message that fails to authenticate is malicious.</span></span> <span data-ttu-id="8f896-115">Однако следует быть внимательным при взаимодействии с сообщениями, которые не прошли проверку подлинности, если вы не распознаете отправителя.</span><span class="sxs-lookup"><span data-stu-id="8f896-115">However, you should be careful about interacting with messages that don't authenticate if you don't recognize the sender.</span></span> <span data-ttu-id="8f896-116">Или, если вы распознаете отправителя, который обычно не содержит "?" в изображении отправителя, но вы неожиданно видите его, это может быть подписание отправителя.</span><span class="sxs-lookup"><span data-stu-id="8f896-116">Or, if you recognize a sender that normally doesn't have a '?' in the sender image, but you suddenly start seeing it, that could be a sign the sender is being spoofed.</span></span>

## <a name="how-to-manage-which-messages-receive-the-unverified-sender-treatment"></a><span data-ttu-id="8f896-117">Как управлять сообщениями, принимающими непроверенные отправители</span><span class="sxs-lookup"><span data-stu-id="8f896-117">How to manage which messages receive the unverified sender treatment</span></span> 

<span data-ttu-id="8f896-118">Если вы являетесь клиентом Office 365, вы можете управлять этим компонентом с помощью центра безопасности & соответствия требованиям Office 365.</span><span class="sxs-lookup"><span data-stu-id="8f896-118">If you are an Office 365 customer you can manage this feature through the Office 365 Security & Compliance Center.</span></span>

- <span data-ttu-id="8f896-119">В центре безопасности & соответствия требованиям глобальные администраторы и администраторы безопасности могут включать и отключать эту функцию с помощью защиты от спуфинга в политике защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="8f896-119">In the Security & Compliance Center, global or security administrators can turn the feature on or off, through anti-spoofing protection under the Anti-Phish policy.</span></span> <span data-ttu-id="8f896-120">Кроме того, вы можете использовать командлет **Set-AntiPhishPolicy** в Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8f896-120">Additionally, you can use the **Set-AntiPhishPolicy** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="8f896-121">Дополнительные сведения см [в статье Защита от фишинга в Office 365](anti-phishing-protection.md) и [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/set-antiphishpolicy).</span><span class="sxs-lookup"><span data-stu-id="8f896-121">For details, see [Anti-phishing protection in Office 365](anti-phishing-protection.md) and [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/set-antiphishpolicy).</span></span>

    ![Изменение отправителя, не прошедшего проверку подлинности, в графическом интерфейсе.](../../media/unverified-sender-article-editing-unauthenticated-senders.jpg)

- <span data-ttu-id="8f896-123">Если администратор определил ложное срабатывание, а отправитель не должен получать непроверенную обработку отправителя, можно выполнить одно из следующих действий, чтобы добавить отправителя в список разрешенных поддельных поддельных поддельных поддельных поддельных подделки:</span><span class="sxs-lookup"><span data-stu-id="8f896-123">If an admin has identified a false positive, and a sender should not be receiving the unverified sender treatment, one of the following actions can be taken to add the sender to the Spoof Intelligence spoof allow list:</span></span>

  - <span data-ttu-id="8f896-124">Добавьте доменную связь с помощью анализа сведений о подделких.</span><span class="sxs-lookup"><span data-stu-id="8f896-124">Add the domain pair through the Spoof Intelligence Insight.</span></span> <span data-ttu-id="8f896-125">Дополнительные сведения [: обзор подделки информации](walkthrough-spoof-intelligence-insight.md).</span><span class="sxs-lookup"><span data-stu-id="8f896-125">For details, see [Walkthrough: spoof intelligence insight](walkthrough-spoof-intelligence-insight.md).</span></span>

  - <span data-ttu-id="8f896-126">Добавьте доменную комбинацию с помощью командлета **Set-PhishFilterPolicy** в Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8f896-126">Add the domain pair through the **Set-PhishFilterPolicy** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="8f896-127">Дополнительные сведения: [Set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-phishfilterpolicy) и [Настройка антифишинга Office 365 ATP и политики защиты от фишинга](set-up-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="8f896-127">For details, see [Set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-phishfilterpolicy) and [Set up Office 365 ATP anti-phishing and anti-phishing policies](set-up-anti-phishing-policies.md).</span></span>

<span data-ttu-id="8f896-128">Кроме того, мы не будем применять непроверенный отправитель, если сообщение было доставлено в папку "Входящие" с помощью правил для почтового процесса (которые также называются правилами транспорта) или списком безопасных доменов (политик защиты от нежелательной почты).</span><span class="sxs-lookup"><span data-stu-id="8f896-128">Additionally, we don't apply the unverified sender treatment if the message was delivered to the Inbox via mail flow rules (also known as transport rules) or the Safe Domain List (anti-spam policies).</span></span>

## <a name="how-to-manage-the-via-tag"></a><span data-ttu-id="8f896-129">Как управлять тегом "Via"</span><span class="sxs-lookup"><span data-stu-id="8f896-129">How to manage the 'via' tag</span></span> 

<span data-ttu-id="8f896-130">Если вы являетесь клиентом Office 365, вы можете управлять этим компонентом с помощью центра безопасности & соответствия требованиям Office 365, аналогично тому, как вы управляете непроверенным способом отправителя.</span><span class="sxs-lookup"><span data-stu-id="8f896-130">If you are an Office 365 customer you can manage this feature through the Office 365 Security & Compliance center, the same way that you manage the unverified sender treatment.</span></span> <span data-ttu-id="8f896-131">Если добавить отправителя в список разрешенных поддельных поддельных поддельных поддельных поддельных поддельных поддельных подделкий, то обработка</span><span class="sxs-lookup"><span data-stu-id="8f896-131">If you add the sender to the Spoof Intelligence spoof allow list, the 'via' treatment will not be applied.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="8f896-132">Вопросы и ответы</span><span class="sxs-lookup"><span data-stu-id="8f896-132">Frequently asked questions</span></span>

### <a name="what-criteria-does-outlookcom-and-outlook-win32-desktop-use-to-add-the--and-the-via-properties"></a><span data-ttu-id="8f896-133">В каких критериях Outlook.com и Outlook для рабочего стола Win32 используется для добавления свойств "?" и "Via"?</span><span class="sxs-lookup"><span data-stu-id="8f896-133">What criteria does Outlook.com and Outlook Win32 desktop use to add the '?' and the 'via' properties?</span></span>

<span data-ttu-id="8f896-134">Для "?" в образе отправителя: Outlook.com требует, чтобы сообщение передавало либо проверку подлинности SPF, либо проверку подлинности DKIM, либо был получен либо проход dMarc, либо составной проход проверки подлинности из службы Office 365 спуфинг.</span><span class="sxs-lookup"><span data-stu-id="8f896-134">For the '?' in the sender image:  Outlook.com requires that the message pass either SPF or DKIM authentication and receive either a dmarc pass, or a composite authentication pass from Office 365 Spoof Intelligence.</span></span> <span data-ttu-id="8f896-135">Дополнительные сведения см. в статье [Set up SPF in Office 365, чтобы предотвратить спуфинг](set-up-spf-in-office-365-to-help-prevent-spoofing.md) и [использовать DKIM для проверки исходящей электронной почты, отправленной из личного домена в Office 365](use-dkim-to-validate-outbound-email.md).</span><span class="sxs-lookup"><span data-stu-id="8f896-135">For details, see [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) and [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span></span>

<span data-ttu-id="8f896-136">Для тега Via: Если домен, указанный в адресе отправителя, отличается от домена в подписи DKIM или в SMTP-почте FROM, Outlook.com отображает домен в одном из этих двух полей (предложив подпись DKIM).</span><span class="sxs-lookup"><span data-stu-id="8f896-136">For the via tag: If the domain in the From address is different from the domain in the DKIM signature or the SMTP MAIL FROM, Outlook.com displays the domain in one of those two fields (preferring the DKIM signature).</span></span>

### <a name="how-do-i-remove-the--without-utilizing-the-spoof-intelligence-spoof-allow-list"></a><span data-ttu-id="8f896-137">Как удалить "?", не используя список разрешенных поддельных поддельных поддельных поддельных подделки?</span><span class="sxs-lookup"><span data-stu-id="8f896-137">How do I remove the '?' without utilizing the Spoof Intelligence spoof allow list?</span></span>

<span data-ttu-id="8f896-138">Для "?" в изображении отправителя: в качестве отправителя необходимо проверить подлинность сообщения с помощью SPF или DKIM.</span><span class="sxs-lookup"><span data-stu-id="8f896-138">For the '?' in the sender image: As a sender, you should authenticate your message with either SPF or DKIM.</span></span>

<span data-ttu-id="8f896-139">Для тега Via: в качестве отправителя необходимо убедиться, что домен в подписи DKIM или SMTP-почте — то же, что и, или является поддоменом домена, в адресе отправителя.</span><span class="sxs-lookup"><span data-stu-id="8f896-139">For the via tag: As a sender, you should ensure that either the domain in the DKIM signature or the SMTP MAIL FROM is the same as, or is a subdomain of, the domain in the From address.</span></span>

### <a name="do-outlookcom-and-outlook-win32-desktop-show-this-for-every-message-that-doesnt-pass-authentication"></a><span data-ttu-id="8f896-140">Outlook.com и Outlook для рабочего стола Win32 показывать это сообщение для каждого сообщения, которое не проходит проверку подлинности?</span><span class="sxs-lookup"><span data-stu-id="8f896-140">Do Outlook.com and Outlook Win32 desktop show this for every message that doesn't pass authentication?</span></span>

<span data-ttu-id="8f896-141">Не обязательно.</span><span class="sxs-lookup"><span data-stu-id="8f896-141">Not necessarily.</span></span> <span data-ttu-id="8f896-142">Кроме того, для проверки подлинности отправителя в Office 365 могут быть другими свойствами сообщения.</span><span class="sxs-lookup"><span data-stu-id="8f896-142">Office 365 may have other properties within the message to authenticate the sender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8f896-143">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="8f896-143">Related topics</span></span>

[<span data-ttu-id="8f896-144">Защитите свою учетную запись электронной почты Outlook.com</span><span class="sxs-lookup"><span data-stu-id="8f896-144">Help protect your Outlook.com email account</span></span>](https://support.microsoft.com/office/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

[<span data-ttu-id="8f896-145">Работа с фишингом или подменой в Outlook.com</span><span class="sxs-lookup"><span data-stu-id="8f896-145">Deal with phishing or spoofing in Outlook.com</span></span>](https://support.office.com/article/0d882ea5-eedc-4bed-aebc-079ffa1105a3)

[<span data-ttu-id="8f896-146">Фильтрация нежелательной почты и спама в Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="8f896-146">Filter junk email and spam in Outlook on the web</span></span>](https://support.microsoft.com/office/db786e79-54e2-40cc-904f-d89d57b7f41d)
