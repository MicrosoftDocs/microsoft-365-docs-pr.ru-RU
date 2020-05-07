---
title: Защита от фишинга в Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 75af74b2-c7ea-4556-a912-8c48e07271d3
ms.collection:
- M365-security-compliance
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
description: В этой статье описываются доступные интерактивные ресурсы, которые можно использовать для изучения и реализации параметров и стратегий защиты от фишинга в Microsoft 365.
ms.openlocfilehash: 09d384376b1e44989987c40ef3c7860e4fac6167
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033766"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a><span data-ttu-id="ed37e-103">Защита от фишинга в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ed37e-103">Anti-phishing protection in Microsoft 365</span></span>

<span data-ttu-id="ed37e-104">*Фишинг* для атаки электронной почты, которая пытается украсть конфиденциальные данные в сообщениях, которые не являются законными или надежными отправителями.</span><span class="sxs-lookup"><span data-stu-id="ed37e-104">*Phishing* an email attack that tries to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="ed37e-105">Существуют определенные категории фишинга.</span><span class="sxs-lookup"><span data-stu-id="ed37e-105">There are specific categories of phishing.</span></span> <span data-ttu-id="ed37e-106">Пример:</span><span class="sxs-lookup"><span data-stu-id="ed37e-106">For example:</span></span>

- <span data-ttu-id="ed37e-107">**Фишинг спеар** использует очень специализированный и настроенный контент, специально предназначенный для целевых получателей (как правило, после реконнаиссанце от получателей).</span><span class="sxs-lookup"><span data-stu-id="ed37e-107">**Spear phishing** uses very focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

- <span data-ttu-id="ed37e-108">**Вхалинг** назначается руководителям или другим целям высокой стоимости в Организации для достижения максимальной силы.</span><span class="sxs-lookup"><span data-stu-id="ed37e-108">**Whaling** is directed at executives or other high value targets within an organization for maximum effect.</span></span>

- <span data-ttu-id="ed37e-109">**Раскрытие электронной почты (Бек)** использует подложные доверенных отправителей (финансовых подразделений, клиентов, доверенных партнеров и т. д.), чтобы заставить получателя утверждать платежи, переносить фонды или раскрывать данные клиента.</span><span class="sxs-lookup"><span data-stu-id="ed37e-109">**Business email compromise (BEC)** uses forged trusted senders (financial officers, customers, trusted partners, etc.) in an effort to trick the recipient into approving payments, transferring funds, or disclosing customer data.</span></span>

- <span data-ttu-id="ed37e-110">Программа- **шантажистом** , которая шифрует данные и требует оплаты для их расшифровки почти всегда начинается в сообщениях фишинга.</span><span class="sxs-lookup"><span data-stu-id="ed37e-110">**Ransomware** that encrypts your data and demands payment to decrypt it almost always starts out in phishing messages.</span></span> <span data-ttu-id="ed37e-111">Защита от фишинга не может помочь при расшифровке зашифрованных файлов, но может помочь определить начальные фишинговые сообщения, связанные с кампанией программы-шантажистом.</span><span class="sxs-lookup"><span data-stu-id="ed37e-111">Anti-phishing protection can't help you decrypt encrypted files, but it can help detect the initial phishing messages that are associated with the ransomware campaign.</span></span> <span data-ttu-id="ed37e-112">Для получения дополнительных сведений об устранении атак с помощью атаки с помощью функции "атаки с помощью атаки" [в Microsoft 365](recover-from-ransomware.md).</span><span class="sxs-lookup"><span data-stu-id="ed37e-112">For more information about recovering from a ransomware attack, see [Recover from a ransomware attack in Microsoft 365](recover-from-ransomware.md).</span></span>

<span data-ttu-id="ed37e-113">При увеличении сложности атак она даже затрудняется для квалифицированных пользователей по определению сложных фишинговых сообщений.</span><span class="sxs-lookup"><span data-stu-id="ed37e-113">With the growing complexity of attacks, it's even difficult for trained users to identify sophisticated phishing messages.</span></span> <span data-ttu-id="ed37e-114">К счастью, Exchange Online Protection (EOP) и дополнительные функции Microsoft 365 Advanced Threat protection (ATP) могут помочь.</span><span class="sxs-lookup"><span data-stu-id="ed37e-114">Fortunately, Exchange Online Protection (EOP) and the additional features in Microsoft 365 Advanced Threat Protection (ATP) can help.</span></span>

## <a name="anti-phishing-protection-in-eop"></a><span data-ttu-id="ed37e-115">Защита от фишинга в EOP</span><span class="sxs-lookup"><span data-stu-id="ed37e-115">Anti-phishing protection in EOP</span></span>

<span data-ttu-id="ed37e-116">EOP (то есть Microsoft 365 организации без ATP) содержит функции, которые могут помочь защитить организацию от фишинговых угроз.</span><span class="sxs-lookup"><span data-stu-id="ed37e-116">EOP (that is, Microsoft 365 organizations without ATP) contains features that can help protect your organization from phishing threats:</span></span>

- <span data-ttu-id="ed37e-117">**Аналитика подделки**: Просмотрите поддельные сообщения от отправителей во внутренних и внешних доменах и разрешите или заблокируйте этих отправителей.</span><span class="sxs-lookup"><span data-stu-id="ed37e-117">**Spoof intelligence**: Review spoofed messages from senders in internal and external domains, and allow or block those senders.</span></span> <span data-ttu-id="ed37e-118">Дополнительные сведения см. в статье [Настройка аналитики спуфинга в Microsoft 365](learn-about-spoof-intelligence.md).</span><span class="sxs-lookup"><span data-stu-id="ed37e-118">For more information, see [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).</span></span>

- <span data-ttu-id="ed37e-119">**Политики защиты от фишинга в EOP**: Включение и выключение функции "Управление подделкой", отключение идентификации отправителей, не прошедших проверку подлинности, в Outlook, а также задание действия для заблокированных отправителей (перемещение в папку "Нежелательная почта" или "карантин").</span><span class="sxs-lookup"><span data-stu-id="ed37e-119">**Anti-phishing policies in EOP**: Turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and specify the action for blocked spoofed senders (move to Junk Email folder or quarantine).</span></span> <span data-ttu-id="ed37e-120">Дополнительные сведения см. [в разделе Настройка политик защиты от фишинга в EOP](configure-anti-phishing-policies-eop.md).</span><span class="sxs-lookup"><span data-stu-id="ed37e-120">For more information, see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

- <span data-ttu-id="ed37e-121">Неявная проверка подлинности **электронной почты**: EOP улучшает стандартные проверки подлинности электронной почты ([SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md)и [DMARC](use-dmarc-to-validate-email.md)) с помощью репутации отправителя, журнала отправителя, журнала получателей, анализа поведения и других дополнительных способов, помогающих определить подложные отправители.</span><span class="sxs-lookup"><span data-stu-id="ed37e-121">**Implicit email authentication**: EOP enhances standard email authentication checks for inbound email ([SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md)) with sender reputation, sender history, recipient history, behavioral analysis, and other advanced techniques to help identify forged senders.</span></span> <span data-ttu-id="ed37e-122">Дополнительные сведения см. в статье [Поверка подлинности электронной почты в Microsoft 365](email-validation-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="ed37e-122">For more information, see [Email authentication in Microsoft 365](email-validation-and-authentication.md).</span></span>

## <a name="additional-anti-phishing-protection-in-office-365-atp"></a><span data-ttu-id="ed37e-123">Дополнительная защита от фишинга в Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="ed37e-123">Additional anti-phishing protection in Office 365 ATP</span></span>

<span data-ttu-id="ed37e-124">Office 365 ATP содержит дополнительные и более совершенные функции защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="ed37e-124">Office 365 ATP contains additional and more advanced anti-phishing features:</span></span>

- <span data-ttu-id="ed37e-125">**Политики защиты от фишинга ATP**: создание новых настраиваемых политик, Настройка параметров защиты от олицетворения (защита пользователей и доменов от олицетворений), параметры аналитики почтовых ящиков и регулируемые расширенные пороговые значения фишинга.</span><span class="sxs-lookup"><span data-stu-id="ed37e-125">**ATP anti-phishing policies**: Create new custom policies, configure anti-impersonation settings (protect users and domains from impersonation), mailbox intelligence settings, and adjustable advanced phishing thresholds.</span></span> <span data-ttu-id="ed37e-126">Для получения дополнительных сведений см. [Настройка политик защиты от фишинга ATP в Microsoft 365](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="ed37e-126">For more information, see [Configure ATP anti-phishing policies in Microsoft 365](configure-atp-anti-phishing-policies.md).</span></span> <span data-ttu-id="ed37e-127">Дополнительные сведения о различиях между политиками защиты от фишинга и политиками защиты от фишинга ATP приведены [в статье политики защиты от фишинга в Microsoft 365](set-up-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="ed37e-127">For more information about the differences between anti-phishing policies and ATP anti-phishing policies, see [Anti-phishing policies in Microsoft 365](set-up-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="ed37e-128">**Представления кампании**: машинное обучение и другие эвристические правила идентифицируют и анализируют сообщения, которые участвуют в согласованных атаках фишинга для всей службы и Организации.</span><span class="sxs-lookup"><span data-stu-id="ed37e-128">**Campaign Views**: Machine learning and other heuristics identify and analyze messages that are involved in coordinated phishing attacks against the entire service and your organization.</span></span> <span data-ttu-id="ed37e-129">Дополнительные сведения см в статье [представления кампании в Office 365 ATP](campaigns.md).</span><span class="sxs-lookup"><span data-stu-id="ed37e-129">For more information, see [Campaign Views in Office 365 ATP](campaigns.md).</span></span>

- <span data-ttu-id="ed37e-130">**Симулятор атак**: Администраторы могут создавать фиктивные фишинговые сообщения и отправлять их внутренним пользователям как средство образования.</span><span class="sxs-lookup"><span data-stu-id="ed37e-130">**Attack simulator**: Admins can create fake phishing messages and send them to internal users as an education tool.</span></span> <span data-ttu-id="ed37e-131">Для получения дополнительных сведений см [в симуляторе атак в Office 365 ATP](attack-simulator.md).</span><span class="sxs-lookup"><span data-stu-id="ed37e-131">For more information, see [Attack Simulator in Office 365 ATP](attack-simulator.md).</span></span>

## <a name="other-anti-phishing-resources"></a><span data-ttu-id="ed37e-132">Другие ресурсы защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="ed37e-132">Other anti-phishing resources</span></span>

- <span data-ttu-id="ed37e-133">Для конечных пользователей: [Защитите себя от фишинговых схем и других форм Интернет-мошенничества](https://support.office.com/article/f84750b4-2f2c-46c3-89f6-e65f7f8c3546).</span><span class="sxs-lookup"><span data-stu-id="ed37e-133">For end-users: [Protect yourself from phishing schemes and other forms of online fraud](https://support.office.com/article/f84750b4-2f2c-46c3-89f6-e65f7f8c3546).</span></span>

- <span data-ttu-id="ed37e-134">[Как Microsoft 365 проверяет адрес отправителя для предотвращения фишинга](how-office-365-validates-the-from-address.md).</span><span class="sxs-lookup"><span data-stu-id="ed37e-134">[How Microsoft 365 validates the From address to prevent phishing](how-office-365-validates-the-from-address.md).</span></span>