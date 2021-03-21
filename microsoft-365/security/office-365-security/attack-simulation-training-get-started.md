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
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: Администраторы могут узнать, как использовать обучение имитации атаки для имитации фишинга и атак паролей в организациях Microsoft 365 E5 или Microsoft Defender для Office 365 Plan 2.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6e344153ef433bc13b16136e584ec4da73fcef6a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921352"
---
# <a name="get-started-using-attack-simulation-training"></a><span data-ttu-id="aee71-103">Начало использования обучения имитации атаки</span><span class="sxs-lookup"><span data-stu-id="aee71-103">Get started using Attack simulation training</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="aee71-104">Если в вашей организации есть Microsoft 365 E5 или Microsoft Defender для [](office-365-ti.md)Office 365 Plan 2, который включает возможности расследования угроз и реагирования, вы можете использовать обучение моделированию атак в Центре безопасности Майкрософт для запуска реалистичных сценариев атак в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="aee71-104">If your organization has Microsoft 365 E5 or Microsoft Defender for Office 365 Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack simulation training in the Microsoft Security Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="aee71-105">Эти смоделированные атаки помогут вам определить и найти уязвимых пользователей до того, как реальная атака сказывается на вашей нижней строке.</span><span class="sxs-lookup"><span data-stu-id="aee71-105">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="aee71-106">Подробнее читайте в этой статье.</span><span class="sxs-lookup"><span data-stu-id="aee71-106">Read this article to learn more.</span></span>

> [!NOTE]
> <span data-ttu-id="aee71-107">Обучение имитации атак заменяет старый симулятор атаки v1, описанный в симуляторе атак в [Microsoft Defender для Office 365.](attack-simulator.md)</span><span class="sxs-lookup"><span data-stu-id="aee71-107">Attack simulation training replaces the old Attack Simulator v1 experience that's described in [Attack Simulator in Microsoft Defender for Office 365](attack-simulator.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="aee71-108">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="aee71-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="aee71-109">Чтобы открыть Центр безопасности Майкрософт, перейдите к <https://security.microsoft.com/> .</span><span class="sxs-lookup"><span data-stu-id="aee71-109">To open the Microsoft Security Center, go to <https://security.microsoft.com/>.</span></span> <span data-ttu-id="aee71-110">Обучение моделированию атак доступно на тренинге **по** моделированию атак по электронной почте и \> **совместной работе.**</span><span class="sxs-lookup"><span data-stu-id="aee71-110">Attack simulation training is available at **Email and collaboration** \> **Attack simulation training**.</span></span> <span data-ttu-id="aee71-111">Чтобы перейти непосредственно к обучению имитации атаки, откройте <https://security.microsoft.com/attacksimulator> .</span><span class="sxs-lookup"><span data-stu-id="aee71-111">To go directly to Attack simulation training, open <https://security.microsoft.com/attacksimulator>.</span></span>

- <span data-ttu-id="aee71-112">Дополнительные сведения о доступности обучения имитации атаки для различных подписок Microsoft 365 см. в описании [службы Microsoft Defender для Office 365.](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)</span><span class="sxs-lookup"><span data-stu-id="aee71-112">For more information about the availability of Attack simulation training across different Microsoft 365 subscriptions, see [Microsoft Defender for Office 365 service description](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="aee71-113">Вам необходимо получить разрешения в Центре & безопасности или в Azure Active Directory, прежде чем вы сможете сделать процедуры в этой статье.</span><span class="sxs-lookup"><span data-stu-id="aee71-113">You need to be assigned permissions in the Security & Compliance Center or in Azure Active Directory before you can do the procedures in this article.</span></span> <span data-ttu-id="aee71-114">В частности, вам необходимо быть членом **Организации Управления,** **Администратором** безопасности или одной из следующих ролей:</span><span class="sxs-lookup"><span data-stu-id="aee71-114">Specifically, you need to be a member of **Organization Management**, **Security Administrator**, or one of the following roles:</span></span>
  - <span data-ttu-id="aee71-115">**Администраторы симулятора атак.** Создайте и управляйте всеми аспектами кампаний имитации атак.</span><span class="sxs-lookup"><span data-stu-id="aee71-115">**Attack Simulator Administrators**: Create and managed all aspects of attack simulation campaigns.</span></span>
  - <span data-ttu-id="aee71-116">**Авторы полезной нагрузки** симулятора атаки. Создайте полезной нагрузки, которые администратор может инициировать позже.</span><span class="sxs-lookup"><span data-stu-id="aee71-116">**Attack Simulator Payload Authors**: Create attack payloads that an admin can initiate later.</span></span>

  <span data-ttu-id="aee71-117">Дополнительные сведения см. [в сведениях Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) или About Admin [roles.](../../admin/add-users/about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="aee71-117">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) or [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="aee71-118">Соответствующие кодлеты PowerShell для подготовки к имитации атаки не имеются.</span><span class="sxs-lookup"><span data-stu-id="aee71-118">There are no corresponding PowerShell cmdlets for Attack simulation training.</span></span>

- <span data-ttu-id="aee71-119">Имитация атаки и связанные с обучением данные хранятся с другими данными клиентов для служб Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="aee71-119">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="aee71-120">Дополнительные сведения см. [в сайте Microsoft 365 data locations.](../../enterprise/o365-data-locations.md)</span><span class="sxs-lookup"><span data-stu-id="aee71-120">For more information see [Microsoft 365 data locations](../../enterprise/o365-data-locations.md).</span></span> <span data-ttu-id="aee71-121">Моделирование атак доступно в следующих регионах: NAM, APC, EUR, IND, CAN, AUS, FRA, GBR, JPN и KOR.</span><span class="sxs-lookup"><span data-stu-id="aee71-121">Attack simulation is available in the following regions: NAM, APC, EUR, IND, CAN, AUS, FRA, GBR, JPN, and KOR.</span></span>

## <a name="simulations"></a><span data-ttu-id="aee71-122">Моделирование</span><span class="sxs-lookup"><span data-stu-id="aee71-122">Simulations</span></span>

<span data-ttu-id="aee71-123">*Фишинг —* это общий термин для атак электронной почты, которые пытаются украсть конфиденциальные сведения в сообщениях, которые, как представляется, являются законными или доверенными отправителями.</span><span class="sxs-lookup"><span data-stu-id="aee71-123">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="aee71-124">*Фишинг является* частью подмножества методов, которые мы классифицировать как _социальные инженерии_.</span><span class="sxs-lookup"><span data-stu-id="aee71-124">*Phishing* is a part of a subset of techniques we classify as _social engineering_.</span></span>

<span data-ttu-id="aee71-125">В обучении моделированию атак доступны несколько типов методов социальной инженерии:</span><span class="sxs-lookup"><span data-stu-id="aee71-125">In Attack simulation training, multiple types of social engineering techniques are available:</span></span>

- <span data-ttu-id="aee71-126">**Сбор учетных** данных. Злоумышленник отправляет получателю сообщение с URL-адресом.</span><span class="sxs-lookup"><span data-stu-id="aee71-126">**Credential harvest**: An attacker sends the recipient a message that contains a URL.</span></span> <span data-ttu-id="aee71-127">Когда получатель щелкает URL-адрес, он передается на веб-сайт, на который обычно указывается диалоговое окно с запросом имени пользователя и пароля.</span><span class="sxs-lookup"><span data-stu-id="aee71-127">When the recipient clicks on the URL, they're taken to a website that typically shows a dialog box that asks the user for their username and password.</span></span> <span data-ttu-id="aee71-128">Как правило, для создания доверия к пользователю на странице назначения используется themed для представления известного веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="aee71-128">Typically, the destination page is themed to represent a well-known website in order to build trust in the user.</span></span>

- <span data-ttu-id="aee71-129">**Вложение** вредоносных программ. Злоумышленник отправляет получателю сообщение, содержаное вложение.</span><span class="sxs-lookup"><span data-stu-id="aee71-129">**Malware attachment**: An attacker sends the recipient a message that contains an attachment.</span></span> <span data-ttu-id="aee71-130">Когда получатель открывает вложение, произвольный код (например, макрос) запускается на устройстве пользователя, чтобы помочь злоумышленнику установить дополнительный код или закрепить себя.</span><span class="sxs-lookup"><span data-stu-id="aee71-130">When the recipient opens the attachment, arbitrary code (for example, a macro) is run on the user's device to help the attacker install additional code or further entrench themselves.</span></span>

- <span data-ttu-id="aee71-131">**Ссылка в приложении.** Это гибрид сбора учетных данных.</span><span class="sxs-lookup"><span data-stu-id="aee71-131">**Link in attachment**: This is a hybrid of a credential harvest.</span></span> <span data-ttu-id="aee71-132">Злоумышленник отправляет получателю сообщение, содержаное URL-адрес внутри вложения.</span><span class="sxs-lookup"><span data-stu-id="aee71-132">An attacker sends the recipient a message that contains a URL inside of an attachment.</span></span> <span data-ttu-id="aee71-133">Когда получатель открывает вложение и щелкает ПО URL-адресу, он передается на веб-сайт, который обычно показывает диалоговое окно, в которое пользователь спрашивает имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="aee71-133">When the recipient opens the attachment and clicks on the URL, they're taken to a website that typically shows a dialog box that asks the user for their username and password.</span></span> <span data-ttu-id="aee71-134">Как правило, для создания доверия к пользователю на странице назначения используется themed для представления известного веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="aee71-134">Typically, the destination page is themed to represent a well-known website in order to build trust in the user.</span></span>

- <span data-ttu-id="aee71-135">**Ссылка на вредоносные** программы: злоумышленник отправляет получателю сообщение, содержаное ссылку на вложение на известном сайте общего доступа к файлам (например, SharePoint Online или Dropbox).</span><span class="sxs-lookup"><span data-stu-id="aee71-135">**Link to malware**: An attacker sends the recipient a message that contains a link to an attachment on a well-known file sharing site (for example, SharePoint Online or Dropbox).</span></span> <span data-ttu-id="aee71-136">Когда получатель щелкает URL-адрес, открывается вложение и произвольный код (например, макрос) запускается на устройстве пользователя, чтобы помочь злоумышленнику установить дополнительный код или закрепить себя.</span><span class="sxs-lookup"><span data-stu-id="aee71-136">When the recipient clicks on the URL, the attachment opens and arbitrary code (for example, a macro) is run on the user's device to help the attacker install additional code or further entrench themselves.</span></span>

- <span data-ttu-id="aee71-137">**Url-адрес drive-by-url.** Злоумышленник отправляет получателю сообщения, содержавшие URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="aee71-137">**Drive-by-url**: An attacker sends the recipient a messages that contains a URL.</span></span> <span data-ttu-id="aee71-138">Когда получатель щелкает URL-адрес, он передается на веб-сайт, который пытается запустить фоновый код.</span><span class="sxs-lookup"><span data-stu-id="aee71-138">When the recipient clicks on the URL, they're taken to a website that tries to run background code.</span></span> <span data-ttu-id="aee71-139">Этот фоновый код пытается собрать сведения о получателе или развернуть произвольный код на своем устройстве.</span><span class="sxs-lookup"><span data-stu-id="aee71-139">This background code attempts to gather information about the recipient or deploy arbitrary code on their device.</span></span> <span data-ttu-id="aee71-140">Как правило, веб-сайт назначения — это хорошо известный веб-сайт, который был скомпрометирован или клон известного веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="aee71-140">Typically, the destination website is a well-known website that has been compromised or a clone of a well-known website.</span></span> <span data-ttu-id="aee71-141">Знакомство с веб-сайтом помогает убедить пользователя в том, что ссылка является безопасной для нажатия.</span><span class="sxs-lookup"><span data-stu-id="aee71-141">Familiarity with the website helps convince the user that the link is safe to click.</span></span> <span data-ttu-id="aee71-142">Этот метод также известен как атака _отверстия для поливка._</span><span class="sxs-lookup"><span data-stu-id="aee71-142">This technique is also known as a _watering hole attack_.</span></span>

> [!NOTE]
> <span data-ttu-id="aee71-143">Проверьте доступность смоделированных URL-адресов фишинга в поддерживаемых веб-браузерах перед использованием URL-адреса в фишинговой кампании.</span><span class="sxs-lookup"><span data-stu-id="aee71-143">Check the availability of the simulated phishing URL in your supported web browsers before you use the URL in a phishing campaign.</span></span> <span data-ttu-id="aee71-144">Хотя мы работаем со многими поставщиками репутации URL-адресов, чтобы всегда разрешал эти URL-адреса моделирования, мы не всегда имеем полное покрытие (например, Google Safe Browsing).</span><span class="sxs-lookup"><span data-stu-id="aee71-144">While we work with many URL reputation vendors to always allow these simulation URLs, we don't always have full coverage (for example, Google Safe Browsing).</span></span> <span data-ttu-id="aee71-145">Большинство поставщиков предоставляют рекомендации, которые позволяют всегда разрешать определенные URL-адреса (например, <https://support.google.com/chrome/a/answer/7532419> ).</span><span class="sxs-lookup"><span data-stu-id="aee71-145">Most vendors provide guidance that allows you to always allow specific URLs (for example, <https://support.google.com/chrome/a/answer/7532419>).</span></span>

<span data-ttu-id="aee71-146">URL-адреса, используемые в обучении имитации атаки, описаны в следующем списке:</span><span class="sxs-lookup"><span data-stu-id="aee71-146">The URLs that are used by Attack simulation training are described in the following list:</span></span>

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

### <a name="create-a-simulation"></a><span data-ttu-id="aee71-147">Создание имитации</span><span class="sxs-lookup"><span data-stu-id="aee71-147">Create a simulation</span></span>

<span data-ttu-id="aee71-148">Инструкции по созданию и отправке нового моделирования см. в инструкции по имитации [фишинговой атаки.](attack-simulation-training.md)</span><span class="sxs-lookup"><span data-stu-id="aee71-148">For step by step instructions on how to create and send a new simulation, see [Simulate a phishing attack](attack-simulation-training.md).</span></span>

### <a name="create-a-payload"></a><span data-ttu-id="aee71-149">Создание полезной нагрузки</span><span class="sxs-lookup"><span data-stu-id="aee71-149">Create a payload</span></span>

<span data-ttu-id="aee71-150">Инструкции по созданию полезной нагрузки для использования в имитации см. в инструкции по созданию настраиваемой полезной нагрузки для обучения [имитации атаки.](attack-simulation-training-payloads.md)</span><span class="sxs-lookup"><span data-stu-id="aee71-150">For step by step instructions on how to create a payload for use within a simulation, see [Create a custom payload for Attack simulation training](attack-simulation-training-payloads.md).</span></span>

### <a name="gaining-insights"></a><span data-ttu-id="aee71-151">Получение информации</span><span class="sxs-lookup"><span data-stu-id="aee71-151">Gaining insights</span></span>

<span data-ttu-id="aee71-152">Инструкции по пошаговую информацию о том, как получить сведения с отчетами, см. в рублях [Gain insights through Attack simulation training.](attack-simulation-training-insights.md)</span><span class="sxs-lookup"><span data-stu-id="aee71-152">For step by step instructions on how to gain insights with reporting, see [Gain insights through Attack simulation training](attack-simulation-training-insights.md).</span></span>

> [!NOTE]
> <span data-ttu-id="aee71-153">Симулятор атак использует безопасные ссылки в Defender для Office 365 для безопасного отслеживания щелкающих данных для URL-адреса  в сообщении полезной нагрузки, которое отправляется целевым получателям фишинговой кампании, даже если включен параметр "Не отслеживайте щелчки пользователя в политиках безопасных ссылок".</span><span class="sxs-lookup"><span data-stu-id="aee71-153">Attack Simulator uses Safe Links in Defender for Office 365 to securely track click data for the URL in the payload message that's sent to targeted recipients of a phishing campaign, even if the **Do not track user clicks** setting in Safe Links policies is turned on.</span></span>