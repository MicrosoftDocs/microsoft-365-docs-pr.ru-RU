---
title: Начало использования обучения имитации атаки
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: Администраторы могут научиться использовать обучение моделированию атак для запуска имитации фишинга и атак с использованием паролей в организациях Microsoft 365 E5 или Microsoft Defender для Office 365 (план 2).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1ec5b8175db6eb03e59a31a4dc21d9649c5e7616
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289900"
---
# <a name="get-started-using-attack-simulation-training"></a><span data-ttu-id="5a565-103">Начало использования обучения имитации атаки</span><span class="sxs-lookup"><span data-stu-id="5a565-103">Get started using Attack simulation training</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="5a565-104">Если в вашей организации есть Microsoft 365 E5 или Microsoft Defender для Office 365 (план 2), который включает возможности [анализа](office-365-ti.md)угроз и реагирования на них, вы можете использовать обучение моделированию атак в Центре безопасности Майкрософт для запуска реалистичных сценариев атак в организации.</span><span class="sxs-lookup"><span data-stu-id="5a565-104">If your organization has Microsoft 365 E5 or Microsoft Defender for Office 365 Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack simulation training in the Microsoft Security Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="5a565-105">Эти смоделированные атаки помогут вам определить и найти уязвимых пользователей, прежде чем реальные атаки поляв на вашу нижнюю часть.</span><span class="sxs-lookup"><span data-stu-id="5a565-105">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="5a565-106">Чтобы узнать больше, ознакомьтесь с этой статьей.</span><span class="sxs-lookup"><span data-stu-id="5a565-106">Read this article to learn more.</span></span>

> [!NOTE]
> <span data-ttu-id="5a565-107">Обучение моделированию атак заменяет старый имитатор атак v1, описанный в имитаторе атак [в Microsoft Defender для Office 365.](attack-simulator.md)</span><span class="sxs-lookup"><span data-stu-id="5a565-107">Attack simulation training replaces the old Attack Simulator v1 experience that's described in [Attack Simulator in Microsoft Defender for Office 365](attack-simulator.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="5a565-108">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="5a565-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="5a565-109">Чтобы открыть Центр безопасности Майкрософт, перейдите по этой <https://security.microsoft.com/> теме.</span><span class="sxs-lookup"><span data-stu-id="5a565-109">To open the Microsoft Security Center, go to <https://security.microsoft.com/>.</span></span> <span data-ttu-id="5a565-110">Обучение моделированию атак доступно на обучающем **обучении моделированию атак электронной почты** \> **и совместной работы.**</span><span class="sxs-lookup"><span data-stu-id="5a565-110">Attack simulation training is available at **Email and collaboration** \> **Attack simulation training**.</span></span> <span data-ttu-id="5a565-111">Чтобы перейти непосредственно к обучению моделированию атак, откройте <https://security.microsoft.com/attacksimulator> .</span><span class="sxs-lookup"><span data-stu-id="5a565-111">To go directly to Attack simulation training, open <https://security.microsoft.com/attacksimulator>.</span></span>

- <span data-ttu-id="5a565-112">Дополнительные сведения о доступности обучения моделированию атак в различных подписках Microsoft 365 см. в описании службы [Microsoft Defender для Office 365.](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)</span><span class="sxs-lookup"><span data-stu-id="5a565-112">For more information about the availability of Attack simulation training across different Microsoft 365 subscriptions, see [Microsoft Defender for Office 365 service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="5a565-113">Для выполнения процедур, которые данная статья, вам должны быть назначены разрешения в Центре безопасности & соответствия требованиям или в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5a565-113">You need to be assigned permissions in the Security & Compliance Center or in Azure Active Directory before you can do the procedures in this article.</span></span> <span data-ttu-id="5a565-114">В частности, необходимо быть членом группы "Управление организацией", "Администратор безопасности" или одной из следующих ролей:</span><span class="sxs-lookup"><span data-stu-id="5a565-114">Specifically, you need to be a member of **Organization Management**, **Security Administrator**, or one of the following roles:</span></span>
  - <span data-ttu-id="5a565-115">**Администраторы имитатора** атак: создание и управление всеми аспектами кампаний моделирования атак.</span><span class="sxs-lookup"><span data-stu-id="5a565-115">**Attack Simulator Administrators**: Create and managed all aspects of attack simulation campaigns.</span></span>
  - <span data-ttu-id="5a565-116">**Авторы полезной нагрузки симулятора** атаки: создайте полезной нагрузки атаки, которые администратор может инициировать позже.</span><span class="sxs-lookup"><span data-stu-id="5a565-116">**Attack Simulator Payload Authors**: Create attack payloads that an admin can initiate later.</span></span>

  <span data-ttu-id="5a565-117">Дополнительные сведения см. в сведениях о разрешениях в Центре [безопасности & соответствия](permissions-in-the-security-and-compliance-center.md) требованиям или о ролях [администраторов.](../../admin/add-users/about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="5a565-117">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) or [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="5a565-118">Для обучения моделированию атак соответствующие cmdlets PowerShell не существуют.</span><span class="sxs-lookup"><span data-stu-id="5a565-118">There are no corresponding PowerShell cmdlets for Attack simulation training.</span></span>

- <span data-ttu-id="5a565-119">Имитация атак и учебные данные хранятся вместе с другими данными клиентов для служб Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5a565-119">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="5a565-120">Дополнительные сведения см. в [расположениях данных Microsoft 365.](/microsoft-365/enterprise/o365-data-locations)</span><span class="sxs-lookup"><span data-stu-id="5a565-120">For more information see [Microsoft 365 data locations](/microsoft-365/enterprise/o365-data-locations).</span></span> <span data-ttu-id="5a565-121">Имитация атаки в настоящее время недоступна в следующих регионах: SGP, NOR, ОАЭ, ZAF, GER, BRA и ZA.</span><span class="sxs-lookup"><span data-stu-id="5a565-121">Attack simulation is currently not available in the following regions: SGP, NOR, UAE, ZAF, GER, BRA, and CHE.</span></span>

## <a name="simulations"></a><span data-ttu-id="5a565-122">Имитации</span><span class="sxs-lookup"><span data-stu-id="5a565-122">Simulations</span></span>

<span data-ttu-id="5a565-123">*Фишинг —* это универсальный термин для атак электронной почты, которые пытаются украсть конфиденциальную информацию в сообщениях, которые кажутся надежными или надежными отправителями.</span><span class="sxs-lookup"><span data-stu-id="5a565-123">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="5a565-124">*Фишинг —* это часть подмножества методов, которые мы классифицируют как _социальные инженеры._</span><span class="sxs-lookup"><span data-stu-id="5a565-124">*Phishing* is a part of a subset of techniques we classify as _social engineering_.</span></span>

<span data-ttu-id="5a565-125">В обучении моделированию атак доступны различные методы социальной инженерии:</span><span class="sxs-lookup"><span data-stu-id="5a565-125">In Attack simulation training, multiple types of social engineering techniques are available:</span></span>

- <span data-ttu-id="5a565-126">**Сбор учетных** данных: злоумышленник отправляет получателю сообщение с URL-адресом.</span><span class="sxs-lookup"><span data-stu-id="5a565-126">**Credential harvest**: An attacker sends the recipient a message that contains a URL.</span></span> <span data-ttu-id="5a565-127">Когда получатель щелкает URL-адрес, он перенабирается на веб-сайт, где обычно появляется диалоговое окно с запросом имени пользователя и пароля.</span><span class="sxs-lookup"><span data-stu-id="5a565-127">When the recipient clicks on the URL, they're taken to a website that typically shows a dialog box that asks the user for their username and password.</span></span> <span data-ttu-id="5a565-128">Как правило, на целевой странице используется темы для представления известного веб-сайта, чтобы создать доверие для пользователя.</span><span class="sxs-lookup"><span data-stu-id="5a565-128">Typically, the destination page is themed to represent a well-known website in order to build trust in the user.</span></span>

- <span data-ttu-id="5a565-129">**Вложение вредоносной** программы: злоумышленник отправляет получателю сообщение, содержаное вложение.</span><span class="sxs-lookup"><span data-stu-id="5a565-129">**Malware attachment**: An attacker sends the recipient a message that contains an attachment.</span></span> <span data-ttu-id="5a565-130">Когда получатель открывает вложение, на устройстве пользователя запускается произвольный код (например, макрос), который помогает злоумышленнику установить дополнительный код или закрепить себя.</span><span class="sxs-lookup"><span data-stu-id="5a565-130">When the recipient opens the attachment, arbitrary code (for example, a macro) is run on the user's device to help the attacker install additional code or further entrench themselves.</span></span>

- <span data-ttu-id="5a565-131">**Ссылка во вложении:** это гибридная система сбора учетных данных.</span><span class="sxs-lookup"><span data-stu-id="5a565-131">**Link in attachment**: This is a hybrid of a credential harvest.</span></span> <span data-ttu-id="5a565-132">Злоумышленник отправляет получателю сообщение с URL-адресом внутри вложения.</span><span class="sxs-lookup"><span data-stu-id="5a565-132">An attacker sends the recipient a message that contains a URL inside of an attachment.</span></span> <span data-ttu-id="5a565-133">Когда получатель открывает вложение и щелкает URL-адрес, он перенабирается на веб-сайт, где обычно появляется диалоговое окно с запросом имени пользователя и пароля.</span><span class="sxs-lookup"><span data-stu-id="5a565-133">When the recipient opens the attachment and clicks on the URL, they're taken to a website that typically shows a dialog box that asks the user for their username and password.</span></span> <span data-ttu-id="5a565-134">Как правило, на целевой странице используется темы для представления известного веб-сайта, чтобы создать доверие для пользователя.</span><span class="sxs-lookup"><span data-stu-id="5a565-134">Typically, the destination page is themed to represent a well-known website in order to build trust in the user.</span></span>

- <span data-ttu-id="5a565-135">**Ссылка на вредоносные** программы: злоумышленник отправляет получателю сообщение со ссылкой на вложение на известном сайте общего доступа к файлам (например, SharePoint Online или Dropbox).</span><span class="sxs-lookup"><span data-stu-id="5a565-135">**Link to malware**: An attacker sends the recipient a message that contains a link to an attachment on a well-known file sharing site (for example, SharePoint Online or Dropbox).</span></span> <span data-ttu-id="5a565-136">Когда получатель щелкает URL-адрес, открывается вложение и на устройстве пользователя запускается произвольный код (например, макрос), который помогает злоумышленнику установить дополнительный код или в дальнейшем закрепить себя.</span><span class="sxs-lookup"><span data-stu-id="5a565-136">When the recipient clicks on the URL, the attachment opens and arbitrary code (for example, a macro) is run on the user's device to help the attacker install additional code or further entrench themselves.</span></span>

- <span data-ttu-id="5a565-137">**Диск по URL-адресу:** злоумышленник отправляет получателю сообщения, которые содержат URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="5a565-137">**Drive-by-url**: An attacker sends the recipient a messages that contains a URL.</span></span> <span data-ttu-id="5a565-138">Когда получатель щелкает URL-адрес, он перенажимается на веб-сайт, который пытается выполнить фоновый код.</span><span class="sxs-lookup"><span data-stu-id="5a565-138">When the recipient clicks on the URL, they're taken to a website that tries to run background code.</span></span> <span data-ttu-id="5a565-139">Этот фоновый код пытается собрать сведения о получателе или развернуть произвольный код на своем устройстве.</span><span class="sxs-lookup"><span data-stu-id="5a565-139">This background code attempts to gather information about the recipient or deploy arbitrary code on their device.</span></span> <span data-ttu-id="5a565-140">Как правило, сайт назначения — это известный веб-сайт, который был скомпрометирован или клон известного веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="5a565-140">Typically, the destination website is a well-known website that has been compromised or a clone of a well-known website.</span></span> <span data-ttu-id="5a565-141">Знакомство с веб-сайтом помогает убедить пользователя в том, что ссылка безопасна для щелчка.</span><span class="sxs-lookup"><span data-stu-id="5a565-141">Familiarity with the website helps convince the user that the link is safe to click.</span></span> <span data-ttu-id="5a565-142">Этот метод также называется атакой с _затхлевкой._</span><span class="sxs-lookup"><span data-stu-id="5a565-142">This technique is also known as a _watering hole attack_.</span></span>

> [!NOTE]
> <span data-ttu-id="5a565-143">Перед использованием URL-адреса в фишинговой кампании проверьте доступность имитированных фишинговых URL-адресов в поддерживаемых веб-браузерах.</span><span class="sxs-lookup"><span data-stu-id="5a565-143">Check the availability of the simulated phishing URL in your supported web browsers before you use the URL in a phishing campaign.</span></span> <span data-ttu-id="5a565-144">Хотя мы работаем со многими поставщиками репутации URL-адресов, чтобы всегда разрешал эти URL-адреса имитации, мы не всегда полностью охватим (например, Google Safe Browsing).</span><span class="sxs-lookup"><span data-stu-id="5a565-144">While we work with many URL reputation vendors to always allow these simulation URLs, we don't always have full coverage (for example, Google Safe Browsing).</span></span> <span data-ttu-id="5a565-145">Большинство поставщиков предоставляют рекомендации, которые позволяют всегда разрешать определенные URL-адреса (например, <https://support.google.com/chrome/a/answer/7532419> ).</span><span class="sxs-lookup"><span data-stu-id="5a565-145">Most vendors provide guidance that allows you to always allow specific URLs (for example, <https://support.google.com/chrome/a/answer/7532419>).</span></span>

<span data-ttu-id="5a565-146">URL-адреса, используемые в обучении моделированию атак, описаны в следующем списке:</span><span class="sxs-lookup"><span data-stu-id="5a565-146">The URLs that are used by Attack simulation training are described in the following list:</span></span>

- <https://www.mcsharepoint.com>
- <https://www.attemplate.com>
- <https://www.doctricant.com>
- <https://www.mesharepoint.com>
- <https://www.officence.com>
- <https://www.officenced.com>
- <https://www.officences.com>
- <https://www.officentry.com>
- <https://www.officested.com>
- <https://www.prizegives.com>
- <https://www.prizemons.com>
- <https://www.prizewel.com>
- <https://www.prizewings.com>
- <https://www.shareholds.com>
- <https://www.sharepointen.com>
- <https://www.sharepointin.com>
- <https://www.sharepointle.com>
- <https://www.sharesbyte.com>
- <https://www.sharession.com>
- <https://www.sharestion.com>
- <https://www.templateau.com>
- <https://www.templatent.com>
- <https://www.templatern.com>
- <https://www.windocyte.com>

### <a name="create-a-simulation"></a><span data-ttu-id="5a565-147">Создание имитации</span><span class="sxs-lookup"><span data-stu-id="5a565-147">Create a simulation</span></span>

<span data-ttu-id="5a565-148">Пошаговая инструкция по созданию и отправке имитации см. в подделывание [фишинговой атаки.](attack-simulation-training.md)</span><span class="sxs-lookup"><span data-stu-id="5a565-148">For step by step instructions on how to create and send a new simulation, see [Simulate a phishing attack](attack-simulation-training.md).</span></span>

### <a name="create-a-payload"></a><span data-ttu-id="5a565-149">Создание полезной нагрузки</span><span class="sxs-lookup"><span data-stu-id="5a565-149">Create a payload</span></span>

<span data-ttu-id="5a565-150">Пошаговая инструкция по созданию полезной нагрузки для использования в имитации см. в подстановке "Создание настраиваемой полезной нагрузки для обучения моделированию [атак".](attack-simulation-training-payloads.md)</span><span class="sxs-lookup"><span data-stu-id="5a565-150">For step by step instructions on how to create a payload for use within a simulation, see [Create a custom payload for Attack simulation training](attack-simulation-training-payloads.md).</span></span>

### <a name="gaining-insights"></a><span data-ttu-id="5a565-151">Получение статистики</span><span class="sxs-lookup"><span data-stu-id="5a565-151">Gaining insights</span></span>

<span data-ttu-id="5a565-152">Пошаговая инструкция по сбору информации с помощью отчетов см. в обучающем обучении по имитации [атак.](attack-simulation-training-insights.md)</span><span class="sxs-lookup"><span data-stu-id="5a565-152">For step by step instructions on how to gain insights with reporting, see [Gain insights through Attack simulation training](attack-simulation-training-insights.md).</span></span>
