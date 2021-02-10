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
description: Администраторы могут просматривать часто задающие вопросы и ответы о защите от спуфинга в Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2d0805b5ca9e951234679ed8b3d03b6bdfced2be
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "50175899"
---
# <a name="anti-spoofing-protection-faq"></a><span data-ttu-id="1ba54-103">Вопросы и ответы о защите от спуфинга</span><span class="sxs-lookup"><span data-stu-id="1ba54-103">Anti-spoofing protection FAQ</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="1ba54-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="1ba54-104">**Applies to**</span></span>
- [<span data-ttu-id="1ba54-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="1ba54-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="1ba54-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="1ba54-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="1ba54-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1ba54-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="1ba54-108">В этой статье данная статья содержит вопросы и ответы о защите от спуфинга для организаций Microsoft 365 с почтовыми ящиками в Exchange Online или автономных организаций Exchange Online Protection (EOP) без почтовых ящиков Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="1ba54-108">This article provides frequently asked questions and answers about anti-spoofing protection for Microsoft 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="1ba54-109">Вопросы и ответы о защите от нежелательной почты см. в ответах на вопросы о защите от нежелательной [почты.](anti-spam-protection-faq.md)</span><span class="sxs-lookup"><span data-stu-id="1ba54-109">For questions and answers about anti-spam protection, see [Anti-spam protection FAQ](anti-spam-protection-faq.md).</span></span>

<span data-ttu-id="1ba54-110">Вопросы и ответы о защите от вредоносных программ см. в вопросы и ответы по защите от [вредоносных программ](anti-malware-protection-faq-eop.md)</span><span class="sxs-lookup"><span data-stu-id="1ba54-110">For questions and answers about anti-malware protection, see [Anti-malware protection FAQ](anti-malware-protection-faq-eop.md)</span></span>

## <a name="why-did-microsoft-choose-to-junk-unauthenticated-inbound-email"></a><span data-ttu-id="1ba54-111">Почему корпорация Майкрософт выбрала входящие сообщения, не непросвещенные по электронной почте?</span><span class="sxs-lookup"><span data-stu-id="1ba54-111">Why did Microsoft choose to junk unauthenticated inbound email?</span></span>

<span data-ttu-id="1ba54-112">Корпорация Майкрософт считает, что риск продолжения поддержки неавтоматической входящие сообщения выше, чем риск потери допустимой входящие сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="1ba54-112">Microsoft believes that the risk of continuing to allow unauthenticated inbound email is higher than the risk of losing legitimate inbound email.</span></span>

## <a name="does-junking-unauthenticated-inbound-email-cause-legitimate-email-to-be-marked-as-spam"></a><span data-ttu-id="1ba54-113">Означает ли нежелачная почта, не проавентированная по электронной почте, помечаемая как нежелачная?</span><span class="sxs-lookup"><span data-stu-id="1ba54-113">Does junking unauthenticated inbound email cause legitimate email to be marked as spam?</span></span>

<span data-ttu-id="1ba54-114">Когда корпорация Майкрософт включила эту функцию в 2018 г., произошли некоторые ложные срабатываия (хорошие сообщения были помечены как плохое).</span><span class="sxs-lookup"><span data-stu-id="1ba54-114">When Microsoft enabled this feature in 2018, some false positives happened (good messages were marked as bad).</span></span> <span data-ttu-id="1ba54-115">Тем не менее, со временем отправители подстраились под требования.</span><span class="sxs-lookup"><span data-stu-id="1ba54-115">However, over time, senders adjusted to the requirements.</span></span> <span data-ttu-id="1ba54-116">Количество сообщений, ошибочно охаченных как поддельные, стало незначительным для большинства путей электронной почты.</span><span class="sxs-lookup"><span data-stu-id="1ba54-116">The number of messages that were misidentified as spoofed became negligible for most email paths.</span></span>

<span data-ttu-id="1ba54-117">Корпорация Майкрософт сначала приняла новые требования к проверке подлинности электронной почты за несколько недель до ее развертывания для клиентов.</span><span class="sxs-lookup"><span data-stu-id="1ba54-117">Microsoft itself first adopted the new email authentication requirements several weeks before deploying it to customers.</span></span> <span data-ttu-id="1ba54-118">Хотя сначала наступали проблемы, их количество постепенно снижалось.</span><span class="sxs-lookup"><span data-stu-id="1ba54-118">While there was disruption at first, it gradually declined.</span></span>

## <a name="is-spoof-intelligence-available-to-microsoft-365-customers-without-defender-for-office-365"></a><span data-ttu-id="1ba54-119">Доступна ли аналитика спуфинга пользователям Microsoft 365 без Защитника для Office 365?</span><span class="sxs-lookup"><span data-stu-id="1ba54-119">Is spoof intelligence available to Microsoft 365 customers without Defender for Office 365?</span></span>

<span data-ttu-id="1ba54-120">Да.</span><span class="sxs-lookup"><span data-stu-id="1ba54-120">Yes.</span></span> <span data-ttu-id="1ba54-121">С октября 2018 г. аналитика спуфинга доступна всем организациям с почтовыми ящиками в Exchange Online и автономным организациям EOP без почтовых ящиков Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="1ba54-121">As of October 2018, spoof intelligence is available to all organizations with mailboxes in Exchange Online, and standalone EOP organizations without Exchange Online mailboxes.</span></span>

## <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a><span data-ttu-id="1ba54-122">Как сообщить спама или фишинговых сообщений назад в корпорацию Майкрософт?</span><span class="sxs-lookup"><span data-stu-id="1ba54-122">How can I report spam or non-spam messages back to Microsoft?</span></span>

<span data-ttu-id="1ba54-123">См. [Передача информации о сообщениях и файлах в корпорацию Майкрософт](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="1ba54-123">See [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="im-an-admin-and-i-dont-know-all-of-sources-for-messages-in-my-email-domain"></a><span data-ttu-id="1ba54-124">Я администратор и не знаю все источники сообщений в моем домене электронной почты!</span><span class="sxs-lookup"><span data-stu-id="1ba54-124">I'm an admin and I don't know all of sources for messages in my email domain!</span></span>

<span data-ttu-id="1ba54-125">См. ["Вы не знаете все источники для своей электронной почты".](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email)</span><span class="sxs-lookup"><span data-stu-id="1ba54-125">See [You don't know all sources for your email](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email).</span></span>

## <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization"></a><span data-ttu-id="1ba54-126">Что произойдет, если отключить защиту от спуфинга в моей организации?</span><span class="sxs-lookup"><span data-stu-id="1ba54-126">What happens if I disable anti-spoofing protection for my organization?</span></span>

<span data-ttu-id="1ba54-127">Не рекомендуется отключать защиту от спуфинга.</span><span class="sxs-lookup"><span data-stu-id="1ba54-127">We do not recommend disabling anti-spoofing protection.</span></span> <span data-ttu-id="1ba54-128">Отключение защиты позволит доставить больше фишинговых и нежелательных сообщений в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="1ba54-128">Disabling the protection will allow more phishing and spam messages to be delivered in your organization.</span></span> <span data-ttu-id="1ba54-129">Не все фишинговые сообщения являются спуфингом, и не все поддельные сообщения будут пропущены.</span><span class="sxs-lookup"><span data-stu-id="1ba54-129">Not all phishing is spoofing, and not all spoofed messages will be missed.</span></span> <span data-ttu-id="1ba54-130">Однако риск будет выше.</span><span class="sxs-lookup"><span data-stu-id="1ba54-130">However, your risk will be higher.</span></span>

<span data-ttu-id="1ba54-131">Теперь, [когда доступна](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) расширенная фильтрация для соединителю, мы больше не рекомендуем отключать защиту от спуфинга, если ваша электронная почта маршрутит через другую службу перед EOP.</span><span class="sxs-lookup"><span data-stu-id="1ba54-131">Now that [Enhanced Filtering for Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) is available, we no longer recommended turning off anti-spoofing protection when your email is routed through another service before EOP.</span></span>

## <a name="does-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a><span data-ttu-id="1ba54-132">Означает ли защита от спуфинга защиту от всех фишинговых сообщений?</span><span class="sxs-lookup"><span data-stu-id="1ba54-132">Does anti-spoofing protection mean I will be protected from all phishing?</span></span>

<span data-ttu-id="1ba54-133">К сожалению, нет.</span><span class="sxs-lookup"><span data-stu-id="1ba54-133">Unfortunately, no.</span></span> <span data-ttu-id="1ba54-134">Злоумышленники адаптируются к использованию других методов (например, компрометации учетных записей или учетных записей в бесплатных службах электронной почты).</span><span class="sxs-lookup"><span data-stu-id="1ba54-134">Attackers will adapt to use other techniques (for example, compromised accounts or accounts in free email services).</span></span> <span data-ttu-id="1ba54-135">Однако защита от фишинга намного лучше работает для обнаружения других типов фишинговых методов.</span><span class="sxs-lookup"><span data-stu-id="1ba54-135">However, anti-phishing protection works much better to detect these other types of phishing methods.</span></span> <span data-ttu-id="1ba54-136">Уровни защиты в EOP разработаны совместно и работают друг над другом.</span><span class="sxs-lookup"><span data-stu-id="1ba54-136">The protection layers in EOP are designed work together and build on top of each other.</span></span>

## <a name="do-other-large-email-services-block-unauthenticated-inbound-email"></a><span data-ttu-id="1ba54-137">Блокируют ли другие крупные службы электронной почты входящие сообщения, не непросвещенные?</span><span class="sxs-lookup"><span data-stu-id="1ba54-137">Do other large email services block unauthenticated inbound email?</span></span>

<span data-ttu-id="1ba54-138">Почти во всех крупных почтовых службах реализованы традиционные проверки SPF, DKIM и DMARC.</span><span class="sxs-lookup"><span data-stu-id="1ba54-138">Nearly all large email services implement traditional SPF, DKIM, and DMARC checks.</span></span> <span data-ttu-id="1ba54-139">Некоторые службы имеют другие, более строгие проверки, но лишь некоторые из них не дойдут до EOP, чтобы заблокировать непроверяемую электронную почту и рассматривать их как поддельные сообщения.</span><span class="sxs-lookup"><span data-stu-id="1ba54-139">Some services have other, more strict checks, but few go as far as EOP to block unauthenticated email and treat them as spoofed messages.</span></span> <span data-ttu-id="1ba54-140">Однако в отрасли все больше известно о проблемах с электронной почтой, неавтериированной, особенно из-за фишинга.</span><span class="sxs-lookup"><span data-stu-id="1ba54-140">However, the industry is becoming more aware about issues with unauthenticated email, particularly because of the problem of phishing.</span></span>

## <a name="do-i-still-need-to-enable-the-advanced-spam-filter-setting-spf-record-hard-fail-_markasspamspfrecordhardfail_-if-i-enable-anti-spoofing"></a><span data-ttu-id="1ba54-141">Нужно ли по-прежнему включить параметр Advanced Spam Filter "Запись SPF: жесткий сбой" (_MarkAsSpamSpfRecordHardFail),_ если я влюлю анти спуфинг?</span><span class="sxs-lookup"><span data-stu-id="1ba54-141">Do I still need to enable the Advanced Spam Filter setting "SPF record: hard fail" (_MarkAsSpamSpfRecordHardFail_) if I enable anti-spoofing?</span></span>

<span data-ttu-id="1ba54-142">Нет.</span><span class="sxs-lookup"><span data-stu-id="1ba54-142">No.</span></span> <span data-ttu-id="1ba54-143">Этот параметр ASF больше не требуется.</span><span class="sxs-lookup"><span data-stu-id="1ba54-143">This ASF setting is no longer required.</span></span> <span data-ttu-id="1ba54-144">Защита от спуфинга рассматривает как жесткий сбой SPF, так и гораздо более широкий набор критериев.</span><span class="sxs-lookup"><span data-stu-id="1ba54-144">Anti-spoofing protection considers both SPF hard fails and a much wider set of criteria.</span></span> <span data-ttu-id="1ba54-145">Если у вас активированы защита от спуфинга и **Запись инфраструктуры политики отправителей: серьезный сбой** (_MarkAsSpamSpfRecordHardFail_), вы, скорее всего, будете получать больше ложных срабатываний.</span><span class="sxs-lookup"><span data-stu-id="1ba54-145">If you have anti-spoofing enabled and the **SPF record: hard fail** (_MarkAsSpamSpfRecordHardFail_) turned on, you will probably get more false positives.</span></span>

<span data-ttu-id="1ba54-146">Мы рекомендуем отключить эту функцию, так как она практически не дает дополнительных преимуществ для обнаружения спама или фишинговых сообщений, а вместо этого будет генерировать в основном ложные срабатывания.</span><span class="sxs-lookup"><span data-stu-id="1ba54-146">We recommend that you disable this feature as it provides almost no additional benefit for detecting spam or phishing message, and would instead generate mostly false positives.</span></span> <span data-ttu-id="1ba54-147">Дополнительные сведения см. в [параметрах advanced Spam Filter (ASF) в EOP.](advanced-spam-filtering-asf-options.md)</span><span class="sxs-lookup"><span data-stu-id="1ba54-147">For more information, see [Advanced Spam Filter (ASF) settings in EOP](advanced-spam-filtering-asf-options.md).</span></span>

## <a name="does-sender-rewriting-scheme-help-fix-forwarded-email"></a><span data-ttu-id="1ba54-148">Помогает ли схема переописи отправитель исправлений перенаправляемой электронной почты?</span><span class="sxs-lookup"><span data-stu-id="1ba54-148">Does Sender Rewriting Scheme help fix forwarded email?</span></span>

<span data-ttu-id="1ba54-149">SRS только частично устраняет проблемы с пересланным письмом.</span><span class="sxs-lookup"><span data-stu-id="1ba54-149">SRS only partially fixes the problem of forwarded email.</span></span> <span data-ttu-id="1ba54-150">Переописав SMTP **MAIL FROM,** SRS гарантирует, что пересылаемая почта пройдет SPF в следующем месте назначения.</span><span class="sxs-lookup"><span data-stu-id="1ba54-150">By rewriting the SMTP **MAIL FROM**, SRS can ensure that the forwarded message passes SPF at the next destination.</span></span> <span data-ttu-id="1ba54-151">Тем не менее, так как в  основе антишуфинга лежит адрес "От" в сочетании с доменом **MAIL FROM** или DKIM-подписью (или другими сигналами), недостаточно предотвратить пометку электронной почты, пересылаемой SRS, как подмену.</span><span class="sxs-lookup"><span data-stu-id="1ba54-151">However, because anti-spoofing is based upon the **From** address in combination with the **MAIL FROM** or DKIM-signing domain (or other signals), it's not enough to prevent SRS forwarded email from being marked as spoofed.</span></span>
