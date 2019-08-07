---
title: Управление мобильными устройствами для Contoso
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/13/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Общие сведения о том, как Contoso использует Intune в Microsoft 365 корпоративный для управления устройствами и работающими на них приложениями.
ms.openlocfilehash: 9f3db160b01a54afa3457703b0333be1ff3a02ec
ms.sourcegitcommit: d9b462e035416bfa4b3d42467902c75859c55381
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/01/2019
ms.locfileid: "36054991"
---
# <a name="mobile-device-management-for-contoso"></a><span data-ttu-id="4db1e-103">Управление мобильными устройствами для Contoso</span><span class="sxs-lookup"><span data-stu-id="4db1e-103">Mobile device management for Contoso</span></span>

<span data-ttu-id="4db1e-104">**Сводка.** Общие сведения о том, как Contoso использует Intune в Microsoft 365 корпоративный для управления устройствами и работающими на них приложениями.</span><span class="sxs-lookup"><span data-stu-id="4db1e-104">**Summary:** Understand how Contoso uses EMS in Microsoft 365 Enterprise to manage its devices and the apps that run on them.</span></span>

<span data-ttu-id="4db1e-105">Microsoft 365 корпоративный содержит Microsoft Intune и набор служб Azure для поддержки мобильных устройств, управления приложениями и обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="4db1e-105">Enterprise Mobility + Security (EMS) in Microsoft 365 Enterprise consists of Microsoft Intune and a set of Azure services to support mobile device and application management and security.</span></span>

<span data-ttu-id="4db1e-p101">В Contoso есть много сотрудников с мобильными устройствами. Некоторые из них имеют офисы в расположениях Contoso, а некоторые — нет. Для Contoso требуется способ обеспечения производительности сотрудников с поддержкой безопасности устройств, данных Contoso на этих устройствах и работы приложений.</span><span class="sxs-lookup"><span data-stu-id="4db1e-p101">Contoso has many mobile-enabled employees, some of which have offices in Contoso locations and some of which have no offices. Contoso needed a way to enable employee productivity but keep the devices, the Contoso data stored on those devices, and application behavior secure.</span></span>

## <a name="plan"></a><span data-ttu-id="4db1e-108">Планирование</span><span class="sxs-lookup"><span data-stu-id="4db1e-108">Plan</span></span>

<span data-ttu-id="4db1e-109">Ранее при анализе управления мобильными устройствами для Microsoft 365 корпоративный были определены следующие случаи использования Intune в Contoso:</span><span class="sxs-lookup"><span data-stu-id="4db1e-109">Early in the analysis of mobile device management for Microsoft 365 Enterprise, Contoso identified the following Intune use cases:</span></span>

- <span data-ttu-id="4db1e-110">Защита данных и электронной почты Exchange Online для безопасного доступа с мобильных устройств</span><span class="sxs-lookup"><span data-stu-id="4db1e-110">Protect Exchange Online email and data so it can be safely accessed by mobile devices</span></span>
- <span data-ttu-id="4db1e-111">Реализация программы использования собственных устройств (BYOD) для сотрудников Contoso</span><span class="sxs-lookup"><span data-stu-id="4db1e-111">Implement a bring your own device (BYOD) program for Contoso employees</span></span>
- <span data-ttu-id="4db1e-112">Предоставление сотрудникам Contoso корпоративных телефонов и общих планшетов для ограниченного использования</span><span class="sxs-lookup"><span data-stu-id="4db1e-112">Issue organization-owned phones and limited-use shared tablets to Contoso employees</span></span>

<span data-ttu-id="4db1e-113">Intune не используется в Contoso для следующего:</span><span class="sxs-lookup"><span data-stu-id="4db1e-113">Contoso is not using Intune to:</span></span>

- <span data-ttu-id="4db1e-114">Предоставление сотрудникам безопасного доступа к Office 365 из неуправляемых общедоступных киосков</span><span class="sxs-lookup"><span data-stu-id="4db1e-114">Allow employees to securely access Office 365 from an unmanaged public kiosk</span></span>
- <span data-ttu-id="4db1e-115">Защита локальной электронной почты и данных для безопасного доступа с мобильных устройств, поскольку локальные серверы Microsoft Exchange больше не применяются.</span><span class="sxs-lookup"><span data-stu-id="4db1e-115">Protect on-premises email and data so it can be safely accessed by mobile devices, because there are no longer on-premises Microsoft Exchange servers.</span></span>

## <a name="deploy"></a><span data-ttu-id="4db1e-116">Развертывание</span><span class="sxs-lookup"><span data-stu-id="4db1e-116">Deploy</span></span>

<span data-ttu-id="4db1e-117">Процедура настройки инфраструктуры управления мобильными устройствами в Contoso:</span><span class="sxs-lookup"><span data-stu-id="4db1e-117">This is how Contoso set up their mobile device management infrastructure:</span></span>

- <span data-ttu-id="4db1e-118">Задание Intune в качестве центра управления мобильными устройствами (MDM) и использование Intune на Azure для администрирования содержимого и управления устройствами</span><span class="sxs-lookup"><span data-stu-id="4db1e-118">Set Intune as the Mobile Device Management (MDM) authority and are using Intune on Azure to administer content and manage the devices</span></span>
- <span data-ttu-id="4db1e-119">Созданные группы Azure AD для устройств для регистрации и политики условного доступа на основе настроек Intune и устройств</span><span class="sxs-lookup"><span data-stu-id="4db1e-119">Created Azure AD groups for devices for enrollment and Intune settings and device-based conditional access policies</span></span>

  <span data-ttu-id="4db1e-120">Для получения дополнительных сведений см. статью [Условные политики доступа Contoso](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).</span><span class="sxs-lookup"><span data-stu-id="4db1e-120">See [Contoso's conditional access policies](contoso-identity.md#conditional-access-policies-for-identity-and-device-access) for more information.</span></span>

- <span data-ttu-id="4db1e-121">Включение платформы устройств Apple для поддержки сотрудников с iPad, iMac, iPhone, а также корпоративными телефонами на базе iPhone</span><span class="sxs-lookup"><span data-stu-id="4db1e-121">Enabled the Apple device platform to support employees with iPads, iMacs, iPhones, and for iPhone-based corporate-owned phones</span></span>
- <span data-ttu-id="4db1e-122">Создание политик использования применительно к Contoso, которые отображаются во время установки корпоративного портала для Contoso на мобильных устройствах</span><span class="sxs-lookup"><span data-stu-id="4db1e-122">Created Contoso-specific terms and conditions policies, which are seen during the installation of the Company Portal for Contoso on mobile devices</span></span>
- <span data-ttu-id="4db1e-123">Задание для незарегистрированных устройств политик управления мобильными приложениями (MAM), требующих проверки подлинности для доступа к службам Office 365</span><span class="sxs-lookup"><span data-stu-id="4db1e-123">For devices that are not enrolled, a set of Mobile Application Management (MAM) policies to require authentication for access to Office 365 services</span></span>
- <span data-ttu-id="4db1e-124">Создание политик Intune, обеспечивающих следующее:</span><span class="sxs-lookup"><span data-stu-id="4db1e-124">Created Intune policies that enforce:</span></span>
  - <span data-ttu-id="4db1e-125">Разрешенные приложения</span><span class="sxs-lookup"><span data-stu-id="4db1e-125">Allowed apps</span></span>
  - <span data-ttu-id="4db1e-126">Шифрование устройства для предотвращения несанкционированного доступа</span><span class="sxs-lookup"><span data-stu-id="4db1e-126">Device encryption to help prevent unauthorized access</span></span>
  - <span data-ttu-id="4db1e-127">Шестизначный ПИН-код или пароль</span><span class="sxs-lookup"><span data-stu-id="4db1e-127">A six-digit PIN or password</span></span>
  - <span data-ttu-id="4db1e-128">Время ожидания простоя</span><span class="sxs-lookup"><span data-stu-id="4db1e-128">An inactivity timeout period</span></span>
  - <span data-ttu-id="4db1e-129">Защита от вирусов и вредоносных программ, а также обновление сигнатур с помощью Защитника Windows на устройствах с Windows 10</span><span class="sxs-lookup"><span data-stu-id="4db1e-129">Antivirus and malware protection, and signature updates with Windows Defender on Windows 10 devices</span></span>
  - <span data-ttu-id="4db1e-130">Автоматические обновления устройств с Windows 10, которые содержат последние обновления для системы безопасности</span><span class="sxs-lookup"><span data-stu-id="4db1e-130">Automatic updates on Windows 10 devices that include the latest security updates</span></span>
  - <span data-ttu-id="4db1e-131">Передача сертификатов управляемым устройствам</span><span class="sxs-lookup"><span data-stu-id="4db1e-131">Pushing certificates to managed devices</span></span>
  - <span data-ttu-id="4db1e-p102">Четкое разделение корпоративных и личных данных. Пользователи или администраторы могут выборочно стирать корпоративные данные с устройства, не трогая личные данные, такие как рисунки, личные учетные записи электронной почты и личные файлы.</span><span class="sxs-lookup"><span data-stu-id="4db1e-p102">A clear separation of business and personal data. Users or admins can selectively wipe corporate data from the device, while leaving personal data such as pictures, personal email accounts, and personal files untouched.</span></span>

<span data-ttu-id="4db1e-p103">После развертывания Contoso регистрирует компьютеры и корпоративные смартфоны с планшетами, добавляя их в соответствующие группы устройств Intune, и разворачивает программу использования собственных устройств (BYOD) для сотрудников, чтобы зарегистрировать их личные устройства. Зарегистрированные устройства получают политики Intune, что обеспечивает управление и защиту устройств и их приложений. Для незарегистрированных устройств применяются политики управления мобильными приложениями (MAM), определяющие разрешенные приложения.</span><span class="sxs-lookup"><span data-stu-id="4db1e-p103">Once deployed, Contoso enrolled PCs and company-owned smartphones and tablets by adding them to the appropriate Intune device groups and rolled out a BYOD program for employees to enroll their personal devices. Enrolled devices received Intune policies, resulting in managed and secured devices and their applications. Devices that are not enrolled have Mobile Application Management (MAM) policies that specify allowed applications.</span></span>

## <a name="next-step"></a><span data-ttu-id="4db1e-137">Следующее действие</span><span class="sxs-lookup"><span data-stu-id="4db1e-137">Next step</span></span>

<span data-ttu-id="4db1e-138">[Сведения о том,](contoso-info-protect.md) как в Contoso используются функции защиты информации из Microsoft 365 корпоративный для классификации, определения и защиты важных цифровых ресурсов организации.</span><span class="sxs-lookup"><span data-stu-id="4db1e-138">[Learn](contoso-info-protect.md) how Contoso uses the information protection capabilities of Microsoft 365 Enterprise to classify, identify, and protect crucial digital assets across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="4db1e-139">См. также</span><span class="sxs-lookup"><span data-stu-id="4db1e-139">See also</span></span>

[<span data-ttu-id="4db1e-140">Управление мобильными устройствами для Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="4db1e-140">Mobile device management for Microsoft 365 Enterprise</span></span>](mobility-infrastructure.md)

[<span data-ttu-id="4db1e-141">Руководство по развертыванию</span><span class="sxs-lookup"><span data-stu-id="4db1e-141">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="4db1e-142">Руководства по лаборатории тестирования</span><span class="sxs-lookup"><span data-stu-id="4db1e-142">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)

