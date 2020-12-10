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
ms.service: O365-seccomp
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
description: Администраторы могут узнать о функциях защиты от фишинга в Exchange Online Protection (EOP) и защитнике Майкрософт для Office 365.
ms.openlocfilehash: 5b175a252f95c62a40348a78e694628ee58488bd
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615001"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a><span data-ttu-id="2b029-103">Защита от фишинга в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2b029-103">Anti-phishing protection in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="2b029-104">*Фишинг* — это атака с использованием электронной почты, которая пытается украсть конфиденциальные данные в сообщениях, которые не являются законными или надежными отправителями.</span><span class="sxs-lookup"><span data-stu-id="2b029-104">*Phishing* is an email attack that tries to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="2b029-105">Существуют определенные категории фишинга.</span><span class="sxs-lookup"><span data-stu-id="2b029-105">There are specific categories of phishing.</span></span> <span data-ttu-id="2b029-106">Например,</span><span class="sxs-lookup"><span data-stu-id="2b029-106">For example:</span></span>

- <span data-ttu-id="2b029-107">**Фишинг спеар** использует отсортированный Настраиваемый контент, специально предназначенный для целевых получателей (как правило, после реконнаиссанце от получателей).</span><span class="sxs-lookup"><span data-stu-id="2b029-107">**Spear phishing** uses focused, customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

- <span data-ttu-id="2b029-108">**Вхалинг** назначается руководителям или другим целям высокой стоимости в Организации для достижения максимальной силы.</span><span class="sxs-lookup"><span data-stu-id="2b029-108">**Whaling** is directed at executives or other high value targets within an organization for maximum effect.</span></span>

- <span data-ttu-id="2b029-109">**Раскрытие электронной почты (Бек)** использует подложные доверенных отправителей (финансовых лиц, клиентов, доверенных партнеров и т. д.), чтобы обманные лица могли утверждать платежи, переносить фонды или раскрывать данные клиентов.</span><span class="sxs-lookup"><span data-stu-id="2b029-109">**Business email compromise (BEC)** uses forged trusted senders (financial officers, customers, trusted partners, etc.) to trick recipients into approving payments, transferring funds, or revealing customer data.</span></span>

- <span data-ttu-id="2b029-110">Программа- **шантажистом** , которая шифрует данные и требует оплаты для их расшифровки почти всегда начинается в сообщениях фишинга.</span><span class="sxs-lookup"><span data-stu-id="2b029-110">**Ransomware** that encrypts your data and demands payment to decrypt it almost always starts out in phishing messages.</span></span> <span data-ttu-id="2b029-111">Защита от фишинга не может помочь при расшифровке зашифрованных файлов, но может помочь определить начальные фишинговые сообщения, связанные с кампанией программы-шантажистом.</span><span class="sxs-lookup"><span data-stu-id="2b029-111">Anti-phishing protection can't help you decrypt encrypted files, but it can help detect the initial phishing messages that are associated with the ransomware campaign.</span></span> <span data-ttu-id="2b029-112">Для получения дополнительных сведений об устранении атак с помощью атаки с помощью функции "атаки с помощью атаки" [в Microsoft 365](recover-from-ransomware.md).</span><span class="sxs-lookup"><span data-stu-id="2b029-112">For more information about recovering from a ransomware attack, see [Recover from a ransomware attack in Microsoft 365](recover-from-ransomware.md).</span></span>

<span data-ttu-id="2b029-113">При увеличении сложности атак она даже затрудняется для квалифицированных пользователей по определению сложных фишинговых сообщений.</span><span class="sxs-lookup"><span data-stu-id="2b029-113">With the growing complexity of attacks, it's even difficult for trained users to identify sophisticated phishing messages.</span></span> <span data-ttu-id="2b029-114">К счастью, Exchange Online Protection (EOP) и дополнительные возможности защитника Майкрософт для Office 365 могут помочь.</span><span class="sxs-lookup"><span data-stu-id="2b029-114">Fortunately, Exchange Online Protection (EOP) and the additional features in Microsoft Defender for Office 365 can help.</span></span>

## <a name="anti-phishing-protection-in-eop"></a><span data-ttu-id="2b029-115">Защита от фишинга в EOP</span><span class="sxs-lookup"><span data-stu-id="2b029-115">Anti-phishing protection in EOP</span></span>

<span data-ttu-id="2b029-116">EOP (то есть Microsoft 365 организации без защитника Майкрософт для Office 365) содержит функции, помогающие защитить организацию от фишинговых угроз.</span><span class="sxs-lookup"><span data-stu-id="2b029-116">EOP (that is, Microsoft 365 organizations without Microsoft Defender for Office 365) contains features that can help protect your organization from phishing threats:</span></span>

- <span data-ttu-id="2b029-117">**Аналитика подделки**: Просмотрите поддельные сообщения от отправителей во внутренних и внешних доменах и разрешите или заблокируйте этих отправителей.</span><span class="sxs-lookup"><span data-stu-id="2b029-117">**Spoof intelligence**: Review spoofed messages from senders in internal and external domains, and allow or block those senders.</span></span> <span data-ttu-id="2b029-118">Дополнительные сведения: [Настройка логики анализа подделки в EOP](learn-about-spoof-intelligence.md).</span><span class="sxs-lookup"><span data-stu-id="2b029-118">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

- <span data-ttu-id="2b029-119">**Политики защиты от фишинга в EOP**: Включение и выключение функции "Управление подделкой", отключение идентификации отправителей, не прошедших проверку подлинности, в Outlook, а также задание действия для заблокированных отправителей (перемещение в папку "Нежелательная почта" или "карантин").</span><span class="sxs-lookup"><span data-stu-id="2b029-119">**Anti-phishing policies in EOP**: Turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and specify the action for blocked spoofed senders (move to Junk Email folder or quarantine).</span></span> <span data-ttu-id="2b029-120">Дополнительные сведения см. [в разделе Настройка политик защиты от фишинга в EOP](configure-anti-phishing-policies-eop.md).</span><span class="sxs-lookup"><span data-stu-id="2b029-120">For more information, see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

- <span data-ttu-id="2b029-121">Неявная проверка подлинности **электронной почты**: EOP улучшает стандартные проверки подлинности электронной почты ([SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md)и [DMARC](use-dmarc-to-validate-email.md)) с помощью репутации отправителя, журнала отправителя, журнала получателей, анализа поведения и других дополнительных способов, помогающих определить подложные отправители.</span><span class="sxs-lookup"><span data-stu-id="2b029-121">**Implicit email authentication**: EOP enhances standard email authentication checks for inbound email ([SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md)) with sender reputation, sender history, recipient history, behavioral analysis, and other advanced techniques to help identify forged senders.</span></span> <span data-ttu-id="2b029-122">Дополнительные сведения см. в статье [Поверка подлинности электронной почты в Microsoft 365](email-validation-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="2b029-122">For more information, see [Email authentication in Microsoft 365](email-validation-and-authentication.md).</span></span>

## <a name="additional-anti-phishing-protection-in-microsoft-defender-for-office-365"></a><span data-ttu-id="2b029-123">Дополнительная защита от фишинга в защитнике Майкрософт для Office 365</span><span class="sxs-lookup"><span data-stu-id="2b029-123">Additional anti-phishing protection in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="2b029-124">Защитник Майкрософт для Office 365 содержит дополнительные и более совершенные функции защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="2b029-124">Microsoft Defender for Office 365 contains additional and more advanced anti-phishing features:</span></span>

- <span data-ttu-id="2b029-125">**Политики защиты от фишинга в защитнике Microsoft для Office 365**: создание новых настраиваемых политик, Настройка параметров защиты от олицетворений (защита пользователей и доменов от олицетворения), параметры аналитики почтовых ящиков и регулируемые расширенные пороговые значения фишинга.</span><span class="sxs-lookup"><span data-stu-id="2b029-125">**Anti-phishing policies in Microsoft Defender for Office 365**: Create new custom policies, configure anti-impersonation settings (protect users and domains from impersonation), mailbox intelligence settings, and adjustable advanced phishing thresholds.</span></span> <span data-ttu-id="2b029-126">Дополнительные сведения см. [в разделе Настройка политик защиты от фишинга в защитнике Майкрософт для Office 365](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="2b029-126">For more information, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span> <span data-ttu-id="2b029-127">Для получения дополнительных сведений о различиях между политиками защиты от фишинга в EOP и политиках защиты от фишинга в защитнике для Office 365, обратитесь к разделу [политики защиты от фишинга в Microsoft 365](set-up-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="2b029-127">For more information about the differences between anti-phishing policies in EOP and anti-phishing policies in Defender for Office 365, see [Anti-phishing policies in Microsoft 365](set-up-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="2b029-128">**Представления кампании**: машинное обучение и другие эвристические правила идентифицируют и анализируют сообщения, которые участвуют в согласованных атаках фишинга для всей службы и Организации.</span><span class="sxs-lookup"><span data-stu-id="2b029-128">**Campaign Views**: Machine learning and other heuristics identify and analyze messages that are involved in coordinated phishing attacks against the entire service and your organization.</span></span> <span data-ttu-id="2b029-129">Дополнительные сведения см. [в статье "представления кампании" в защитнике Майкрософт для Office 365](campaigns.md).</span><span class="sxs-lookup"><span data-stu-id="2b029-129">For more information, see [Campaign Views in Microsoft Defender for Office 365](campaigns.md).</span></span>

- <span data-ttu-id="2b029-130">**Симулятор атак**: Администраторы могут создавать фиктивные фишинговые сообщения и отправлять их внутренним пользователям как средство образования.</span><span class="sxs-lookup"><span data-stu-id="2b029-130">**Attack simulator**: Admins can create fake phishing messages and send them to internal users as an education tool.</span></span> <span data-ttu-id="2b029-131">Для получения дополнительных сведений обратитесь к [симулятору атак в защитнике Майкрософт для Office 365](attack-simulator.md).</span><span class="sxs-lookup"><span data-stu-id="2b029-131">For more information, see [Attack Simulator in Microsoft Defender for Office 365](attack-simulator.md).</span></span>

## <a name="other-anti-phishing-resources"></a><span data-ttu-id="2b029-132">Другие ресурсы защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="2b029-132">Other anti-phishing resources</span></span>

- <span data-ttu-id="2b029-133">Для конечных пользователей: [Защитите себя от фишинговых схем и других форм Интернет-мошенничества](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593).</span><span class="sxs-lookup"><span data-stu-id="2b029-133">For end users: [Protect yourself from phishing schemes and other forms of online fraud](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593).</span></span>

- <span data-ttu-id="2b029-134">[Как Microsoft 365 проверяет адрес отправителя для предотвращения фишинга](how-office-365-validates-the-from-address.md).</span><span class="sxs-lookup"><span data-stu-id="2b029-134">[How Microsoft 365 validates the From address to prevent phishing](how-office-365-validates-the-from-address.md).</span></span>
