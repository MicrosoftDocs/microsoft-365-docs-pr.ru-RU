---
title: Управление мобильными устройствами для Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Общие сведения о том, как Contoso использует Microsoft Intune в Microsoft 365 корпоративный для управления устройствами и работающими на них приложениями.
ms.openlocfilehash: 7232c89cc105525cc57facd5a1b9de06426adbca
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42068374"
---
# <a name="mobile-device-management-for-contoso"></a><span data-ttu-id="fad51-103">Управление мобильными устройствами для Contoso</span><span class="sxs-lookup"><span data-stu-id="fad51-103">Mobile device management for Contoso</span></span>

<span data-ttu-id="fad51-104">Microsoft 365 корпоративный содержит Intune и набор служб Azure для поддержки мобильных устройств, управления приложениями и обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="fad51-104">Microsoft 365 Enterprise includes Intune and a set of Azure services to support mobile device and application management and security.</span></span>

<span data-ttu-id="fad51-p101">В Contoso есть много сотрудников с мобильными устройствами. Некоторые из них имеют офисы в расположениях Contoso, а некоторые — нет. Для Contoso требуется способ обеспечения производительности сотрудников с поддержкой безопасности устройств, данных Contoso на этих устройствах и работы приложений.</span><span class="sxs-lookup"><span data-stu-id="fad51-p101">Contoso has many mobile-enabled employees, some of which have offices in Contoso locations and some of which have no offices. Contoso needed a way to enable employee productivity but keep the devices, the Contoso data stored on those devices, and application behavior secure.</span></span>

## <a name="plan"></a><span data-ttu-id="fad51-107">Планирование</span><span class="sxs-lookup"><span data-stu-id="fad51-107">Plan</span></span>

<span data-ttu-id="fad51-108">Ранее при анализе управления мобильными устройствами для Microsoft 365 корпоративный были определены следующие случаи использования Intune в Contoso:</span><span class="sxs-lookup"><span data-stu-id="fad51-108">Early in the analysis of mobile device management for Microsoft 365 Enterprise, Contoso identified the following Intune use cases:</span></span>

- <span data-ttu-id="fad51-109">Защита данных и электронной почты Exchange Online для безопасного доступа с мобильных устройств</span><span class="sxs-lookup"><span data-stu-id="fad51-109">Protect Exchange Online email and data so it can be safely accessed by mobile devices</span></span>
- <span data-ttu-id="fad51-110">Реализация программы использования собственных устройств (BYOD) для сотрудников Contoso</span><span class="sxs-lookup"><span data-stu-id="fad51-110">Implement a bring your own device (BYOD) program for Contoso employees</span></span>
- <span data-ttu-id="fad51-111">Предоставление сотрудникам Contoso корпоративных телефонов и общих планшетов для ограниченного использования</span><span class="sxs-lookup"><span data-stu-id="fad51-111">Issue organization-owned phones and limited-use shared tablets to Contoso employees</span></span>

<span data-ttu-id="fad51-112">Intune не используется в Contoso для следующего:</span><span class="sxs-lookup"><span data-stu-id="fad51-112">Contoso is not using Intune to:</span></span>

- <span data-ttu-id="fad51-113">Предоставление сотрудникам безопасного доступа к Office 365 из неуправляемых общедоступных киосков</span><span class="sxs-lookup"><span data-stu-id="fad51-113">Allow employees to securely access Office 365 from an unmanaged public kiosk</span></span>
- <span data-ttu-id="fad51-114">Защита локальной электронной почты и данных для безопасного доступа с мобильных устройств, поскольку локальные серверы Microsoft Exchange больше не применяются.</span><span class="sxs-lookup"><span data-stu-id="fad51-114">Protect on-premises email and data so it can be safely accessed by mobile devices, because there are no longer on-premises Microsoft Exchange servers.</span></span>

## <a name="deploy"></a><span data-ttu-id="fad51-115">Развертывание</span><span class="sxs-lookup"><span data-stu-id="fad51-115">Deploy</span></span>

<span data-ttu-id="fad51-116">Процедура настройки инфраструктуры управления мобильными устройствами в Contoso:</span><span class="sxs-lookup"><span data-stu-id="fad51-116">This is how Contoso set up their mobile device management infrastructure:</span></span>

- <span data-ttu-id="fad51-117">Задание Intune в качестве центра управления мобильными устройствами (MDM) и использование Intune на Azure для администрирования содержимого и управления устройствами</span><span class="sxs-lookup"><span data-stu-id="fad51-117">Set Intune as the Mobile Device Management (MDM) authority and are using Intune on Azure to administer content and manage the devices</span></span>
- <span data-ttu-id="fad51-118">Созданные группы Azure AD для устройств для регистрации и политики условного доступа на основе настроек Intune и устройств</span><span class="sxs-lookup"><span data-stu-id="fad51-118">Created Azure AD groups for devices for enrollment and Intune settings and device-based Conditional Access policies</span></span>

  <span data-ttu-id="fad51-119">Для получения дополнительных сведений см. статью [Условные политики доступа Contoso](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).</span><span class="sxs-lookup"><span data-stu-id="fad51-119">See [Contoso's Conditional Access policies](contoso-identity.md#conditional-access-policies-for-identity-and-device-access) for more information.</span></span>

- <span data-ttu-id="fad51-120">Включение платформы устройств Apple для поддержки сотрудников с iPad, iMac, iPhone, а также корпоративными телефонами на базе iPhone</span><span class="sxs-lookup"><span data-stu-id="fad51-120">Enabled the Apple device platform to support employees with iPads, iMacs, iPhones, and for iPhone-based corporate-owned phones</span></span>
- <span data-ttu-id="fad51-121">Создание политик использования применительно к Contoso, которые отображаются во время установки корпоративного портала для Contoso на мобильных устройствах</span><span class="sxs-lookup"><span data-stu-id="fad51-121">Created Contoso-specific terms and conditions policies, which are seen during the installation of the Company Portal for Contoso on mobile devices</span></span>
- <span data-ttu-id="fad51-122">Задание для незарегистрированных устройств политик управления мобильными приложениями (MAM), требующих проверки подлинности для доступа к службам Office 365</span><span class="sxs-lookup"><span data-stu-id="fad51-122">For devices that are not enrolled, a set of Mobile Application Management (MAM) policies to require authentication for access to Office 365 services</span></span>
- <span data-ttu-id="fad51-123">Создание политик Intune, обеспечивающих следующее:</span><span class="sxs-lookup"><span data-stu-id="fad51-123">Created Intune policies that enforce:</span></span>
  - <span data-ttu-id="fad51-124">Разрешенные приложения</span><span class="sxs-lookup"><span data-stu-id="fad51-124">Allowed apps</span></span>
  - <span data-ttu-id="fad51-125">Шифрование устройства для предотвращения несанкционированного доступа</span><span class="sxs-lookup"><span data-stu-id="fad51-125">Device encryption to help prevent unauthorized access</span></span>
  - <span data-ttu-id="fad51-126">Шестизначный ПИН-код или пароль</span><span class="sxs-lookup"><span data-stu-id="fad51-126">A six-digit PIN or password</span></span>
  - <span data-ttu-id="fad51-127">Время ожидания простоя</span><span class="sxs-lookup"><span data-stu-id="fad51-127">An inactivity timeout period</span></span>
  - <span data-ttu-id="fad51-128">Защита от вирусов и вредоносных программ, а также обновление сигнатур с помощью Защитника Windows на устройствах с Windows 10</span><span class="sxs-lookup"><span data-stu-id="fad51-128">Antivirus and malware protection, and signature updates with Windows Defender on Windows 10 devices</span></span>
  - <span data-ttu-id="fad51-129">Автоматические обновления устройств с Windows 10, которые содержат последние обновления для системы безопасности</span><span class="sxs-lookup"><span data-stu-id="fad51-129">Automatic updates on Windows 10 devices that include the latest security updates</span></span>
  - <span data-ttu-id="fad51-130">Передача сертификатов управляемым устройствам</span><span class="sxs-lookup"><span data-stu-id="fad51-130">Pushing certificates to managed devices</span></span>
  - <span data-ttu-id="fad51-p102">Четкое разделение корпоративных и личных данных. Пользователи или администраторы могут выборочно стирать корпоративные данные с устройства, не трогая личные данные, такие как рисунки, личные учетные записи электронной почты и личные файлы.</span><span class="sxs-lookup"><span data-stu-id="fad51-p102">A clear separation of business and personal data. Users or admins can selectively wipe corporate data from the device, while leaving personal data such as pictures, personal email accounts, and personal files untouched.</span></span>

<span data-ttu-id="fad51-p103">После развертывания Contoso регистрирует компьютеры и корпоративные смартфоны с планшетами, добавляя их в соответствующие группы устройств Intune, и разворачивает программу использования собственных устройств (BYOD) для сотрудников, чтобы зарегистрировать их личные устройства. Зарегистрированные устройства получают политики Intune, что обеспечивает управление и защиту устройств и их приложений. Для незарегистрированных устройств применяются политики управления мобильными приложениями (MAM), определяющие разрешенные приложения.</span><span class="sxs-lookup"><span data-stu-id="fad51-p103">Once deployed, Contoso enrolled PCs and company-owned smartphones and tablets by adding them to the appropriate Intune device groups and rolled out a BYOD program for employees to enroll their personal devices. Enrolled devices received Intune policies, resulting in managed and secured devices and their applications. Devices that are not enrolled have Mobile Application Management (MAM) policies that specify allowed applications.</span></span>

<span data-ttu-id="fad51-136">Ниже приведена архитектура развертывания управления мобильными устройствами Contoso.</span><span class="sxs-lookup"><span data-stu-id="fad51-136">Here is Contoso's mobile device management deployment architecture.</span></span>

![Инфраструктура развертывания управления мобильными устройствами Contoso](../media/contoso-mdm/contoso-mdm-fig1.png)

## <a name="next-step"></a><span data-ttu-id="fad51-138">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="fad51-138">Next step</span></span>

<span data-ttu-id="fad51-139">[Сведения о том,](contoso-info-protect.md) как в Contoso используются функции защиты информации из Microsoft 365 корпоративный для классификации, определения и защиты важных цифровых ресурсов организации.</span><span class="sxs-lookup"><span data-stu-id="fad51-139">[Learn](contoso-info-protect.md) how Contoso uses the information protection capabilities of Microsoft 365 Enterprise to classify, identify, and protect crucial digital assets across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="fad51-140">См. также</span><span class="sxs-lookup"><span data-stu-id="fad51-140">See also</span></span>

[<span data-ttu-id="fad51-141">Управление мобильными устройствами для Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="fad51-141">Mobile device management for Microsoft 365 Enterprise</span></span>](mobility-infrastructure.md)

[<span data-ttu-id="fad51-142">Руководство по развертыванию</span><span class="sxs-lookup"><span data-stu-id="fad51-142">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="fad51-143">Руководства по лаборатории тестирования</span><span class="sxs-lookup"><span data-stu-id="fad51-143">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)

