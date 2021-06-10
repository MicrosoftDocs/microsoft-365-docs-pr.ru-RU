---
title: Использование удостоверений, устройств и защиты от угроз для регулирования конфиденциальности данных
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: Предотвращение нарушений персональных данных с помощью служб идентификации, устройств и защиты от Microsoft 365.
ms.openlocfilehash: 5e08ef574e199769e572b3836b3323dc88fc4bbd
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199469"
---
# <a name="use-identity-device-and-threat-protection-for-data-privacy-regulation"></a><span data-ttu-id="87ced-103">Использование удостоверений, устройств и защиты от угроз для регулирования конфиденциальности данных</span><span class="sxs-lookup"><span data-stu-id="87ced-103">Use identity, device, and threat protection for data privacy regulation</span></span>

<span data-ttu-id="87ced-104">Microsoft 365 предоставляет ряд возможностей для защиты от личных данных, устройств и угроз, которые организации могут использовать для обеспечения соответствия требованиям, связанным с конфиденциальностью данных.</span><span class="sxs-lookup"><span data-stu-id="87ced-104">Microsoft 365 provides a number of identity, device, and threat protection capabilities that organizations can employ to help comply with data privacy-related compliance regulations.</span></span> <span data-ttu-id="87ced-105">В этой статье описываются требования к конфиденциальности данных в этих областях и содержится список связанных Microsoft 365 и служб со ссылками на дополнительные сведения, которые помогут вам решить вопросы реализации.</span><span class="sxs-lookup"><span data-stu-id="87ced-105">This article describes what the data privacy regulations require in these areas and provides a listing of related Microsoft 365 features and services with links to more information to help you address implementation requirements.</span></span>

## <a name="how-identity-device-and-threat-protection-relate-to-data-privacy-regulation"></a><span data-ttu-id="87ced-106">Отношение удостоверений, устройств и защиты от угроз к регулированию конфиденциальности данных</span><span class="sxs-lookup"><span data-stu-id="87ced-106">How identity, device, and threat protection relate to data privacy regulation</span></span>

<span data-ttu-id="87ced-107">Хотя правила конфиденциальности данных различаются по своей специфике, суть того, к чему они призывают, воплощена в статье 5(1) (f) GDPR, в которой говорится, что:</span><span class="sxs-lookup"><span data-stu-id="87ced-107">While the data privacy regulations vary in their specificity, the essence of what they call for is embodied in the GDPR’s Article 5(1)(f), which states that:</span></span>

- <span data-ttu-id="87ced-108">Персональные данные обрабатываются таким образом, чтобы обеспечить соответствующую безопасность персональных данных, включая защиту от несанкционированной или незаконной обработки, а также от случайных потерь, разрушений или повреждений, используя соответствующие технические или организационные меры ("целостность и конфиденциальность").</span><span class="sxs-lookup"><span data-stu-id="87ced-108">Personal data shall be processed in a manner that ensures appropriate security of the personal data, including protection against unauthorized or unlawful processing and against accidental loss, destruction or damage, using appropriate technical or organizational measures ('integrity and confidentiality').</span></span>

<span data-ttu-id="87ced-109">Так как нарушения персональных данных часто вызваны компрометативом учетной записи администратора или пользователя и вредоносным доступом к системе.</span><span class="sxs-lookup"><span data-stu-id="87ced-109">Because personal data breaches are often caused by administrative or end-user account compromise and malicious system access.</span></span> <span data-ttu-id="87ced-110">Например, взлом учетной записи администратора может привести к эксфильтрации номеров кредитных карт клиентов или других персональных данных.</span><span class="sxs-lookup"><span data-stu-id="87ced-110">For example, an admin account hack can result in exfiltration of customer credit card numbers or other personal information.</span></span> <span data-ttu-id="87ced-111">Все, как правило, рекомендуется удостоверение, устройство и защиту от угроз, доступные с помощью Microsoft 365 потенциально должны быть реализованы, что будет отражено в вашей оценке соответствия требованиям, найденной в диспетчере соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="87ced-111">All the generally advisable identity, device, and threat protection available with Microsoft 365 potentially should be implemented, which will be reflected in your compliance score, found in Compliance Manager.</span></span>

## <a name="using-the-results-of-your-assessment-work-and-compliance-manager"></a><span data-ttu-id="87ced-112">Использование результатов работы по оценке и диспетчер соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="87ced-112">Using the results of your assessment work and Compliance Manager</span></span>

<span data-ttu-id="87ced-113">Диспетчер соответствия требованиям включает в себя удостоверения, устройства и защиту от угроз с помощью этих категорий:</span><span class="sxs-lookup"><span data-stu-id="87ced-113">Compliance Manager includes identity, device, and threat protection using these categories:</span></span>

- <span data-ttu-id="87ced-114">Удостоверение соответствует категории **Контрольный** доступ</span><span class="sxs-lookup"><span data-stu-id="87ced-114">Identity corresponds to the **Control Access** category</span></span>
- <span data-ttu-id="87ced-115">Устройство соответствует категории **Manage Devices**</span><span class="sxs-lookup"><span data-stu-id="87ced-115">Device corresponds to the **Manage Devices** category</span></span>
- <span data-ttu-id="87ced-116">Защита от угроз соответствует категории **Protect Against Threats**</span><span class="sxs-lookup"><span data-stu-id="87ced-116">Threat protection corresponds to the **Protect Against Threats** category</span></span>
 
<span data-ttu-id="87ced-117">Если они выбраны в нашем примере из четырех основных правил конфиденциальности данных, диспетчер соответствия требованиям указывает 90 действий по улучшению, большинство из которых засчет "27".</span><span class="sxs-lookup"><span data-stu-id="87ced-117">If these are selected across our sample set of four major data privacy regulations, Compliance Manager specifies 90 improvement actions, most of which are scored a "27".</span></span> <span data-ttu-id="87ced-118">Так как такое большое число вызвано диспетчером соответствия требованиям для этих категорий, некоторые из наиболее распространенных из них перечислены здесь, для справки.</span><span class="sxs-lookup"><span data-stu-id="87ced-118">Since such a large number are called out by Compliance Manager for these categories, some of the more common ones are listed here, for reference.</span></span>

<span data-ttu-id="87ced-119">Используйте [Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/) для удостоверений и категории **Control Access,** с помощью которой можно:</span><span class="sxs-lookup"><span data-stu-id="87ced-119">Use [Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/) for identity and the **Control Access** category, with which you can:</span></span>

- <span data-ttu-id="87ced-120">Реализация проверки подлинности с устойчивостью к повторам (чтобы предотвратить атаки "Человек в центре"</span><span class="sxs-lookup"><span data-stu-id="87ced-120">Implement replay-resistant authentication (to prevent “Man in the middle” attacks)</span></span>
- <span data-ttu-id="87ced-121">Заблокируйте традиционную проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="87ced-121">Block legacy authentication.</span></span>
- <span data-ttu-id="87ced-122">Настройка политик риска для пользователей и входных данных.</span><span class="sxs-lookup"><span data-stu-id="87ced-122">Configure user risk and user sign-in risk policies.</span></span>
- <span data-ttu-id="87ced-123">Включить условный доступ и многофакторную проверку подлинности (MFA) для администраторов и не-администраторов.</span><span class="sxs-lookup"><span data-stu-id="87ced-123">Enable Conditional Access and multi-factor authentication (MFA) for admins and non-admins.</span></span>
- <span data-ttu-id="87ced-124">Настройка и соблюдение политик паролей.</span><span class="sxs-lookup"><span data-stu-id="87ced-124">Configure and enforce password policies.</span></span>
- <span data-ttu-id="87ced-125">Ограничение доступа к привилегированным учетным записям с помощью Azure AD управление привилегированными пользователями.</span><span class="sxs-lookup"><span data-stu-id="87ced-125">Restrict access to privileged accounts with Azure AD Privileged Identity Management.</span></span>
- <span data-ttu-id="87ced-126">Отключение доступа после завершения.</span><span class="sxs-lookup"><span data-stu-id="87ced-126">Disable access upon termination.</span></span>
- <span data-ttu-id="87ced-127">Аудит учетных записей пользователей и изменение состояния.</span><span class="sxs-lookup"><span data-stu-id="87ced-127">Audit user accounts and status changes.</span></span>
- <span data-ttu-id="87ced-128">Просмотр групп ролей и административных изменений.</span><span class="sxs-lookup"><span data-stu-id="87ced-128">Review role group and administrative changes.</span></span>

<span data-ttu-id="87ced-129">Используйте [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) для устройств и категории **Manage Devices,** с помощью которых можно:</span><span class="sxs-lookup"><span data-stu-id="87ced-129">Use [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) for devices and the **Manage Devices** category, with which you can:</span></span>

- <span data-ttu-id="87ced-130">Блокировка разбитых и корневых мобильных устройств.</span><span class="sxs-lookup"><span data-stu-id="87ced-130">Block jail broken and rooted mobile devices.</span></span>
- <span data-ttu-id="87ced-131">Настройка Intune для управления мобильными устройствами.</span><span class="sxs-lookup"><span data-stu-id="87ced-131">Configure Intune for mobile device management.</span></span>
- <span data-ttu-id="87ced-132">Создание политик соответствия требованиям для android, iOS, macOS и Windows устройств.</span><span class="sxs-lookup"><span data-stu-id="87ced-132">Create compliance policies for Android, iOS, macOS and Windows devices.</span></span>
- <span data-ttu-id="87ced-133">Создайте профиль конфигурации устройств для устройств Android, iOS, macOS и Windows устройств.</span><span class="sxs-lookup"><span data-stu-id="87ced-133">Create a device configuration profile for Android, iOS, macOS and Windows devices.</span></span>
- <span data-ttu-id="87ced-134">Создание политик защиты приложений для iOS и Windows.</span><span class="sxs-lookup"><span data-stu-id="87ced-134">Create app protection policies for iOS and Windows.</span></span>
- <span data-ttu-id="87ced-135">Сокрытие сведений с помощью экрана блокировки.</span><span class="sxs-lookup"><span data-stu-id="87ced-135">Conceal information with lock screen.</span></span>
- <span data-ttu-id="87ced-136">Реализация политик паролей для мобильных устройств.</span><span class="sxs-lookup"><span data-stu-id="87ced-136">Implement password policies for mobile devices.</span></span>
- <span data-ttu-id="87ced-137">Требовать от мобильных устройств блокировки неактивности.</span><span class="sxs-lookup"><span data-stu-id="87ced-137">Require mobile devices to lock upon inactivity.</span></span>
- <span data-ttu-id="87ced-138">Требуется, чтобы мобильные устройства стирались при нескольких сбоях при входе.</span><span class="sxs-lookup"><span data-stu-id="87ced-138">Require mobile devices to wipe on multiple sign-in failures.</span></span>

<span data-ttu-id="87ced-139">Используйте [Exchange Online Protection и Microsoft Defender для Office 365](../security/office-365-security/defender-for-office-365.md) категории Protect Against **Threats,** с помощью которых можно:</span><span class="sxs-lookup"><span data-stu-id="87ced-139">Use [Exchange Online Protection and Microsoft Defender for Office 365](../security/office-365-security/defender-for-office-365.md) for the **Protect Against Threats** category, with which you can:</span></span>

- <span data-ttu-id="87ced-140">Включить проверку подлинности отправитель (SPF, DMARC и DKIM).</span><span class="sxs-lookup"><span data-stu-id="87ced-140">Enable sender authentication (SPF, DMARC and DKIM).</span></span>
- <span data-ttu-id="87ced-141">Настройка Microsoft Defender для Office 365 политик защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="87ced-141">Set up Microsoft Defender for Office 365 anti-phishing policies.</span></span>
- <span data-ttu-id="87ced-142">Реализация Сейф вложений.</span><span class="sxs-lookup"><span data-stu-id="87ced-142">Implement Safe Attachments.</span></span>
- <span data-ttu-id="87ced-143">Реализация Сейф ссылки.</span><span class="sxs-lookup"><span data-stu-id="87ced-143">Implement Safe Links.</span></span>
- <span data-ttu-id="87ced-144">Реализация политик обнаружения вредоносных программ и ответных действий.</span><span class="sxs-lookup"><span data-stu-id="87ced-144">Implement malware detection and response policies.</span></span>
- <span data-ttu-id="87ced-145">Реализация политик исходящие и входящие нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="87ced-145">Implement outbound and inbound spam policies.</span></span>

### <a name="references"></a><span data-ttu-id="87ced-146">Ссылки:</span><span class="sxs-lookup"><span data-stu-id="87ced-146">References:</span></span>

- [<span data-ttu-id="87ced-147">Основные политики доступа для удостоверений и устройств</span><span class="sxs-lookup"><span data-stu-id="87ced-147">Common identity and device access policies</span></span>](../security/office-365-security/identity-access-policies.md)
- [<span data-ttu-id="87ced-148">Защита от угроз в Office 365</span><span class="sxs-lookup"><span data-stu-id="87ced-148">Protect against threats in Office 365</span></span>](https://support.office.com/article/protect-against-threats-in-office-365-b10023f6-f30f-45d3-b3ad-b71aa4aa0d58)
- [<span data-ttu-id="87ced-149">Безопасные вложения</span><span class="sxs-lookup"><span data-stu-id="87ced-149">Safe Attachments</span></span>](../security/office-365-security/safe-attachments.md)
- [<span data-ttu-id="87ced-150">Безопасные ссылки</span><span class="sxs-lookup"><span data-stu-id="87ced-150">Safe Links</span></span>](../security/office-365-security/safe-links.md)
- [<span data-ttu-id="87ced-151">Безопасные документы</span><span class="sxs-lookup"><span data-stu-id="87ced-151">Safe Documents</span></span>](../security/office-365-security/safe-docs.md)
