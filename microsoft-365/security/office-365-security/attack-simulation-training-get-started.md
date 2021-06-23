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
description: Администраторы могут научиться использовать обучение имитации атаки для имитации фишинга и атак паролей в Microsoft 365 E5 или Microsoft Defender для Office 365 plan 2.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ad86f77399cfa2a3a780d3fed7e483e3c11bc08d
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2021
ms.locfileid: "53082904"
---
# <a name="get-started-using-attack-simulation-training"></a><span data-ttu-id="a2269-103">Начало использования обучения имитации атаки</span><span class="sxs-lookup"><span data-stu-id="a2269-103">Get started using Attack simulation training</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a2269-104">**Применяется к** [Microsoft Defender для Office 365 плана 2](defender-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="a2269-104">**Applies to** [Microsoft Defender for Office 365 plan 2](defender-for-office-365.md)</span></span>

<span data-ttu-id="a2269-105">Если в вашей организации Microsoft 365 E5 или Microsoft Defender для Office 365 Plan 2, который включает возможности расследования и реагирования на [угрозы,](office-365-ti.md)вы можете использовать обучение имитации атаки на портале Microsoft 365 Defender для запуска реалистичных сценариев атак в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="a2269-105">If your organization has Microsoft 365 E5 or Microsoft Defender for Office 365 Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack simulation training in the Microsoft 365 Defender portal to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="a2269-106">Эти смоделированные атаки помогут вам определить и найти уязвимых пользователей до того, как реальная атака сказывается на вашей нижней строке.</span><span class="sxs-lookup"><span data-stu-id="a2269-106">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="a2269-107">Подробнее читайте в этой статье.</span><span class="sxs-lookup"><span data-stu-id="a2269-107">Read this article to learn more.</span></span>

> [!NOTE]
> <span data-ttu-id="a2269-108">Обучение имитации атаки заменяет старый симулятор атаки v1, описанный в симуляторе атак в [Microsoft Defender для](attack-simulator.md)Office 365 .</span><span class="sxs-lookup"><span data-stu-id="a2269-108">Attack simulation training replaces the old Attack Simulator v1 experience that's described in [Attack Simulator in Microsoft Defender for Office 365](attack-simulator.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a2269-109">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="a2269-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a2269-110">Чтобы открыть портал Microsoft 365 Defender, перейдите на сайт <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="a2269-110">To open the Microsoft 365 Defender portal, go to <https://security.microsoft.com>.</span></span> <span data-ttu-id="a2269-111">Обучение моделированию атак доступно на тренинге **по** моделированию атак по электронной почте и \> **совместной работе.**</span><span class="sxs-lookup"><span data-stu-id="a2269-111">Attack simulation training is available at **Email and collaboration** \> **Attack simulation training**.</span></span> <span data-ttu-id="a2269-112">Чтобы перейти непосредственно к обучению имитации атаки, откройте <https://security.microsoft.com/attacksimulator> .</span><span class="sxs-lookup"><span data-stu-id="a2269-112">To go directly to Attack simulation training, open <https://security.microsoft.com/attacksimulator>.</span></span>

- <span data-ttu-id="a2269-113">Дополнительные сведения о доступности учебных занятий по имитации атаки в различных Microsoft 365 подписках см. в описании службы [Microsoft Defender для Office 365.](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)</span><span class="sxs-lookup"><span data-stu-id="a2269-113">For more information about the availability of Attack simulation training across different Microsoft 365 subscriptions, see [Microsoft Defender for Office 365 service description](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="a2269-114">Вам необходимо получить разрешения на портале Microsoft 365 Defender или в Azure Active Directory, прежде чем вы сможете сделать процедуры в этой статье.</span><span class="sxs-lookup"><span data-stu-id="a2269-114">You need to be assigned permissions in the Microsoft 365 Defender portal or in Azure Active Directory before you can do the procedures in this article.</span></span> <span data-ttu-id="a2269-115">В частности, вам необходимо быть членом **Организации Управления,** **Администратором** безопасности или одной из следующих ролей:</span><span class="sxs-lookup"><span data-stu-id="a2269-115">Specifically, you need to be a member of **Organization Management**, **Security Administrator**, or one of the following roles:</span></span>
  - <span data-ttu-id="a2269-116">**Администраторы симулятора атак.** Создайте и управляйте всеми аспектами кампаний имитации атак.</span><span class="sxs-lookup"><span data-stu-id="a2269-116">**Attack Simulator Administrators**: Create and managed all aspects of attack simulation campaigns.</span></span>
  - <span data-ttu-id="a2269-117">**Авторы полезной нагрузки** симулятора атаки. Создайте полезной нагрузки, которые администратор может инициировать позже.</span><span class="sxs-lookup"><span data-stu-id="a2269-117">**Attack Simulator Payload Authors**: Create attack payloads that an admin can initiate later.</span></span>

  <span data-ttu-id="a2269-118">Дополнительные сведения см. [в "Разрешениях"](permissions-microsoft-365-security-center.md) на портале Microsoft 365 Defender или о ролях [администратора.](../../admin/add-users/about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="a2269-118">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md) or [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="a2269-119">Соответствующие кодлеты PowerShell для подготовки к имитации атаки не имеются.</span><span class="sxs-lookup"><span data-stu-id="a2269-119">There are no corresponding PowerShell cmdlets for Attack simulation training.</span></span>

- <span data-ttu-id="a2269-120">Имитация атаки и связанные с обучением данные хранятся с другими данными клиентов для Microsoft 365 служб.</span><span class="sxs-lookup"><span data-stu-id="a2269-120">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="a2269-121">Дополнительные сведения [см. в Microsoft 365 расположения данных.](../../enterprise/o365-data-locations.md)</span><span class="sxs-lookup"><span data-stu-id="a2269-121">For more information see [Microsoft 365 data locations](../../enterprise/o365-data-locations.md).</span></span> <span data-ttu-id="a2269-122">Моделирование атак доступно в следующих регионах: NAM, APC, EUR, IND, CAN, AUS, FRA, GBR, JPN и KOR.</span><span class="sxs-lookup"><span data-stu-id="a2269-122">Attack simulation is available in the following regions: NAM, APC, EUR, IND, CAN, AUS, FRA, GBR, JPN, and KOR.</span></span>

- <span data-ttu-id="a2269-123">С 15 июня 2021 г. обучение имитации атаки доступно в GCC.</span><span class="sxs-lookup"><span data-stu-id="a2269-123">As of June 15 2021, Attack simulation training is available in GCC.</span></span> <span data-ttu-id="a2269-124">Если в вашей организации Office 365 G5 GCC или Microsoft Defender для Office 365 (План 2) для правительства, вы можете использовать обучение имитации атаки на портале Microsoft 365 Defender для запуска реалистичных сценариев атак в вашей организации, как описано в этой статье.</span><span class="sxs-lookup"><span data-stu-id="a2269-124">If your organization has Office 365 G5 GCC or Microsoft Defender for Office 365 (Plan 2) for Government, you can use Attack simulation training in the Microsoft 365 Defender portal to run realistic attack scenarios in your organization as described in this article.</span></span> <span data-ttu-id="a2269-125">Обучение моделированию атак пока не доступно в GCC среде High или DoD.</span><span class="sxs-lookup"><span data-stu-id="a2269-125">Attack simulation training is not yet available in GCC High or DoD environments.</span></span>

> [!NOTE]
> <span data-ttu-id="a2269-126">Обучение имитации атак предоставляет клиентам E3 подмножество возможностей в качестве пробной пробной части.</span><span class="sxs-lookup"><span data-stu-id="a2269-126">Attack simulation training offers a subset of capabilities to E3 customers as a trial.</span></span> <span data-ttu-id="a2269-127">В пробном предложении содержится возможность использования полезной нагрузки Credential Harvest и возможность выбора обучающих опытом "Фишинг isA" или "Mass Market Phishing".</span><span class="sxs-lookup"><span data-stu-id="a2269-127">The trial offering contains the ability to use a Credential Harvest payload and the ability to select 'ISA Phishing' or 'Mass Market Phishing' training experiences.</span></span> <span data-ttu-id="a2269-128">Никакие другие возможности не являются частью пробного предложения E3.</span><span class="sxs-lookup"><span data-stu-id="a2269-128">No other capabilities are part of the E3 trial offering.</span></span>

## <a name="simulations"></a><span data-ttu-id="a2269-129">Моделирование</span><span class="sxs-lookup"><span data-stu-id="a2269-129">Simulations</span></span>

<span data-ttu-id="a2269-130">*Фишинг —* это общий термин для атак электронной почты, которые пытаются украсть конфиденциальные сведения в сообщениях, которые, как представляется, являются законными или доверенными отправителями.</span><span class="sxs-lookup"><span data-stu-id="a2269-130">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="a2269-131">*Фишинг является* частью подмножества методов, которые мы классифицировать как _социальные инженерии_.</span><span class="sxs-lookup"><span data-stu-id="a2269-131">*Phishing* is a part of a subset of techniques we classify as _social engineering_.</span></span>

<span data-ttu-id="a2269-132">В обучении моделированию атак доступны несколько типов методов социальной инженерии:</span><span class="sxs-lookup"><span data-stu-id="a2269-132">In Attack simulation training, multiple types of social engineering techniques are available:</span></span>

- <span data-ttu-id="a2269-133">**Сбор учетных** данных. Злоумышленник отправляет получателю сообщение с URL-адресом.</span><span class="sxs-lookup"><span data-stu-id="a2269-133">**Credential harvest**: An attacker sends the recipient a message that contains a URL.</span></span> <span data-ttu-id="a2269-134">Когда получатель щелкает URL-адрес, он передается на веб-сайт, на который обычно указывается диалоговое окно с запросом имени пользователя и пароля.</span><span class="sxs-lookup"><span data-stu-id="a2269-134">When the recipient clicks on the URL, they're taken to a website that typically shows a dialog box that asks the user for their username and password.</span></span> <span data-ttu-id="a2269-135">Как правило, для создания доверия к пользователю на странице назначения используется themed для представления известного веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="a2269-135">Typically, the destination page is themed to represent a well-known website in order to build trust in the user.</span></span>

- <span data-ttu-id="a2269-136">**Вложение** вредоносных программ. Злоумышленник отправляет получателю сообщение, содержаное вложение.</span><span class="sxs-lookup"><span data-stu-id="a2269-136">**Malware attachment**: An attacker sends the recipient a message that contains an attachment.</span></span> <span data-ttu-id="a2269-137">Когда получатель открывает вложение, произвольный код (например, макрос) запускается на устройстве пользователя, чтобы помочь злоумышленнику установить дополнительный код или закрепить себя.</span><span class="sxs-lookup"><span data-stu-id="a2269-137">When the recipient opens the attachment, arbitrary code (for example, a macro) is run on the user's device to help the attacker install additional code or further entrench themselves.</span></span>

- <span data-ttu-id="a2269-138">**Ссылка в приложении.** Это гибрид сбора учетных данных.</span><span class="sxs-lookup"><span data-stu-id="a2269-138">**Link in attachment**: This is a hybrid of a credential harvest.</span></span> <span data-ttu-id="a2269-139">Злоумышленник отправляет получателю сообщение, содержаное URL-адрес внутри вложения.</span><span class="sxs-lookup"><span data-stu-id="a2269-139">An attacker sends the recipient a message that contains a URL inside of an attachment.</span></span> <span data-ttu-id="a2269-140">Когда получатель открывает вложение и щелкает ПО URL-адресу, он передается на веб-сайт, который обычно показывает диалоговое окно, в которое пользователь спрашивает имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="a2269-140">When the recipient opens the attachment and clicks on the URL, they're taken to a website that typically shows a dialog box that asks the user for their username and password.</span></span> <span data-ttu-id="a2269-141">Как правило, для создания доверия к пользователю на странице назначения используется themed для представления известного веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="a2269-141">Typically, the destination page is themed to represent a well-known website in order to build trust in the user.</span></span>

- <span data-ttu-id="a2269-142">**Ссылка на** вредоносные программы: злоумышленник отправляет получателю сообщение, содержаное ссылку на вложение на известном сайте общего доступа к файлам (например, SharePoint Online или Dropbox).</span><span class="sxs-lookup"><span data-stu-id="a2269-142">**Link to malware**: An attacker sends the recipient a message that contains a link to an attachment on a well-known file sharing site (for example, SharePoint Online or Dropbox).</span></span> <span data-ttu-id="a2269-143">Когда получатель щелкает URL-адрес, открывается вложение и произвольный код (например, макрос) запускается на устройстве пользователя, чтобы помочь злоумышленнику установить дополнительный код или закрепить себя.</span><span class="sxs-lookup"><span data-stu-id="a2269-143">When the recipient clicks on the URL, the attachment opens and arbitrary code (for example, a macro) is run on the user's device to help the attacker install additional code or further entrench themselves.</span></span>

- <span data-ttu-id="a2269-144">**Url-адрес drive-by-url.** Злоумышленник отправляет получателю сообщения, содержавшие URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="a2269-144">**Drive-by-url**: An attacker sends the recipient a messages that contains a URL.</span></span> <span data-ttu-id="a2269-145">Когда получатель щелкает URL-адрес, он передается на веб-сайт, который пытается запустить фоновый код.</span><span class="sxs-lookup"><span data-stu-id="a2269-145">When the recipient clicks on the URL, they're taken to a website that tries to run background code.</span></span> <span data-ttu-id="a2269-146">Этот фоновый код пытается собрать сведения о получателе или развернуть произвольный код на своем устройстве.</span><span class="sxs-lookup"><span data-stu-id="a2269-146">This background code attempts to gather information about the recipient or deploy arbitrary code on their device.</span></span> <span data-ttu-id="a2269-147">Как правило, веб-сайт назначения — это хорошо известный веб-сайт, который был скомпрометирован или клон известного веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="a2269-147">Typically, the destination website is a well-known website that has been compromised or a clone of a well-known website.</span></span> <span data-ttu-id="a2269-148">Знакомство с веб-сайтом помогает убедить пользователя в том, что ссылка является безопасной для нажатия.</span><span class="sxs-lookup"><span data-stu-id="a2269-148">Familiarity with the website helps convince the user that the link is safe to click.</span></span> <span data-ttu-id="a2269-149">Этот метод также известен как атака _отверстия для поливка._</span><span class="sxs-lookup"><span data-stu-id="a2269-149">This technique is also known as a _watering hole attack_.</span></span>

> [!NOTE]
> <span data-ttu-id="a2269-150">Проверьте доступность смоделированных URL-адресов фишинга в поддерживаемых веб-браузерах перед использованием URL-адреса в фишинговой кампании.</span><span class="sxs-lookup"><span data-stu-id="a2269-150">Check the availability of the simulated phishing URL in your supported web browsers before you use the URL in a phishing campaign.</span></span> <span data-ttu-id="a2269-151">Хотя мы работаем со многими поставщиками репутации URL-адресов, чтобы всегда разрешал эти URL-адреса моделирования, у нас не всегда есть полный охват (например, Google Сейф Browsing).</span><span class="sxs-lookup"><span data-stu-id="a2269-151">While we work with many URL reputation vendors to always allow these simulation URLs, we don't always have full coverage (for example, Google Safe Browsing).</span></span> <span data-ttu-id="a2269-152">Большинство поставщиков предоставляют рекомендации, которые позволяют всегда разрешать определенные URL-адреса (например, <https://support.google.com/chrome/a/answer/7532419> ).</span><span class="sxs-lookup"><span data-stu-id="a2269-152">Most vendors provide guidance that allows you to always allow specific URLs (for example, <https://support.google.com/chrome/a/answer/7532419>).</span></span>

<span data-ttu-id="a2269-153">URL-адреса, используемые в обучении имитации атаки, описаны в следующем списке:</span><span class="sxs-lookup"><span data-stu-id="a2269-153">The URLs that are used by Attack simulation training are described in the following list:</span></span>

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

### <a name="create-a-simulation"></a><span data-ttu-id="a2269-154">Создание имитации</span><span class="sxs-lookup"><span data-stu-id="a2269-154">Create a simulation</span></span>

<span data-ttu-id="a2269-155">Инструкции по созданию и отправке нового моделирования см. в инструкции по имитации [фишинговой атаки.](attack-simulation-training.md)</span><span class="sxs-lookup"><span data-stu-id="a2269-155">For step by step instructions on how to create and send a new simulation, see [Simulate a phishing attack](attack-simulation-training.md).</span></span>

### <a name="create-a-payload"></a><span data-ttu-id="a2269-156">Создание полезной нагрузки</span><span class="sxs-lookup"><span data-stu-id="a2269-156">Create a payload</span></span>

<span data-ttu-id="a2269-157">Инструкции по созданию полезной нагрузки для использования в имитации см. в инструкции по созданию настраиваемой полезной нагрузки для обучения [имитации атаки.](attack-simulation-training-payloads.md)</span><span class="sxs-lookup"><span data-stu-id="a2269-157">For step by step instructions on how to create a payload for use within a simulation, see [Create a custom payload for Attack simulation training](attack-simulation-training-payloads.md).</span></span>

### <a name="gaining-insights"></a><span data-ttu-id="a2269-158">Получение информации</span><span class="sxs-lookup"><span data-stu-id="a2269-158">Gaining insights</span></span>

<span data-ttu-id="a2269-159">Инструкции по пошаговую информацию о том, как получить сведения с отчетами, см. в рублях [Gain insights through Attack simulation training.](attack-simulation-training-insights.md)</span><span class="sxs-lookup"><span data-stu-id="a2269-159">For step by step instructions on how to gain insights with reporting, see [Gain insights through Attack simulation training](attack-simulation-training-insights.md).</span></span>

> [!NOTE]
> <span data-ttu-id="a2269-160">Симулятор атаки использует Сейф Ссылки в Defender для Office 365 для безопасного отслеживания щелкающих данных для URL-адреса в сообщении полезной  нагрузки, которое отправляется целевым получателям фишинговой кампании, даже если включен параметр Не отслеживать щелчок пользователя в Сейф политиках ссылок.</span><span class="sxs-lookup"><span data-stu-id="a2269-160">Attack Simulator uses Safe Links in Defender for Office 365 to securely track click data for the URL in the payload message that's sent to targeted recipients of a phishing campaign, even if the **Do not track user clicks** setting in Safe Links policies is turned on.</span></span>
