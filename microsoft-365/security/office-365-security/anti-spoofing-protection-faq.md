---
title: Вопросы и ответы о защите от спуфинга
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365-initiative-defender-office365
description: Администраторы могут просматривать часто задаваемые вопросы и ответы о защите от спуфинга в Exchange Online Protection (EOP).
ms.openlocfilehash: 57ca258e2990719e50a84a402e0b4ff7db1c229e
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/09/2020
ms.locfileid: "48411726"
---
# <a name="anti-spoofing-protection-faq"></a><span data-ttu-id="36e11-103">Вопросы и ответы о защите от спуфинга</span><span class="sxs-lookup"><span data-stu-id="36e11-103">Anti-spoofing protection FAQ</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="36e11-104">В этой статье приведены часто задаваемые вопросы и ответы о защите от спуфинга для организаций Microsoft 365 с почтовыми ящиками в Exchange Online или отдельными организациями Exchange Online Protection (EOP) без почтовых ящиков Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="36e11-104">This article provides frequently asked questions and answers about anti-spoofing protection for Microsoft 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="36e11-105">Вопросы и ответы по защите от нежелательной почты приведены в статье [вопросы и ответы по защите от нежелательной почты](anti-spam-protection-faq.md).</span><span class="sxs-lookup"><span data-stu-id="36e11-105">For questions and answers about anti-spam protection, see [Anti-spam protection FAQ](anti-spam-protection-faq.md).</span></span>

<span data-ttu-id="36e11-106">Вопросы и ответы о защите от вредоносных программ приведены в статье [вопросы и ответы по защите от вредоносных программ](anti-malware-protection-faq-eop.md)</span><span class="sxs-lookup"><span data-stu-id="36e11-106">For questions and answers about anti-malware protection, see [Anti-malware protection FAQ](anti-malware-protection-faq-eop.md)</span></span>

## <a name="why-did-microsoft-choose-to-junk-unauthenticated-inbound-email"></a><span data-ttu-id="36e11-107">Почему Майкрософт выбирает нежелательную входящую почту, не прошедший проверку подлинности?</span><span class="sxs-lookup"><span data-stu-id="36e11-107">Why did Microsoft choose to junk unauthenticated inbound email?</span></span>

<span data-ttu-id="36e11-108">Корпорация Майкрософт считает, что риск пропуска входящей электронной почты, не прошедший проверку подлинности, должен быть выше, чем риск потери входящей электронной почты.</span><span class="sxs-lookup"><span data-stu-id="36e11-108">Microsoft believes that the risk of continuing to allow unauthenticated inbound email is higher than the risk of losing legitimate inbound email.</span></span>

## <a name="does-junking-unauthenticated-inbound-email-cause-legitimate-email-to-be-marked-as-spam"></a><span data-ttu-id="36e11-109">Возникает ли Нежелательная почта для входящей электронной почты с пометкой о нежелательной почте?</span><span class="sxs-lookup"><span data-stu-id="36e11-109">Does junking unauthenticated inbound email cause legitimate email to be marked as spam?</span></span>

<span data-ttu-id="36e11-110">Если Майкрософт включила эту функцию в 2018, некоторые ложные срабатывания были помечены как плохие сообщения.</span><span class="sxs-lookup"><span data-stu-id="36e11-110">When Microsoft enabled this feature in 2018, some false positives happened (good messages were marked as bad).</span></span> <span data-ttu-id="36e11-111">Однако со временем отправители корректируются согласно требованиям.</span><span class="sxs-lookup"><span data-stu-id="36e11-111">However, over time, senders adjusted to the requirements.</span></span> <span data-ttu-id="36e11-112">Количество сообщений, которые были ошибочно распознаны как поддельное, становится незначительным для большинства почтовых путей.</span><span class="sxs-lookup"><span data-stu-id="36e11-112">The number of messages that were misidentified as spoofed became negligible for most email paths.</span></span>

<span data-ttu-id="36e11-113">Microsoft сама по себе предприняла новые требования к проверке подлинности электронной почты в течение нескольких недель перед развертыванием на клиентах.</span><span class="sxs-lookup"><span data-stu-id="36e11-113">Microsoft itself first adopted the new email authentication requirements several weeks before deploying it to customers.</span></span> <span data-ttu-id="36e11-114">Хотя сначала наступали проблемы, их количество постепенно снижалось.</span><span class="sxs-lookup"><span data-stu-id="36e11-114">While there was disruption at first, it gradually declined.</span></span>

## <a name="is-spoof-intelligence-available-to-microsoft-365-customers-without-atp"></a><span data-ttu-id="36e11-115">Доступна аналитика подделки для клиентов Microsoft 365 без ATP?</span><span class="sxs-lookup"><span data-stu-id="36e11-115">Is spoof intelligence available to Microsoft 365 customers without ATP?</span></span>

<span data-ttu-id="36e11-116">Да.</span><span class="sxs-lookup"><span data-stu-id="36e11-116">Yes.</span></span> <span data-ttu-id="36e11-117">В октябре 2018 логика подделки доступна всем организациям с почтовыми ящиками в Exchange Online и автономным организациям EOP без почтовых ящиков Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="36e11-117">As of October 2018, spoof intelligence is available to all organizations with mailboxes in Exchange Online, and standalone EOP organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="36e11-118">Изначально технология защиты от спуфинга доступна только в Office 365 Advanced Threat protection.</span><span class="sxs-lookup"><span data-stu-id="36e11-118">Anti-spoofing technology was initially only available in Office 365 Advanced Threat Protection.</span></span> <span data-ttu-id="36e11-119">Например, подписки Microsoft и надстройки ATP.</span><span class="sxs-lookup"><span data-stu-id="36e11-119">For example, Microsoft E5 subscriptions or ATP add-ons.</span></span>

## <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a><span data-ttu-id="36e11-120">Как сообщить спама или фишинговых сообщений назад в корпорацию Майкрософт?</span><span class="sxs-lookup"><span data-stu-id="36e11-120">How can I report spam or non-spam messages back to Microsoft?</span></span>

<span data-ttu-id="36e11-121">См. [Передача информации о сообщениях и файлах в корпорацию Майкрософт](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="36e11-121">See [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="im-an-admin-and-i-dont-know-all-of-sources-for-messages-in-my-email-domain"></a><span data-ttu-id="36e11-122">Я администратор, и я не знаю все источники сообщений в моем домене электронной почты.</span><span class="sxs-lookup"><span data-stu-id="36e11-122">I'm an admin and I don't know all of sources for messages in my email domain!</span></span>

<span data-ttu-id="36e11-123">Сведения о [том, как вы не знаете все источники электронной почты](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email).</span><span class="sxs-lookup"><span data-stu-id="36e11-123">See [You don't know all sources for your email](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email).</span></span>

## <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization"></a><span data-ttu-id="36e11-124">Что произойдет, если отключить защиту от спуфинга для моей организации?</span><span class="sxs-lookup"><span data-stu-id="36e11-124">What happens if I disable anti-spoofing protection for my organization?</span></span>

<span data-ttu-id="36e11-125">Не рекомендуется отключать защиту от спуфинга.</span><span class="sxs-lookup"><span data-stu-id="36e11-125">We do not recommend disabling anti-spoofing protection.</span></span> <span data-ttu-id="36e11-126">Отключение защиты позволит доставить больше сообщений фишинга и нежелательной почты в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="36e11-126">Disabling the protection will allow more phishing and spam messages to be delivered in your organization.</span></span> <span data-ttu-id="36e11-127">Не все фишинги являются подложными, а не все подложные сообщения будут пропущены.</span><span class="sxs-lookup"><span data-stu-id="36e11-127">Not all phishing is spoofing, and not all spoofed messages will be missed.</span></span> <span data-ttu-id="36e11-128">Однако риск будет выше.</span><span class="sxs-lookup"><span data-stu-id="36e11-128">However, your risk will be higher.</span></span>

<span data-ttu-id="36e11-129">Теперь, когда включена [Расширенная фильтрация соединителей](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) , мы не рекомендуем отключить защиту от спуфинга при маршрутизации электронной почты через другую службу перед EOP.</span><span class="sxs-lookup"><span data-stu-id="36e11-129">Now that [Enhanced Filtering for Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) is available, we no longer recommended turning off anti-spoofing protection when your email is routed through another service before EOP.</span></span>

## <a name="does-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a><span data-ttu-id="36e11-130">Означает ли защита от подмены, будет ли защита от всех фишинга?</span><span class="sxs-lookup"><span data-stu-id="36e11-130">Does anti-spoofing protection mean I will be protected from all phishing?</span></span>

<span data-ttu-id="36e11-131">Увы, нет.</span><span class="sxs-lookup"><span data-stu-id="36e11-131">Unfortunately, no.</span></span> <span data-ttu-id="36e11-132">Злоумышленники будут адаптироваться к использованию других способов (например, скомпрометированных учетных записей или учетных записей в бесплатной почтовой службе).</span><span class="sxs-lookup"><span data-stu-id="36e11-132">Attackers will adapt to use other techniques (for example, compromised accounts or accounts in free email services).</span></span> <span data-ttu-id="36e11-133">Тем не менее, защита от фишинговых атак работает быстрее, чтобы обнаруживать эти другие типы методов фишинга.</span><span class="sxs-lookup"><span data-stu-id="36e11-133">However, anti-phishing protection works much better to detect these other types of phishing methods.</span></span> <span data-ttu-id="36e11-134">Уровни защиты в EOP предназначены для совместной работы и построения поверх других.</span><span class="sxs-lookup"><span data-stu-id="36e11-134">The protection layers in EOP are designed work together and build on top of each other.</span></span>

## <a name="do-other-large-email-services-block-unauthenticated-inbound-email"></a><span data-ttu-id="36e11-135">Блокируется и не прошедший проверку подлинности входящая электронная почта другими большими почтовыми службами?</span><span class="sxs-lookup"><span data-stu-id="36e11-135">Do other large email services block unauthenticated inbound email?</span></span>

<span data-ttu-id="36e11-136">Почти все крупные службы электронной почты реализуют традиционные проверки SPF, DKIM и DMARC.</span><span class="sxs-lookup"><span data-stu-id="36e11-136">Nearly all large email services implement traditional SPF, DKIM, and DMARC checks.</span></span> <span data-ttu-id="36e11-137">Некоторые службы обладают другими, более жесткими проверками, но не EOP, чтобы блокировать непроверенные сообщения электронной почты и обрабатывать их как поддельные сообщения.</span><span class="sxs-lookup"><span data-stu-id="36e11-137">Some services have other, more strict checks, but few go as far as EOP to block unauthenticated email and treat them as spoofed messages.</span></span> <span data-ttu-id="36e11-138">Тем не менее, отрасль становится более осведомленной о проблемах с электронной почтой, не прошедшей проверку подлинности, в частности из-за проблем с фишингом.</span><span class="sxs-lookup"><span data-stu-id="36e11-138">However, the industry is becoming more aware about issues with unauthenticated email, particularly because of the problem of phishing.</span></span>

## <a name="do-i-still-need-to-enable-the-advanced-spam-filter-setting-spf-record-hard-fail-_markasspamspfrecordhardfail_-if-i-enable-anti-spoofing"></a><span data-ttu-id="36e11-139">Нужно ли включать параметр Advanced спам Filter "запись SPF: неисправность" (_маркасспамспфрекордхардфаил_), если включена функция защиты от спуфинга?</span><span class="sxs-lookup"><span data-stu-id="36e11-139">Do I still need to enable the Advanced Spam Filter setting "SPF record: hard fail" (_MarkAsSpamSpfRecordHardFail_) if I enable anti-spoofing?</span></span>

<span data-ttu-id="36e11-140">Нет.</span><span class="sxs-lookup"><span data-stu-id="36e11-140">No.</span></span> <span data-ttu-id="36e11-141">Этот параметр ASF больше не нужен.</span><span class="sxs-lookup"><span data-stu-id="36e11-141">This ASF setting is no longer required.</span></span> <span data-ttu-id="36e11-142">Защита от подмены рассматривает как сбой SPF, так и более широкий набор критериев.</span><span class="sxs-lookup"><span data-stu-id="36e11-142">Anti-spoofing protection considers both SPF hard fails and a much wider set of criteria.</span></span> <span data-ttu-id="36e11-143">Если у вас активированы защита от спуфинга и **Запись инфраструктуры политики отправителей: серьезный сбой** (_MarkAsSpamSpfRecordHardFail_), вы, скорее всего, будете получать больше ложных срабатываний.</span><span class="sxs-lookup"><span data-stu-id="36e11-143">If you have anti-spoofing enabled and the **SPF record: hard fail** (_MarkAsSpamSpfRecordHardFail_) turned on, you will probably get more false positives.</span></span>

<span data-ttu-id="36e11-144">Мы рекомендуем отключить эту функцию, так как она не обеспечивает дополнительных преимуществ для обнаружения нежелательной почты или фишинговых сообщений, а вместо этого может создать преимущественно ложные срабатывания.</span><span class="sxs-lookup"><span data-stu-id="36e11-144">We recommend that you disable this feature as it provides almost no additional benefit for detecting spam or phishing message, and would instead generate mostly false positives.</span></span> <span data-ttu-id="36e11-145">Дополнительные сведения: Дополнительные сведения о [параметрах фильтра нежелательной почты (ASF) в EOP](advanced-spam-filtering-asf-options.md).</span><span class="sxs-lookup"><span data-stu-id="36e11-145">For more information, see [Advanced Spam Filter (ASF) settings in EOP](advanced-spam-filtering-asf-options.md).</span></span>

## <a name="does-sender-rewriting-scheme-help-fix-forwarded-email"></a><span data-ttu-id="36e11-146">Помогает ли эта схема перезаписи отправителя исправлять переадресованные сообщения?</span><span class="sxs-lookup"><span data-stu-id="36e11-146">Does Sender Rewriting Scheme help fix forwarded email?</span></span>

<span data-ttu-id="36e11-147">SRS только частично устраняет проблемы с пересланным письмом.</span><span class="sxs-lookup"><span data-stu-id="36e11-147">SRS only partially fixes the problem of forwarded email.</span></span> <span data-ttu-id="36e11-148">Переписывая SMTP- **почту from**, служба SRS может гарантировать, что перенаправляемые сообщения проходят SPF в следующем месте назначения.</span><span class="sxs-lookup"><span data-stu-id="36e11-148">By rewriting the SMTP **MAIL FROM**, SRS can ensure that the forwarded message passes SPF at the next destination.</span></span> <span data-ttu-id="36e11-149">Тем не менее, так как защита от подмены основывается на адресе **отправителя** в сочетании с **почтовым ящиком от** или DKIM-подписи (или другими сигналами), недостаточно помечать пересылаемые сообщения в службе SRS как поддельные.</span><span class="sxs-lookup"><span data-stu-id="36e11-149">However, because anti-spoofing is based upon the **From** address in combination with the **MAIL FROM** or DKIM-signing domain (or other signals), it's not enough to prevent SRS forwarded email from being marked as spoofed.</span></span>
