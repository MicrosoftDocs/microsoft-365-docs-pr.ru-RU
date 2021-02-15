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
description: Предотвращение нарушений безопасности персональных данных с помощью служб идентификации, устройств и защиты от угроз в Microsoft 365.
ms.openlocfilehash: 321b60efbdabe62b14502df4a16dd2dcec4b9cef
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847182"
---
# <a name="use-identity-device-and-threat-protection-for-data-privacy-regulation"></a><span data-ttu-id="9e53b-103">Использование удостоверений, устройств и защиты от угроз для регулирования конфиденциальности данных</span><span class="sxs-lookup"><span data-stu-id="9e53b-103">Use identity, device, and threat protection for data privacy regulation</span></span>

<span data-ttu-id="9e53b-104">Microsoft 365 предоставляет ряд возможностей защиты от угроз, связанных с идентификацией, устройствами и угрозами, которые организации могут использовать для обеспечения соответствия нормативным требованиям, связанным с конфиденциальностью данных.</span><span class="sxs-lookup"><span data-stu-id="9e53b-104">Microsoft 365 provides a number of identity, device, and threat protection capabilities that organizations can employ to help comply with data privacy-related compliance regulations.</span></span> <span data-ttu-id="9e53b-105">В этой статье описываются требования нормативных требований к конфиденциальности данных в этих областях, а также приводится список связанных функций и служб Microsoft 365 со ссылками на дополнительные сведения, которые помогут вам реализации требований.</span><span class="sxs-lookup"><span data-stu-id="9e53b-105">This article describes what the data privacy regulations require in these areas and provides a listing of related Microsoft 365 features and services with links to more information to help you address implementation requirements.</span></span>

## <a name="how-identity-device-and-threat-protection-relate-to-data-privacy-regulation"></a><span data-ttu-id="9e53b-106">Как защита удостоверений, устройств и угроз связана с нормативом конфиденциальности данных</span><span class="sxs-lookup"><span data-stu-id="9e53b-106">How identity, device, and threat protection relate to data privacy regulation</span></span>

<span data-ttu-id="9e53b-107">Хотя нормативы конфиденциальности данных отличаются в зависимости от их специфичности, суть их вызова заключается в статье 5(1)(f) GDPR, в которой говорится, что:</span><span class="sxs-lookup"><span data-stu-id="9e53b-107">While the data privacy regulations vary in their specificity, the essence of what they call for is embodied in the GDPR’s Article 5(1)(f), which states that:</span></span> 

- <span data-ttu-id="9e53b-108">Персональные данные должны обрабатываться таким образом, чтобы обеспечить соответствующую безопасность персональных данных, включая защиту от несанкционированной или незаконной обработки, а также от случайной потери, уничтожения или повреждения, используя соответствующие технические или организационные меры ("целостность и конфиденциальность").</span><span class="sxs-lookup"><span data-stu-id="9e53b-108">Personal data shall be processed in a manner that ensures appropriate security of the personal data, including protection against unauthorized or unlawful processing and against accidental loss, destruction or damage, using appropriate technical or organizational measures ('integrity and confidentiality').</span></span>

<span data-ttu-id="9e53b-109">Поскольку нарушения безопасности персональных данных часто вызваны компрометативом учетной записи администратора или пользователя и вредоносным доступом к системе.</span><span class="sxs-lookup"><span data-stu-id="9e53b-109">Because personal data breaches are often caused by administrative or end-user account compromise and malicious system access.</span></span> <span data-ttu-id="9e53b-110">Например, взлом учетной записи администратора может привести к вымылению номеров кредитных карт клиентов или других персональных данных.</span><span class="sxs-lookup"><span data-stu-id="9e53b-110">For example, an admin account hack can result in exfiltration of customer credit card numbers or other personal information.</span></span> <span data-ttu-id="9e53b-111">В диспетчере соответствия требованиям могут быть реализованы все общедоступные удостоверения, устройства и средства защиты от угроз, доступные в Microsoft 365, что будет отражено в вашем показателе соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="9e53b-111">All the generally advisable identity, device, and threat protection available with Microsoft 365 potentially should be implemented, which will be reflected in your compliance score, found in Compliance Manager.</span></span>

## <a name="using-the-results-of-your-assessment-work-and-compliance-manager"></a><span data-ttu-id="9e53b-112">Использование результатов оценки и диспетчера соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="9e53b-112">Using the results of your assessment work and Compliance Manager</span></span>

<span data-ttu-id="9e53b-113">Диспетчер соответствия требованиям включает удостоверения, устройства и защиту от угроз, используя следующие категории:</span><span class="sxs-lookup"><span data-stu-id="9e53b-113">Compliance Manager includes identity, device, and threat protection using these categories:</span></span>

- <span data-ttu-id="9e53b-114">Удостоверение соответствует категории доступа **к** контрольным данным</span><span class="sxs-lookup"><span data-stu-id="9e53b-114">Identity corresponds to the **Control Access** category</span></span>
- <span data-ttu-id="9e53b-115">Устройство соответствует категории **"Управление устройствами"**</span><span class="sxs-lookup"><span data-stu-id="9e53b-115">Device corresponds to the **Manage Devices** category</span></span>
- <span data-ttu-id="9e53b-116">Защита от угроз соответствует категории "Защита от **угроз"**</span><span class="sxs-lookup"><span data-stu-id="9e53b-116">Threat protection corresponds to the **Protect Against Threats** category</span></span>
 
<span data-ttu-id="9e53b-117">Если они выбраны в нашем примере набора из четырех основных нормативов конфиденциальности данных, диспетчер соответствия требованиям указывает 90 действий по улучшению, большинство из которых имеют "27".</span><span class="sxs-lookup"><span data-stu-id="9e53b-117">If these are selected across our sample set of four major data privacy regulations, Compliance Manager specifies 90 improvement actions, most of which are scored a "27".</span></span> <span data-ttu-id="9e53b-118">Так как такое большое количество вызвано диспетчером соответствия требованиям для этих категорий, некоторые из наиболее распространенных из них перечислены здесь для справки.</span><span class="sxs-lookup"><span data-stu-id="9e53b-118">Since such a large number are called out by Compliance Manager for these categories, some of the more common ones are listed here, for reference.</span></span>

<span data-ttu-id="9e53b-119">Используйте [Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/) для удостоверений и категории доступа к управлению, с помощью которой вы можете: </span><span class="sxs-lookup"><span data-stu-id="9e53b-119">Use [Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/) for identity and the **Control Access** category, with which you can:</span></span>

- <span data-ttu-id="9e53b-120">Реализация проверки подлинности с устойчивостью к повтору (для предотвращения атак "Человек в середине")</span><span class="sxs-lookup"><span data-stu-id="9e53b-120">Implement replay-resistant authentication (to prevent “Man in the middle” attacks)</span></span>
- <span data-ttu-id="9e53b-121">Заблокируйте традиционную проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="9e53b-121">Block legacy authentication.</span></span>
- <span data-ttu-id="9e53b-122">Настройте политики риска для пользователей и вход в нее.</span><span class="sxs-lookup"><span data-stu-id="9e53b-122">Configure user risk and user sign-in risk policies.</span></span>
- <span data-ttu-id="9e53b-123">Включить условный доступ и многофакторную проверку подлинности (MFA) для администраторов и других администраторов.</span><span class="sxs-lookup"><span data-stu-id="9e53b-123">Enable Conditional Access and multi-factor authentication (MFA) for admins and non-admins.</span></span>
- <span data-ttu-id="9e53b-124">Настройка и принудительное выполнение политик паролей.</span><span class="sxs-lookup"><span data-stu-id="9e53b-124">Configure and enforce password policies.</span></span>
- <span data-ttu-id="9e53b-125">Ограничение доступа к привилегированным учетным записям с помощью Azure AD Privileged Identity Management.</span><span class="sxs-lookup"><span data-stu-id="9e53b-125">Restrict access to privileged accounts with Azure AD Privileged Identity Management.</span></span>
- <span data-ttu-id="9e53b-126">Отключать доступ после завершения работы.</span><span class="sxs-lookup"><span data-stu-id="9e53b-126">Disable access upon termination.</span></span>
- <span data-ttu-id="9e53b-127">Аудит учетных записей пользователей и изменений состояния.</span><span class="sxs-lookup"><span data-stu-id="9e53b-127">Audit user accounts and status changes.</span></span>
- <span data-ttu-id="9e53b-128">Просмотрите группу ролей и административные изменения.</span><span class="sxs-lookup"><span data-stu-id="9e53b-128">Review role group and administrative changes.</span></span>

<span data-ttu-id="9e53b-129">Используйте [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) для устройств и категорию **"Управление** устройствами", с помощью которой вы можете:</span><span class="sxs-lookup"><span data-stu-id="9e53b-129">Use [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) for devices and the **Manage Devices** category, with which you can:</span></span>

- <span data-ttu-id="9e53b-130">Блокировка заблокированных и корневых мобильных устройств.</span><span class="sxs-lookup"><span data-stu-id="9e53b-130">Block jail broken and rooted mobile devices.</span></span>
- <span data-ttu-id="9e53b-131">Настройка Intune для управления мобильными устройствами.</span><span class="sxs-lookup"><span data-stu-id="9e53b-131">Configure Intune for mobile device management.</span></span>
- <span data-ttu-id="9e53b-132">Создайте политики соответствия требованиям для устройств с Android, iOS, macOS и Windows.</span><span class="sxs-lookup"><span data-stu-id="9e53b-132">Create compliance policies for Android, iOS, macOS and Windows devices.</span></span>
- <span data-ttu-id="9e53b-133">Создайте профиль конфигурации устройства для устройств с Android, iOS, macOS и Windows.</span><span class="sxs-lookup"><span data-stu-id="9e53b-133">Create a device configuration profile for Android, iOS, macOS and Windows devices.</span></span>
- <span data-ttu-id="9e53b-134">Создайте политики защиты приложений для iOS и Windows.</span><span class="sxs-lookup"><span data-stu-id="9e53b-134">Create app protection policies for iOS and Windows.</span></span>
- <span data-ttu-id="9e53b-135">Сокрытие информации с помощью экрана блокировки.</span><span class="sxs-lookup"><span data-stu-id="9e53b-135">Conceal information with lock screen.</span></span>
- <span data-ttu-id="9e53b-136">Внедрить политики паролей для мобильных устройств.</span><span class="sxs-lookup"><span data-stu-id="9e53b-136">Implement password policies for mobile devices.</span></span>
- <span data-ttu-id="9e53b-137">Требовать от мобильных устройств блокировки бездействия.</span><span class="sxs-lookup"><span data-stu-id="9e53b-137">Require mobile devices to lock upon inactivity.</span></span>
- <span data-ttu-id="9e53b-138">Требовать от мобильных устройств стирать несколько неудачных входов.</span><span class="sxs-lookup"><span data-stu-id="9e53b-138">Require mobile devices to wipe on multiple sign-in failures.</span></span>

<span data-ttu-id="9e53b-139">Используйте [Exchange Online Protection и Microsoft Defender для Office 365](../security/office-365-security/office-365-atp.md) в категории **"Защита** от угроз", с помощью которой вы можете:</span><span class="sxs-lookup"><span data-stu-id="9e53b-139">Use [Exchange Online Protection and Microsoft Defender for Office 365](../security/office-365-security/office-365-atp.md) for the **Protect Against Threats** category, with which you can:</span></span>

- <span data-ttu-id="9e53b-140">Включить проверку подлинности отправитель (SPF, DMARC и DKIM).</span><span class="sxs-lookup"><span data-stu-id="9e53b-140">Enable sender authentication (SPF, DMARC and DKIM).</span></span>
- <span data-ttu-id="9e53b-141">Настройка Microsoft Defender для политик защиты от фишинга в Office 365.</span><span class="sxs-lookup"><span data-stu-id="9e53b-141">Set up Microsoft Defender for Office 365 anti-phishing policies.</span></span>
- <span data-ttu-id="9e53b-142">Реализация безопасных вложений.</span><span class="sxs-lookup"><span data-stu-id="9e53b-142">Implement Safe Attachments.</span></span>
- <span data-ttu-id="9e53b-143">Реализация безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="9e53b-143">Implement Safe Links.</span></span>
- <span data-ttu-id="9e53b-144">Внедрить политики обнаружения вредоносных программ и реагирования на них.</span><span class="sxs-lookup"><span data-stu-id="9e53b-144">Implement malware detection and response policies.</span></span>
- <span data-ttu-id="9e53b-145">Реализуют политики нежелательной почты для исходящие и входящие сообщения.</span><span class="sxs-lookup"><span data-stu-id="9e53b-145">Implement outbound and inbound spam policies.</span></span>

### <a name="references"></a><span data-ttu-id="9e53b-146">Ссылки:</span><span class="sxs-lookup"><span data-stu-id="9e53b-146">References:</span></span>

- [<span data-ttu-id="9e53b-147">Основные политики доступа для удостоверений и устройств</span><span class="sxs-lookup"><span data-stu-id="9e53b-147">Common identity and device access policies</span></span>](../security/office-365-security/identity-access-policies.md)
- [<span data-ttu-id="9e53b-148">Защита от угроз в Office 365</span><span class="sxs-lookup"><span data-stu-id="9e53b-148">Protect against threats in Office 365</span></span>](https://support.office.com/article/protect-against-threats-in-office-365-b10023f6-f30f-45d3-b3ad-b71aa4aa0d58)
- [<span data-ttu-id="9e53b-149">Безопасные вложения</span><span class="sxs-lookup"><span data-stu-id="9e53b-149">Safe Attachments</span></span>](../security/office-365-security/atp-safe-attachments.md)
- [<span data-ttu-id="9e53b-150">Безопасные ссылки</span><span class="sxs-lookup"><span data-stu-id="9e53b-150">Safe Links</span></span>](../security/office-365-security/atp-safe-links.md)
- [<span data-ttu-id="9e53b-151">Безопасные документы</span><span class="sxs-lookup"><span data-stu-id="9e53b-151">Safe Documents</span></span>](../security/office-365-security/safe-docs.md)
