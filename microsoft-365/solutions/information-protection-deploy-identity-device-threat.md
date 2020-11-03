---
title: Использование удостоверений, устройств и защиты от угроз для обеспечения конфиденциальности данных
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
description: Предотвращение нарушений персональных данных с помощью удостоверений, устройств и служб защиты от угроз Microsoft 365.
ms.openlocfilehash: 321b60efbdabe62b14502df4a16dd2dcec4b9cef
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847182"
---
# <a name="use-identity-device-and-threat-protection-for-data-privacy-regulation"></a><span data-ttu-id="3fe99-103">Использование удостоверений, устройств и защиты от угроз для обеспечения конфиденциальности данных</span><span class="sxs-lookup"><span data-stu-id="3fe99-103">Use identity, device, and threat protection for data privacy regulation</span></span>

<span data-ttu-id="3fe99-104">Microsoft 365 предоставляет ряд возможностей, которые могут использовать удостоверения, устройства и защиту от угроз, чтобы обеспечить соответствие нормативным требованиям, связанным с конфиденциальностью данных.</span><span class="sxs-lookup"><span data-stu-id="3fe99-104">Microsoft 365 provides a number of identity, device, and threat protection capabilities that organizations can employ to help comply with data privacy-related compliance regulations.</span></span> <span data-ttu-id="3fe99-105">В этой статье описываются требования к конфиденциальности данных в этих областях и приводятся сведения о дополнительных возможностях и службах Microsoft 365 со ссылками на дополнительные сведения, которые помогут вам устранить требования к реализации.</span><span class="sxs-lookup"><span data-stu-id="3fe99-105">This article describes what the data privacy regulations require in these areas and provides a listing of related Microsoft 365 features and services with links to more information to help you address implementation requirements.</span></span>

## <a name="how-identity-device-and-threat-protection-relate-to-data-privacy-regulation"></a><span data-ttu-id="3fe99-106">Как удостоверение, устройство и защита от угроз связаны с требованиями к конфиденциальности данных</span><span class="sxs-lookup"><span data-stu-id="3fe99-106">How identity, device, and threat protection relate to data privacy regulation</span></span>

<span data-ttu-id="3fe99-107">Несмотря на то, что нормативы по конфиденциальности данных различаются по их определению, суть того, что они вызывают, связана со статьей 5 (1) GDPR (f), которая указывает на следующее:</span><span class="sxs-lookup"><span data-stu-id="3fe99-107">While the data privacy regulations vary in their specificity, the essence of what they call for is embodied in the GDPR’s Article 5(1)(f), which states that:</span></span> 

- <span data-ttu-id="3fe99-108">Личные данные должны обрабатываться таким образом, чтобы обеспечить соответствующую безопасность персональных данных, включая защиту от незаконной или незаконному обработки и от случайных потерь, уничтожения или повреждений, используя подходящие технические или организационные меры ("целостность и конфиденциальность").</span><span class="sxs-lookup"><span data-stu-id="3fe99-108">Personal data shall be processed in a manner that ensures appropriate security of the personal data, including protection against unauthorized or unlawful processing and against accidental loss, destruction or damage, using appropriate technical or organizational measures ('integrity and confidentiality').</span></span>

<span data-ttu-id="3fe99-109">Так как личные нарушения данных часто возникают из-за нарушения безопасности администратора или учетной записи конечного пользователя, а также при несанкционированном доступе к системе.</span><span class="sxs-lookup"><span data-stu-id="3fe99-109">Because personal data breaches are often caused by administrative or end-user account compromise and malicious system access.</span></span> <span data-ttu-id="3fe99-110">Например, учетная запись администратора может привести к ексфилтратион номеров кредитных карт клиентов или других персональных данных.</span><span class="sxs-lookup"><span data-stu-id="3fe99-110">For example, an admin account hack can result in exfiltration of customer credit card numbers or other personal information.</span></span> <span data-ttu-id="3fe99-111">Все как правило, как правило, обеспечивается идентификация, устройство и защита от угроз, доступные в Microsoft 365, потенциально должны быть реализованы, что отражается в рейтинге соответствия требованиям, обнаруженном в диспетчере соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="3fe99-111">All the generally advisable identity, device, and threat protection available with Microsoft 365 potentially should be implemented, which will be reflected in your compliance score, found in Compliance Manager.</span></span>

## <a name="using-the-results-of-your-assessment-work-and-compliance-manager"></a><span data-ttu-id="3fe99-112">Использование результатов оценки работы и управления соответствием требованиям</span><span class="sxs-lookup"><span data-stu-id="3fe99-112">Using the results of your assessment work and Compliance Manager</span></span>

<span data-ttu-id="3fe99-113">Диспетчер соответствия требованиям включает удостоверения, устройства и защиту от угроз, используя следующие категории:</span><span class="sxs-lookup"><span data-stu-id="3fe99-113">Compliance Manager includes identity, device, and threat protection using these categories:</span></span>

- <span data-ttu-id="3fe99-114">Удостоверение соответствует категории **доступа к управлению**</span><span class="sxs-lookup"><span data-stu-id="3fe99-114">Identity corresponds to the **Control Access** category</span></span>
- <span data-ttu-id="3fe99-115">Устройство соответствует категории " **Управление устройствами** "</span><span class="sxs-lookup"><span data-stu-id="3fe99-115">Device corresponds to the **Manage Devices** category</span></span>
- <span data-ttu-id="3fe99-116">Защита от угроз соответствует категории " **Защита от угроз** "</span><span class="sxs-lookup"><span data-stu-id="3fe99-116">Threat protection corresponds to the **Protect Against Threats** category</span></span>
 
<span data-ttu-id="3fe99-117">Если они выбраны в нашем примере набора из четырех основных правил конфиденциальности данных, диспетчер соответствия требованиям определяет действия по улучшению 90, большинство из которых оцениваются как "27".</span><span class="sxs-lookup"><span data-stu-id="3fe99-117">If these are selected across our sample set of four major data privacy regulations, Compliance Manager specifies 90 improvement actions, most of which are scored a "27".</span></span> <span data-ttu-id="3fe99-118">Так как это большое число вызывается диспетчером соответствия требованиям для этих категорий, некоторые наиболее распространенные из них указаны в справочных целях.</span><span class="sxs-lookup"><span data-stu-id="3fe99-118">Since such a large number are called out by Compliance Manager for these categories, some of the more common ones are listed here, for reference.</span></span>

<span data-ttu-id="3fe99-119">Используйте [Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/) для удостоверения и категории **доступа к управлению** , с помощью которых можно выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="3fe99-119">Use [Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/) for identity and the **Control Access** category, with which you can:</span></span>

- <span data-ttu-id="3fe99-120">Реализация безвозвратной проверки подлинности (для предотвращения атак "мужчина в середине")</span><span class="sxs-lookup"><span data-stu-id="3fe99-120">Implement replay-resistant authentication (to prevent “Man in the middle” attacks)</span></span>
- <span data-ttu-id="3fe99-121">Заблокируйте традиционную проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="3fe99-121">Block legacy authentication.</span></span>
- <span data-ttu-id="3fe99-122">Настройте политики риска для пользователей и пользователей, которые входят в систему.</span><span class="sxs-lookup"><span data-stu-id="3fe99-122">Configure user risk and user sign-in risk policies.</span></span>
- <span data-ttu-id="3fe99-123">Включение условного доступа и многофакторной проверки подлинности (MFA) для администраторов и администраторов, не являющихся администраторами.</span><span class="sxs-lookup"><span data-stu-id="3fe99-123">Enable Conditional Access and multi-factor authentication (MFA) for admins and non-admins.</span></span>
- <span data-ttu-id="3fe99-124">Настройка и применение политик паролей.</span><span class="sxs-lookup"><span data-stu-id="3fe99-124">Configure and enforce password policies.</span></span>
- <span data-ttu-id="3fe99-125">Ограничьте доступ к привилегированным учетным записям с помощью службы управления удостоверениями Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3fe99-125">Restrict access to privileged accounts with Azure AD Privileged Identity Management.</span></span>
- <span data-ttu-id="3fe99-126">Отключить доступ при завершении работы.</span><span class="sxs-lookup"><span data-stu-id="3fe99-126">Disable access upon termination.</span></span>
- <span data-ttu-id="3fe99-127">Аудит и изменение состояния учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="3fe99-127">Audit user accounts and status changes.</span></span>
- <span data-ttu-id="3fe99-128">Изучите группу ролей и административные изменения.</span><span class="sxs-lookup"><span data-stu-id="3fe99-128">Review role group and administrative changes.</span></span>

<span data-ttu-id="3fe99-129">Используйте [Диспетчер конечных точек Майкрософт](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) для устройств и категорию **Manage Devices** , с помощью которой можно выполнять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="3fe99-129">Use [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) for devices and the **Manage Devices** category, with which you can:</span></span>

- <span data-ttu-id="3fe99-130">Блокировать взломанным и появляющиеся корневые мобильные устройства.</span><span class="sxs-lookup"><span data-stu-id="3fe99-130">Block jail broken and rooted mobile devices.</span></span>
- <span data-ttu-id="3fe99-131">Настройка Intune для управления мобильными устройствами.</span><span class="sxs-lookup"><span data-stu-id="3fe99-131">Configure Intune for mobile device management.</span></span>
- <span data-ttu-id="3fe99-132">Создание политик соответствия требованиям для устройств с Android, iOS, macOS и Windows.</span><span class="sxs-lookup"><span data-stu-id="3fe99-132">Create compliance policies for Android, iOS, macOS and Windows devices.</span></span>
- <span data-ttu-id="3fe99-133">Создайте профиль конфигурации устройства для устройств с Android, iOS, macOS и Windows.</span><span class="sxs-lookup"><span data-stu-id="3fe99-133">Create a device configuration profile for Android, iOS, macOS and Windows devices.</span></span>
- <span data-ttu-id="3fe99-134">Создайте политики защиты приложений для iOS и Windows.</span><span class="sxs-lookup"><span data-stu-id="3fe99-134">Create app protection policies for iOS and Windows.</span></span>
- <span data-ttu-id="3fe99-135">Скрытие информации с экрана блокировки.</span><span class="sxs-lookup"><span data-stu-id="3fe99-135">Conceal information with lock screen.</span></span>
- <span data-ttu-id="3fe99-136">Реализуйте политики паролей для мобильных устройств.</span><span class="sxs-lookup"><span data-stu-id="3fe99-136">Implement password policies for mobile devices.</span></span>
- <span data-ttu-id="3fe99-137">Потребовать, чтобы мобильные устройства блокировались после неактивности.</span><span class="sxs-lookup"><span data-stu-id="3fe99-137">Require mobile devices to lock upon inactivity.</span></span>
- <span data-ttu-id="3fe99-138">Потребовать от мобильных устройств очистки при сбоях нескольких входов.</span><span class="sxs-lookup"><span data-stu-id="3fe99-138">Require mobile devices to wipe on multiple sign-in failures.</span></span>

<span data-ttu-id="3fe99-139">Используйте [Exchange Online Protection и защитник Майкрософт для Office 365](../security/office-365-security/office-365-atp.md) для категории **Защита от угроз** , с помощью которой можно выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="3fe99-139">Use [Exchange Online Protection and Microsoft Defender for Office 365](../security/office-365-security/office-365-atp.md) for the **Protect Against Threats** category, with which you can:</span></span>

- <span data-ttu-id="3fe99-140">Включите проверку подлинности отправителей (SPF, DMARC и DKIM).</span><span class="sxs-lookup"><span data-stu-id="3fe99-140">Enable sender authentication (SPF, DMARC and DKIM).</span></span>
- <span data-ttu-id="3fe99-141">Настройте защитник Майкрософт для политик защиты от фишинга в Office 365.</span><span class="sxs-lookup"><span data-stu-id="3fe99-141">Set up Microsoft Defender for Office 365 anti-phishing policies.</span></span>
- <span data-ttu-id="3fe99-142">Реализуйте безопасные вложения.</span><span class="sxs-lookup"><span data-stu-id="3fe99-142">Implement Safe Attachments.</span></span>
- <span data-ttu-id="3fe99-143">Реализуйте безопасные ссылки.</span><span class="sxs-lookup"><span data-stu-id="3fe99-143">Implement Safe Links.</span></span>
- <span data-ttu-id="3fe99-144">Внедрение политик обнаружения и ответа на вредоносные программы.</span><span class="sxs-lookup"><span data-stu-id="3fe99-144">Implement malware detection and response policies.</span></span>
- <span data-ttu-id="3fe99-145">Реализуйте политики исходящей и входящей нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="3fe99-145">Implement outbound and inbound spam policies.</span></span>

### <a name="references"></a><span data-ttu-id="3fe99-146">Содержит</span><span class="sxs-lookup"><span data-stu-id="3fe99-146">References:</span></span>

- [<span data-ttu-id="3fe99-147">Основные политики доступа для удостоверений и устройств</span><span class="sxs-lookup"><span data-stu-id="3fe99-147">Common identity and device access policies</span></span>](../security/office-365-security/identity-access-policies.md)
- [<span data-ttu-id="3fe99-148">Защита от угроз в Office 365</span><span class="sxs-lookup"><span data-stu-id="3fe99-148">Protect against threats in Office 365</span></span>](https://support.office.com/article/protect-against-threats-in-office-365-b10023f6-f30f-45d3-b3ad-b71aa4aa0d58)
- [<span data-ttu-id="3fe99-149">Безопасные вложения</span><span class="sxs-lookup"><span data-stu-id="3fe99-149">Safe Attachments</span></span>](../security/office-365-security/atp-safe-attachments.md)
- [<span data-ttu-id="3fe99-150">Безопасные ссылки</span><span class="sxs-lookup"><span data-stu-id="3fe99-150">Safe Links</span></span>](../security/office-365-security/atp-safe-links.md)
- [<span data-ttu-id="3fe99-151">Безопасные документы</span><span class="sxs-lookup"><span data-stu-id="3fe99-151">Safe Documents</span></span>](../security/office-365-security/safe-docs.md)
