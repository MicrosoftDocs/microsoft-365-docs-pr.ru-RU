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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Администраторы могут просматривать часто задамые вопросы и ответы о защите от спуфинга в Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a5843ee7f791fbc2c37914194b153fdd05866d0a
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204958"
---
# <a name="anti-spoofing-protection-faq"></a><span data-ttu-id="998ed-103">Вопросы и ответы о защите от спуфинга</span><span class="sxs-lookup"><span data-stu-id="998ed-103">Anti-spoofing protection FAQ</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="998ed-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="998ed-104">**Applies to**</span></span>
- [<span data-ttu-id="998ed-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="998ed-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="998ed-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="998ed-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="998ed-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="998ed-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="998ed-108">В этой статье часто задаются вопросы и ответы о защите от спуфинга для организаций Microsoft 365 с почтовыми ящиками в Exchange Online или автономных организаций Exchange Online Protection (EOP) без почтовых ящиков Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="998ed-108">This article provides frequently asked questions and answers about anti-spoofing protection for Microsoft 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="998ed-109">Вопросы и ответы о защите от нежелательной почты см. в [faq anti-spam protection.](anti-spam-protection-faq.md)</span><span class="sxs-lookup"><span data-stu-id="998ed-109">For questions and answers about anti-spam protection, see [Anti-spam protection FAQ](anti-spam-protection-faq.md).</span></span>

<span data-ttu-id="998ed-110">Вопросы и ответы о защите от вредоносных программ см. в faq [anti-malware protection](anti-malware-protection-faq-eop.md)</span><span class="sxs-lookup"><span data-stu-id="998ed-110">For questions and answers about anti-malware protection, see [Anti-malware protection FAQ](anti-malware-protection-faq-eop.md)</span></span>

## <a name="why-did-microsoft-choose-to-junk-unauthenticated-inbound-email"></a><span data-ttu-id="998ed-111">Почему Корпорация Майкрософт выбрала нежелательной неавентированной входящие сообщения электронной почты?</span><span class="sxs-lookup"><span data-stu-id="998ed-111">Why did Microsoft choose to junk unauthenticated inbound email?</span></span>

<span data-ttu-id="998ed-112">Корпорация Майкрософт считает, что риск продолжения допуска недостоверной входящий электронной почты выше, чем риск потери законной входящие сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="998ed-112">Microsoft believes that the risk of continuing to allow unauthenticated inbound email is higher than the risk of losing legitimate inbound email.</span></span>

## <a name="does-junking-unauthenticated-inbound-email-cause-legitimate-email-to-be-marked-as-spam"></a><span data-ttu-id="998ed-113">Вызывает ли нежелательное почта неавентированное входящие сообщения нежелательной почты как нежелательной почты?</span><span class="sxs-lookup"><span data-stu-id="998ed-113">Does junking unauthenticated inbound email cause legitimate email to be marked as spam?</span></span>

<span data-ttu-id="998ed-114">Когда Microsoft включила эту функцию в 2018 г., произошли некоторые ложные срабатыва(хорошие сообщения были отмечены как плохие).</span><span class="sxs-lookup"><span data-stu-id="998ed-114">When Microsoft enabled this feature in 2018, some false positives happened (good messages were marked as bad).</span></span> <span data-ttu-id="998ed-115">Однако со временем отправители адаптировались к требованиям.</span><span class="sxs-lookup"><span data-stu-id="998ed-115">However, over time, senders adjusted to the requirements.</span></span> <span data-ttu-id="998ed-116">Количество сообщений, ошибочно заверенных в качестве поддельных, стало незначительным для большинства путей электронной почты.</span><span class="sxs-lookup"><span data-stu-id="998ed-116">The number of messages that were misidentified as spoofed became negligible for most email paths.</span></span>

<span data-ttu-id="998ed-117">Корпорация Майкрософт впервые приняла новые требования к проверке подлинности электронной почты за несколько недель до ее развертывания для клиентов.</span><span class="sxs-lookup"><span data-stu-id="998ed-117">Microsoft itself first adopted the new email authentication requirements several weeks before deploying it to customers.</span></span> <span data-ttu-id="998ed-118">Хотя сначала наступали проблемы, их количество постепенно снижалось.</span><span class="sxs-lookup"><span data-stu-id="998ed-118">While there was disruption at first, it gradually declined.</span></span>

## <a name="is-spoof-intelligence-available-to-microsoft-365-customers-without-defender-for-office-365"></a><span data-ttu-id="998ed-119">Доступна ли подмена сведений клиентам Microsoft 365 без Defender для Office 365?</span><span class="sxs-lookup"><span data-stu-id="998ed-119">Is spoof intelligence available to Microsoft 365 customers without Defender for Office 365?</span></span>

<span data-ttu-id="998ed-120">Да.</span><span class="sxs-lookup"><span data-stu-id="998ed-120">Yes.</span></span> <span data-ttu-id="998ed-121">С октября 2018 г. сведения о подмене доступны всем организациям с почтовыми ящиками в Exchange Online и автономными организациями EOP без почтовых ящиков Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="998ed-121">As of October 2018, spoof intelligence is available to all organizations with mailboxes in Exchange Online, and standalone EOP organizations without Exchange Online mailboxes.</span></span>

## <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a><span data-ttu-id="998ed-122">Как сообщить спама или фишинговых сообщений назад в корпорацию Майкрософт?</span><span class="sxs-lookup"><span data-stu-id="998ed-122">How can I report spam or non-spam messages back to Microsoft?</span></span>

<span data-ttu-id="998ed-123">См. [Передача информации о сообщениях и файлах в корпорацию Майкрософт](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="998ed-123">See [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="im-an-admin-and-i-dont-know-all-of-sources-for-messages-in-my-email-domain"></a><span data-ttu-id="998ed-124">Я администратор и не знаю всех источников сообщений в моем домене электронной почты!</span><span class="sxs-lookup"><span data-stu-id="998ed-124">I'm an admin and I don't know all of sources for messages in my email domain!</span></span>

<span data-ttu-id="998ed-125">См. [не все источники электронной почты.](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email)</span><span class="sxs-lookup"><span data-stu-id="998ed-125">See [You don't know all sources for your email](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email).</span></span>

## <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization"></a><span data-ttu-id="998ed-126">Что произойдет, если я отключу защиту от подмены для организации?</span><span class="sxs-lookup"><span data-stu-id="998ed-126">What happens if I disable anti-spoofing protection for my organization?</span></span>

<span data-ttu-id="998ed-127">Мы не рекомендуем отключить защиту от спуфинга.</span><span class="sxs-lookup"><span data-stu-id="998ed-127">We do not recommend disabling anti-spoofing protection.</span></span> <span data-ttu-id="998ed-128">Отключение защиты позволит доставить больше фишинговых и спам-сообщений в организации.</span><span class="sxs-lookup"><span data-stu-id="998ed-128">Disabling the protection will allow more phishing and spam messages to be delivered in your organization.</span></span> <span data-ttu-id="998ed-129">Не все фишинговые сообщения являются подменой, и не все поддельные сообщения будут пропущены.</span><span class="sxs-lookup"><span data-stu-id="998ed-129">Not all phishing is spoofing, and not all spoofed messages will be missed.</span></span> <span data-ttu-id="998ed-130">Однако риск будет выше.</span><span class="sxs-lookup"><span data-stu-id="998ed-130">However, your risk will be higher.</span></span>

<span data-ttu-id="998ed-131">Теперь, [когда](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) расширенная фильтрация для соединители доступна, мы больше не рекомендуем отключать защиту от подмены, когда ваша электронная почта передается через другую службу перед EOP.</span><span class="sxs-lookup"><span data-stu-id="998ed-131">Now that [Enhanced Filtering for Connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) is available, we no longer recommended turning off anti-spoofing protection when your email is routed through another service before EOP.</span></span>

## <a name="does-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a><span data-ttu-id="998ed-132">Означает ли защита от подмены, что я буду защищен от всех фишинговых атак?</span><span class="sxs-lookup"><span data-stu-id="998ed-132">Does anti-spoofing protection mean I will be protected from all phishing?</span></span>

<span data-ttu-id="998ed-133">К сожалению, нет.</span><span class="sxs-lookup"><span data-stu-id="998ed-133">Unfortunately, no.</span></span> <span data-ttu-id="998ed-134">Злоумышленники будут адаптироваться к использованию других методов (например, скомпрометированная учетная запись или учетные записи в бесплатных службах электронной почты).</span><span class="sxs-lookup"><span data-stu-id="998ed-134">Attackers will adapt to use other techniques (for example, compromised accounts or accounts in free email services).</span></span> <span data-ttu-id="998ed-135">Однако защита от фишинга гораздо лучше работает для обнаружения этих других типов методов фишинга.</span><span class="sxs-lookup"><span data-stu-id="998ed-135">However, anti-phishing protection works much better to detect these other types of phishing methods.</span></span> <span data-ttu-id="998ed-136">Уровни защиты в EOP разработаны совместно и строятся друг на друге.</span><span class="sxs-lookup"><span data-stu-id="998ed-136">The protection layers in EOP are designed work together and build on top of each other.</span></span>

## <a name="do-other-large-email-services-block-unauthenticated-inbound-email"></a><span data-ttu-id="998ed-137">Блокируют ли другие крупные службы электронной почты недоверимую входящие сообщения?</span><span class="sxs-lookup"><span data-stu-id="998ed-137">Do other large email services block unauthenticated inbound email?</span></span>

<span data-ttu-id="998ed-138">Почти все крупные службы электронной почты реализуют традиционные проверки SPF, DKIM и DMARC.</span><span class="sxs-lookup"><span data-stu-id="998ed-138">Nearly all large email services implement traditional SPF, DKIM, and DMARC checks.</span></span> <span data-ttu-id="998ed-139">Некоторые службы имеют другие, более строгие проверки, но лишь немногие идут до EOP, чтобы заблокировать неавентированную электронную почту и относиться к ним как к поддельным сообщениям.</span><span class="sxs-lookup"><span data-stu-id="998ed-139">Some services have other, more strict checks, but few go as far as EOP to block unauthenticated email and treat them as spoofed messages.</span></span> <span data-ttu-id="998ed-140">Однако отрасль становится все более осведомленной о проблемах с недостоверной электронной почтой, особенно из-за проблемы фишинга.</span><span class="sxs-lookup"><span data-stu-id="998ed-140">However, the industry is becoming more aware about issues with unauthenticated email, particularly because of the problem of phishing.</span></span>

## <a name="do-i-still-need-to-enable-the-advanced-spam-filter-setting-spf-record-hard-fail-_markasspamspfrecordhardfail_-if-i-enable-anti-spoofing"></a><span data-ttu-id="998ed-141">Необходимо ли включить параметр Advanced Spam Filter "SPF record: hard fail"_(MarkAsSpamSpfRecordHardFail),_ если я встану для борьбы с подменой?</span><span class="sxs-lookup"><span data-stu-id="998ed-141">Do I still need to enable the Advanced Spam Filter setting "SPF record: hard fail" (_MarkAsSpamSpfRecordHardFail_) if I enable anti-spoofing?</span></span>

<span data-ttu-id="998ed-142">Нет.</span><span class="sxs-lookup"><span data-stu-id="998ed-142">No.</span></span> <span data-ttu-id="998ed-143">Этот параметр ASF больше не требуется.</span><span class="sxs-lookup"><span data-stu-id="998ed-143">This ASF setting is no longer required.</span></span> <span data-ttu-id="998ed-144">Защита от спуфинга рассматривает как жесткий SPF- сбой, так и гораздо более широкий набор критериев.</span><span class="sxs-lookup"><span data-stu-id="998ed-144">Anti-spoofing protection considers both SPF hard fails and a much wider set of criteria.</span></span> <span data-ttu-id="998ed-145">Если у вас активированы защита от спуфинга и **Запись инфраструктуры политики отправителей: серьезный сбой** (_MarkAsSpamSpfRecordHardFail_), вы, скорее всего, будете получать больше ложных срабатываний.</span><span class="sxs-lookup"><span data-stu-id="998ed-145">If you have anti-spoofing enabled and the **SPF record: hard fail** (_MarkAsSpamSpfRecordHardFail_) turned on, you will probably get more false positives.</span></span>

<span data-ttu-id="998ed-146">Мы рекомендуем отключить эту функцию, так как она практически не предоставляет дополнительных преимуществ для обнаружения нежелательной почты или фишинга, а вместо этого создает в основном ложные срабатывания.</span><span class="sxs-lookup"><span data-stu-id="998ed-146">We recommend that you disable this feature as it provides almost no additional benefit for detecting spam or phishing message, and would instead generate mostly false positives.</span></span> <span data-ttu-id="998ed-147">Дополнительные сведения см. в дополнительных настройках фильтра нежелательной почты [(ASF) в EOP.](advanced-spam-filtering-asf-options.md)</span><span class="sxs-lookup"><span data-stu-id="998ed-147">For more information, see [Advanced Spam Filter (ASF) settings in EOP](advanced-spam-filtering-asf-options.md).</span></span>

## <a name="does-sender-rewriting-scheme-help-fix-forwarded-email"></a><span data-ttu-id="998ed-148">Помогает ли схема переописывающего отправщика исправить отправленную электронную почту?</span><span class="sxs-lookup"><span data-stu-id="998ed-148">Does Sender Rewriting Scheme help fix forwarded email?</span></span>

<span data-ttu-id="998ed-149">SRS только частично устраняет проблемы с пересланным письмом.</span><span class="sxs-lookup"><span data-stu-id="998ed-149">SRS only partially fixes the problem of forwarded email.</span></span> <span data-ttu-id="998ed-150">Переписав SMTP **MAIL FROM,** SRS может убедиться, что отправленное сообщение передает SPF в следующем пункте назначения.</span><span class="sxs-lookup"><span data-stu-id="998ed-150">By rewriting the SMTP **MAIL FROM**, SRS can ensure that the forwarded message passes SPF at the next destination.</span></span> <span data-ttu-id="998ed-151">Однако, так как анти-спуфинг основан на адресе **From** в сочетании с доменом **MAIL FROM** или DKIM-подписанием (или другими сигналами), этого недостаточно, чтобы не допустить, чтобы отправленная SRS электронная почта была помечена как поддельный.</span><span class="sxs-lookup"><span data-stu-id="998ed-151">However, because anti-spoofing is based upon the **From** address in combination with the **MAIL FROM** or DKIM-signing domain (or other signals), it's not enough to prevent SRS forwarded email from being marked as spoofed.</span></span>