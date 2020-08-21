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
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
description: Администраторы могут узнать о функциях защиты от фишинга в службах Exchange Online Protection (EOP) и Office 365 Advanced Threat Protection (Office 365 ATP).
ms.openlocfilehash: 5594c4e7033ab70a622403bca7759cd4b89f111a
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827449"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a><span data-ttu-id="21019-103">Защита от фишинга в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="21019-103">Anti-phishing protection in Microsoft 365</span></span>

<span data-ttu-id="21019-104">*Фишинг —* это атака, которая пытается украсть конфиденциальную информацию в сообщениях, кажущихся как надежные или надежные отправители.</span><span class="sxs-lookup"><span data-stu-id="21019-104">*Phishing* is an email attack that tries to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="21019-105">Существует определенные категории фишинга.</span><span class="sxs-lookup"><span data-stu-id="21019-105">There are specific categories of phishing.</span></span> <span data-ttu-id="21019-106">Пример:</span><span class="sxs-lookup"><span data-stu-id="21019-106">For example:</span></span>

- <span data-ttu-id="21019-107">**Целевой фишинг использует** очень сфокусированный и настраиваемый контент, специально подобранный для целевых получателей (обычно после согласования получателей злоумышленником).</span><span class="sxs-lookup"><span data-stu-id="21019-107">**Spear phishing** uses very focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

- <span data-ttu-id="21019-108">**При важнее стили** направляются руководителям или другим высоким целевым объектам в организации для максимального эффекта.</span><span class="sxs-lookup"><span data-stu-id="21019-108">**Whaling** is directed at executives or other high value targets within an organization for maximum effect.</span></span>

- <span data-ttu-id="21019-109">**Компрометация бизнес-сообщений использует** поддельных доверенных отправителей (финансовых руководителей, клиентов, доверенных партнеров и т. д.) для обмана в частности, по обманому получателем в случае утверждения платежей, передачи средств или разакрытия данных клиентов.</span><span class="sxs-lookup"><span data-stu-id="21019-109">**Business email compromise (BEC)** uses forged trusted senders (financial officers, customers, trusted partners, etc.) in an effort to trick the recipient into approving payments, transferring funds, or disclosing customer data.</span></span>

- <span data-ttu-id="21019-110">**Программа-шантажист,** шифруя данные и заплату на расшифровку практически всегда запускается в фишинговых сообщениях.</span><span class="sxs-lookup"><span data-stu-id="21019-110">**Ransomware** that encrypts your data and demands payment to decrypt it almost always starts out in phishing messages.</span></span> <span data-ttu-id="21019-111">Защита от фишинга не поможет расшифровать зашифрованные файлы, но помогает обнаружить исходные фишинговые сообщения, связанные с кампанией программ-шантажистов.</span><span class="sxs-lookup"><span data-stu-id="21019-111">Anti-phishing protection can't help you decrypt encrypted files, but it can help detect the initial phishing messages that are associated with the ransomware campaign.</span></span> <span data-ttu-id="21019-112">Дополнительные сведения о восстановлении после атаки программ-шумоподавления см. в статье ["Восстановление после атаки программ-шинахдиалов из Microsoft 365".](recover-from-ransomware.md)</span><span class="sxs-lookup"><span data-stu-id="21019-112">For more information about recovering from a ransomware attack, see [Recover from a ransomware attack in Microsoft 365](recover-from-ransomware.md).</span></span>

<span data-ttu-id="21019-113">В результате растущего сложности атак даже трудно обучить пользователей с могли определить сложные фишинговые сообщения.</span><span class="sxs-lookup"><span data-stu-id="21019-113">With the growing complexity of attacks, it's even difficult for trained users to identify sophisticated phishing messages.</span></span> <span data-ttu-id="21019-114">К счастью, вам могут помочь Exchange Online Protection (EOP) и дополнительные функции Office 365 Advanced Threat Protection (Office 365 ATP).</span><span class="sxs-lookup"><span data-stu-id="21019-114">Fortunately, Exchange Online Protection (EOP) and the additional features in Office 365 Advanced Threat Protection (Office 365 ATP) can help.</span></span>

## <a name="anti-phishing-protection-in-eop"></a><span data-ttu-id="21019-115">Защита от фишинга в EOP</span><span class="sxs-lookup"><span data-stu-id="21019-115">Anti-phishing protection in EOP</span></span>

<span data-ttu-id="21019-116">EOP (то есть, в организациях Microsoft 365 без ATP) содержатся функции, помогающие защитить организацию от фишинговых угроз:</span><span class="sxs-lookup"><span data-stu-id="21019-116">EOP (that is, Microsoft 365 organizations without ATP) contains features that can help protect your organization from phishing threats:</span></span>

- <span data-ttu-id="21019-117">**Аналитика подделки**: Просмотрите поддельные сообщения от отправителей во внутренних и внешних доменах и разрешите или заблокируйте этих отправителей.</span><span class="sxs-lookup"><span data-stu-id="21019-117">**Spoof intelligence**: Review spoofed messages from senders in internal and external domains, and allow or block those senders.</span></span> <span data-ttu-id="21019-118">Дополнительные сведения см. в статье ["Настройка аналитики спуфинга" в EOP.](learn-about-spoof-intelligence.md)</span><span class="sxs-lookup"><span data-stu-id="21019-118">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

- <span data-ttu-id="21019-119">**Политики защиты от фишинга в EOP:** включение и отключение аналитики спуфинга, включение и отключение непроверенных отправителей в Outlook и выбор действия для заблокированных отправителей (перемещение в папку нежелательной почты или помещение на карантин).</span><span class="sxs-lookup"><span data-stu-id="21019-119">**Anti-phishing policies in EOP**: Turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and specify the action for blocked spoofed senders (move to Junk Email folder or quarantine).</span></span> <span data-ttu-id="21019-120">Дополнительные сведения см. в статье ["Настройка политик защиты от фишинга" в EOP.](configure-anti-phishing-policies-eop.md)</span><span class="sxs-lookup"><span data-stu-id="21019-120">For more information, see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

- <span data-ttu-id="21019-121">**Неявная проверка**подлинности электронной почты: служба EOP улучшает стандартные проверки подлинности электронной почты[(SPF,](set-up-spf-in-office-365-to-help-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)и [DMARC)](use-dmarc-to-validate-email.md)с репутацией отправителя, журналом отправителя, журналом получателей, анализом поведения и другими прогнозируемыми методиками для идентификации поддельных отправителей.</span><span class="sxs-lookup"><span data-stu-id="21019-121">**Implicit email authentication**: EOP enhances standard email authentication checks for inbound email ([SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md)) with sender reputation, sender history, recipient history, behavioral analysis, and other advanced techniques to help identify forged senders.</span></span> <span data-ttu-id="21019-122">Дополнительные сведения см. в статье [Поверка подлинности электронной почты в Microsoft 365](email-validation-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="21019-122">For more information, see [Email authentication in Microsoft 365](email-validation-and-authentication.md).</span></span>

## <a name="additional-anti-phishing-protection-in-office-365-atp"></a><span data-ttu-id="21019-123">Дополнительная защита от фишинга в Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="21019-123">Additional anti-phishing protection in Office 365 ATP</span></span>

<span data-ttu-id="21019-124">В Office 365 ATP представлены дополнительные и более сложные функции защиты от фишинга:</span><span class="sxs-lookup"><span data-stu-id="21019-124">Office 365 ATP contains additional and more advanced anti-phishing features:</span></span>

- <span data-ttu-id="21019-125">**Политики защиты от фишинга ATP:** создание новых настраиваемых политик, настройка параметров защиты от олицетворения (защита пользователей и доменов от олицетворения), параметров аналитики почтовых ящиков и регулируемые расширенные пороговые значения фишинга.</span><span class="sxs-lookup"><span data-stu-id="21019-125">**ATP anti-phishing policies**: Create new custom policies, configure anti-impersonation settings (protect users and domains from impersonation), mailbox intelligence settings, and adjustable advanced phishing thresholds.</span></span> <span data-ttu-id="21019-126">Дополнительные сведения см. в статье ["Настройка политик защиты от фишинга" ATP в Microsoft 365.](configure-atp-anti-phishing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="21019-126">For more information, see [Configure ATP anti-phishing policies in Microsoft 365](configure-atp-anti-phishing-policies.md).</span></span> <span data-ttu-id="21019-127">Дополнительные сведения о различиях между политиками защиты от фишинга и политиками защиты от фишинга ATP см. в статье "Политики защиты [от фишинга" в Microsoft 365.](set-up-anti-phishing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="21019-127">For more information about the differences between anti-phishing policies and ATP anti-phishing policies, see [Anti-phishing policies in Microsoft 365](set-up-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="21019-128">**Представления кампаний:** машинное обучение и другая эвристика идентична являться при вовлеченности в скоординированные фишинговые атаки на всю службу и вашу организацию.</span><span class="sxs-lookup"><span data-stu-id="21019-128">**Campaign Views**: Machine learning and other heuristics identify and analyze messages that are involved in coordinated phishing attacks against the entire service and your organization.</span></span> <span data-ttu-id="21019-129">Дополнительные сведения см. в статье ["Представления кампаний" в Office 365 ATP.](campaigns.md)</span><span class="sxs-lookup"><span data-stu-id="21019-129">For more information, see [Campaign Views in Office 365 ATP](campaigns.md).</span></span>

- <span data-ttu-id="21019-130">**Имитатор атак: администраторы**могут создавать поддельные фишинговые сообщения и отправлять их внутренним пользователям как средство обучения.</span><span class="sxs-lookup"><span data-stu-id="21019-130">**Attack simulator**: Admins can create fake phishing messages and send them to internal users as an education tool.</span></span> <span data-ttu-id="21019-131">Дополнительные сведения см. в [статье "Эмулятор атак в Office 365 ATP".](attack-simulator.md)</span><span class="sxs-lookup"><span data-stu-id="21019-131">For more information, see [Attack Simulator in Office 365 ATP](attack-simulator.md).</span></span>

## <a name="other-anti-phishing-resources"></a><span data-ttu-id="21019-132">Другие антифишинговые ресурсы</span><span class="sxs-lookup"><span data-stu-id="21019-132">Other anti-phishing resources</span></span>

- <span data-ttu-id="21019-133">Для пользователей: [защитите себя от схем фишинга и других форм мошенничества в Интернете.](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593)</span><span class="sxs-lookup"><span data-stu-id="21019-133">For end-users: [Protect yourself from phishing schemes and other forms of online fraud](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593).</span></span>

- <span data-ttu-id="21019-134">[Как Microsoft 365 проверяет адрес отправителя, чтобы предотвратить фишинг.](how-office-365-validates-the-from-address.md)</span><span class="sxs-lookup"><span data-stu-id="21019-134">[How Microsoft 365 validates the From address to prevent phishing](how-office-365-validates-the-from-address.md).</span></span>
