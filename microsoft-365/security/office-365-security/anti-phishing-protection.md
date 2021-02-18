---
title: Защита от фишинга
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 75af74b2-c7ea-4556-a912-8c48e07271d3
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
description: Администраторы могут узнать о средствах защиты от фишинга в Exchange Online Protection (EOP) и Microsoft Defender для Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4fef8aa30f2b41c0ba84a6535969b12448e80562
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289057"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a><span data-ttu-id="5c95a-103">Защита от фишинга в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5c95a-103">Anti-phishing protection in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="5c95a-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="5c95a-104">**Applies to**</span></span>
- [<span data-ttu-id="5c95a-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="5c95a-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="5c95a-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="5c95a-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="5c95a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5c95a-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="5c95a-108">*Фишинг —* это атака электронной почты, которая пытается украсть конфиденциальную информацию в сообщениях, которые кажутся надежными или надежными отправителями.</span><span class="sxs-lookup"><span data-stu-id="5c95a-108">*Phishing* is an email attack that tries to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="5c95a-109">Существуют определенные категории фишинга.</span><span class="sxs-lookup"><span data-stu-id="5c95a-109">There are specific categories of phishing.</span></span> <span data-ttu-id="5c95a-110">Например,</span><span class="sxs-lookup"><span data-stu-id="5c95a-110">For example:</span></span>

- <span data-ttu-id="5c95a-111">**При целевом** фишинге используется специализированный настраиваемый контент, специально разработанный для целевых получателей (как правило, после помеченного перенастройки получателей злоумышленником).</span><span class="sxs-lookup"><span data-stu-id="5c95a-111">**Spear phishing** uses focused, customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

- <span data-ttu-id="5c95a-112">**Whaling** is directed at executives or other high value targets within an organization for maximum effect.</span><span class="sxs-lookup"><span data-stu-id="5c95a-112">**Whaling** is directed at executives or other high value targets within an organization for maximum effect.</span></span>

- <span data-ttu-id="5c95a-113">Бизнес-компрометации электронной почты **(BEC)** использует поддельных надежных отправителей (финансовых сотрудников, клиентов, доверенных партнеров и т. д.) для обмана получателей на одобрение платежей, передачу средств или раскрытие данных клиентов.</span><span class="sxs-lookup"><span data-stu-id="5c95a-113">**Business email compromise (BEC)** uses forged trusted senders (financial officers, customers, trusted partners, etc.) to trick recipients into approving payments, transferring funds, or revealing customer data.</span></span>

- <span data-ttu-id="5c95a-114"> Программа-программа-выможатель, которая шифрует ваши данные и требует оплаты для их расшифровки, почти всегда запускается в фишинговых сообщениях.</span><span class="sxs-lookup"><span data-stu-id="5c95a-114">**Ransomware** that encrypts your data and demands payment to decrypt it almost always starts out in phishing messages.</span></span> <span data-ttu-id="5c95a-115">Защита от фишинга не может помочь в расшифровке зашифрованных файлов, но может помочь обнаружить исходные фишинговые сообщения, связанные с кампанией программы-вымогателя.</span><span class="sxs-lookup"><span data-stu-id="5c95a-115">Anti-phishing protection can't help you decrypt encrypted files, but it can help detect the initial phishing messages that are associated with the ransomware campaign.</span></span> <span data-ttu-id="5c95a-116">Дополнительные сведения о восстановлении после атаки программы-вымогателя см. в подпрограмме "Восстановление после атаки программы-вымогателя" [в Microsoft 365.](recover-from-ransomware.md)</span><span class="sxs-lookup"><span data-stu-id="5c95a-116">For more information about recovering from a ransomware attack, see [Recover from a ransomware attack in Microsoft 365](recover-from-ransomware.md).</span></span>

<span data-ttu-id="5c95a-117">С ростом сложности атак даже трудно обучить пользователей определять сложные фишинговые сообщения.</span><span class="sxs-lookup"><span data-stu-id="5c95a-117">With the growing complexity of attacks, it's even difficult for trained users to identify sophisticated phishing messages.</span></span> <span data-ttu-id="5c95a-118">К счастью, вам могут помочь Exchange Online Protection (EOP) и дополнительные функции в Microsoft Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="5c95a-118">Fortunately, Exchange Online Protection (EOP) and the additional features in Microsoft Defender for Office 365 can help.</span></span>

## <a name="anti-phishing-protection-in-eop"></a><span data-ttu-id="5c95a-119">Защита от фишинга в EOP</span><span class="sxs-lookup"><span data-stu-id="5c95a-119">Anti-phishing protection in EOP</span></span>

<span data-ttu-id="5c95a-120">EOP (то есть организации Microsoft 365 без Microsoft Defender для Office 365) содержит функции, которые помогут защитить организацию от фишинговых угроз:</span><span class="sxs-lookup"><span data-stu-id="5c95a-120">EOP (that is, Microsoft 365 organizations without Microsoft Defender for Office 365) contains features that can help protect your organization from phishing threats:</span></span>

- <span data-ttu-id="5c95a-121">**Аналитика подделки**: Просмотрите поддельные сообщения от отправителей во внутренних и внешних доменах и разрешите или заблокируйте этих отправителей.</span><span class="sxs-lookup"><span data-stu-id="5c95a-121">**Spoof intelligence**: Review spoofed messages from senders in internal and external domains, and allow or block those senders.</span></span> <span data-ttu-id="5c95a-122">Дополнительные сведения см. в сведениях [о настройке аналитики спуфинга в EOP.](learn-about-spoof-intelligence.md)</span><span class="sxs-lookup"><span data-stu-id="5c95a-122">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

- <span data-ttu-id="5c95a-123">Политики защиты от фишинга в **EOP:** включите или отключите аналитику спуфинга, включите или отключите идентификацию отправителей, неавтерификацию отправителей в Outlook, а также укажите действие для заблокированных поддельных отправителей (переместить в папку нежелательной почты или на карантин).</span><span class="sxs-lookup"><span data-stu-id="5c95a-123">**Anti-phishing policies in EOP**: Turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and specify the action for blocked spoofed senders (move to Junk Email folder or quarantine).</span></span> <span data-ttu-id="5c95a-124">Дополнительные сведения см. в подстроке "Настройка политик защиты от [фишинга" в EOP.](configure-anti-phishing-policies-eop.md)</span><span class="sxs-lookup"><span data-stu-id="5c95a-124">For more information, see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

- <span data-ttu-id="5c95a-125">Неявная проверка подлинности электронной почты: EOP улучшает стандартные проверки подлинности электронной почты для входящие сообщения электронной почты ([SPF,](set-up-spf-in-office-365-to-help-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)и [DMARC)](use-dmarc-to-validate-email.md)с репутацией отправителей, историями отправителей, историями получателей, анализом поведения и другими расширенными методиками для идентификации поддельных отправителей.</span><span class="sxs-lookup"><span data-stu-id="5c95a-125">**Implicit email authentication**: EOP enhances standard email authentication checks for inbound email ([SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md)) with sender reputation, sender history, recipient history, behavioral analysis, and other advanced techniques to help identify forged senders.</span></span> <span data-ttu-id="5c95a-126">Дополнительные сведения см. в статье [Поверка подлинности электронной почты в Microsoft 365](email-validation-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="5c95a-126">For more information, see [Email authentication in Microsoft 365](email-validation-and-authentication.md).</span></span>

## <a name="additional-anti-phishing-protection-in-microsoft-defender-for-office-365"></a><span data-ttu-id="5c95a-127">Дополнительная защита от фишинга в Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="5c95a-127">Additional anti-phishing protection in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="5c95a-128">Microsoft Defender для Office 365 содержит дополнительные и более сложные функции защиты от фишинга:</span><span class="sxs-lookup"><span data-stu-id="5c95a-128">Microsoft Defender for Office 365 contains additional and more advanced anti-phishing features:</span></span>

- <span data-ttu-id="5c95a-129">Политики защиты от фишинга в **Microsoft Defender для Office 365:** создание новых настраиваемых политик, настройка параметров защиты от фишинга (защита пользователей и доменов от обезличения), параметры аналитики почтовых ящиков и настраиваемые расширенные пороги фишинга.</span><span class="sxs-lookup"><span data-stu-id="5c95a-129">**Anti-phishing policies in Microsoft Defender for Office 365**: Create new custom policies, configure anti-impersonation settings (protect users and domains from impersonation), mailbox intelligence settings, and adjustable advanced phishing thresholds.</span></span> <span data-ttu-id="5c95a-130">Дополнительные сведения см. в подстройке "Настройка политик защиты от фишинга" в [Microsoft Defender для Office 365.](configure-atp-anti-phishing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="5c95a-130">For more information, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span> <span data-ttu-id="5c95a-131">Дополнительные сведения о различиях между политиками защиты от фишинга в EOP и политиками защиты от фишинга в Защитнике office 365 см. в политиках защиты от фишинга [в Microsoft 365.](set-up-anti-phishing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="5c95a-131">For more information about the differences between anti-phishing policies in EOP and anti-phishing policies in Defender for Office 365, see [Anti-phishing policies in Microsoft 365](set-up-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="5c95a-132">**Представления кампаний:** машинное обучение и другие действия, связанные с идентификацией и анализом сообщений, которые участвуют в скоординированных фишинговых атаках на всю службу и вашу организацию.</span><span class="sxs-lookup"><span data-stu-id="5c95a-132">**Campaign Views**: Machine learning and other heuristics identify and analyze messages that are involved in coordinated phishing attacks against the entire service and your organization.</span></span> <span data-ttu-id="5c95a-133">Дополнительные сведения [см. в представлениях кампании в Microsoft Defender для Office 365.](campaigns.md)</span><span class="sxs-lookup"><span data-stu-id="5c95a-133">For more information, see [Campaign Views in Microsoft Defender for Office 365](campaigns.md).</span></span>

- <span data-ttu-id="5c95a-134">**Имитатор** атак: администраторы могут создавать поддельные фишинговые сообщения и отправлять их внутренним пользователям в качестве средства обучения.</span><span class="sxs-lookup"><span data-stu-id="5c95a-134">**Attack simulator**: Admins can create fake phishing messages and send them to internal users as an education tool.</span></span> <span data-ttu-id="5c95a-135">Дополнительные сведения см. в [симуляторе атак в Microsoft Defender для Office 365.](attack-simulator.md)</span><span class="sxs-lookup"><span data-stu-id="5c95a-135">For more information, see [Attack Simulator in Microsoft Defender for Office 365](attack-simulator.md).</span></span>

## <a name="other-anti-phishing-resources"></a><span data-ttu-id="5c95a-136">Другие ресурсы для защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="5c95a-136">Other anti-phishing resources</span></span>

- <span data-ttu-id="5c95a-137">Для конечных пользователей: [защититесь от фишинговых](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593)схем и других форм мошенничества в Интернете.</span><span class="sxs-lookup"><span data-stu-id="5c95a-137">For end users: [Protect yourself from phishing schemes and other forms of online fraud](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593).</span></span>

- <span data-ttu-id="5c95a-138">[Как Microsoft 365 проверяет адрес "От" для предотвращения фишинга.](how-office-365-validates-the-from-address.md)</span><span class="sxs-lookup"><span data-stu-id="5c95a-138">[How Microsoft 365 validates the From address to prevent phishing](how-office-365-validates-the-from-address.md).</span></span>
