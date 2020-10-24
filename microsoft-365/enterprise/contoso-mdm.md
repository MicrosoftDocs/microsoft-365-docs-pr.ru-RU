---
title: Управление мобильными устройствами для Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Узнайте, как компания Contoso использует Microsoft Intune в Microsoft 365 для управления устройствами и приложениями, которые запускаются на них.
ms.openlocfilehash: 6d7783e8c2d9b78b63bf9eefe761fbc52d0b280f
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754001"
---
# <a name="mobile-device-management-for-contoso"></a><span data-ttu-id="758de-103">Управление мобильными устройствами для Contoso</span><span class="sxs-lookup"><span data-stu-id="758de-103">Mobile device management for Contoso</span></span>

<span data-ttu-id="758de-104">Microsoft 365 для предприятий включает Intune и набор служб Azure, поддерживающих управление мобильными устройствами и приложениями и безопасность.</span><span class="sxs-lookup"><span data-stu-id="758de-104">Microsoft 365 for enterprise includes Intune and a set of Azure services that support mobile device and application management and security.</span></span>

<span data-ttu-id="758de-p101">У компании Contoso есть много сотрудников с поддержкой мобильных устройств. У некоторых есть офисы в расположениях Contoso, а в других нет офисов. Компании Contoso требовалось обеспечить возможность повышения продуктивности сотрудников, хранения устройств, данных Contoso, хранящихся на этих устройствах, и обеспечения безопасности поведения приложений.</span><span class="sxs-lookup"><span data-stu-id="758de-p101">Contoso has many mobile-enabled employees. Some have offices in Contoso locations, and some have no offices. Contoso needed a way to enable employee productivity but keep the devices, the Contoso data stored on those devices, and application behavior secure.</span></span>

## <a name="plan"></a><span data-ttu-id="758de-108">План</span><span class="sxs-lookup"><span data-stu-id="758de-108">Plan</span></span>

<span data-ttu-id="758de-109">Компания Contoso определила следующие варианты использования Intune для управления мобильными устройствами для Microsoft 365 для предприятий:</span><span class="sxs-lookup"><span data-stu-id="758de-109">Contoso identified the following Intune use cases of mobile device management for Microsoft 365 for enterprise:</span></span>

- <span data-ttu-id="758de-110">Защитите электронную почту и данные Exchange Online, чтобы обеспечить их безопасное обращение к мобильным устройствам.</span><span class="sxs-lookup"><span data-stu-id="758de-110">Protect Exchange Online email and data so it can be safely accessed by mobile devices.</span></span>
- <span data-ttu-id="758de-111">Реализация программы "самостоятельное устройство" (BYOD) для сотрудников Contoso.</span><span class="sxs-lookup"><span data-stu-id="758de-111">Implement a bring-your-own-device (BYOD) program for Contoso employees.</span></span>
- <span data-ttu-id="758de-112">Выдача сотрудников компании Contoso с помощью телефонов, принадлежащих Организации, и общих планшетов.</span><span class="sxs-lookup"><span data-stu-id="758de-112">Issue organization-owned phones and limited-use shared tablets to Contoso employees.</span></span>

<span data-ttu-id="758de-113">Contoso не использует Intune для следующих действий:</span><span class="sxs-lookup"><span data-stu-id="758de-113">Contoso doesn't use Intune to:</span></span>

- <span data-ttu-id="758de-114">Разрешить сотрудникам безопасно получать доступ к Microsoft 365 из неуправляемого общедоступного киоска.</span><span class="sxs-lookup"><span data-stu-id="758de-114">Allow employees to securely access Microsoft 365 from an unmanaged public kiosk.</span></span>
- <span data-ttu-id="758de-115">Защитите локальную электронную почту и данные, чтобы обеспечить их безопасное обращение к мобильным устройствам, так как нет локальных серверов Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="758de-115">Protect on-premises email and data so it can be safely accessed by mobile devices, because there are no on-premises Microsoft Exchange servers.</span></span>

## <a name="deploy"></a><span data-ttu-id="758de-116">Развертывание</span><span class="sxs-lookup"><span data-stu-id="758de-116">Deploy</span></span>

<span data-ttu-id="758de-117">Процедура настройки инфраструктуры управления мобильными устройствами в Contoso:</span><span class="sxs-lookup"><span data-stu-id="758de-117">This is how Contoso set up their mobile device management infrastructure:</span></span>

- <span data-ttu-id="758de-118">Настройка Intune в качестве центра управления мобильными устройствами (MDM) и использование Intune в Azure для администрирования контента и управления устройствами</span><span class="sxs-lookup"><span data-stu-id="758de-118">Set Intune as the Mobile Device Management (MDM) authority, and use Intune on Azure to administer content and manage the devices</span></span>
- <span data-ttu-id="758de-119">Созданы группы Azure Active Directory (Azure AD) для устройств для регистрации и настройки Intune и политик условного доступа на основе устройств</span><span class="sxs-lookup"><span data-stu-id="758de-119">Created Azure Active Directory (Azure AD) groups for devices for enrollment and Intune settings and device-based Conditional Access policies</span></span>

  <span data-ttu-id="758de-120">Дополнительные сведения см. в разделе [политики условного доступа Contoso](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).</span><span class="sxs-lookup"><span data-stu-id="758de-120">For more information, see [Contoso Conditional Access policies](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).</span></span>

- <span data-ttu-id="758de-121">Включена платформа устройств Apple для поддержки сотрудников с iPad, iMac и iPhone, а также для корпоративных iPhone</span><span class="sxs-lookup"><span data-stu-id="758de-121">Enabled the Apple device platform to support employees with iPads, iMacs, and iPhones, and corporate-owned iPhones</span></span>
- <span data-ttu-id="758de-122">Создание политик использования применительно к Contoso, которые отображаются во время установки корпоративного портала для Contoso на мобильных устройствах</span><span class="sxs-lookup"><span data-stu-id="758de-122">Created Contoso-specific terms and conditions policies, which are seen during the installation of the Company Portal for Contoso on mobile devices</span></span>
- <span data-ttu-id="758de-123">Для устройств, которые не зарегистрированы, реализован набор политик управления мобильными приложениями (MAM), требующих проверки подлинности для доступа к службам Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="758de-123">For devices that aren't enrolled, implemented a set of Mobile Application Management (MAM) policies to require authentication for access to Microsoft 365 services</span></span>
- <span data-ttu-id="758de-124">Создание политик Intune, обеспечивающих следующее:</span><span class="sxs-lookup"><span data-stu-id="758de-124">Created Intune policies that enforce:</span></span>
  - <span data-ttu-id="758de-125">Разрешенные приложения.</span><span class="sxs-lookup"><span data-stu-id="758de-125">Allowed apps.</span></span>
  - <span data-ttu-id="758de-126">Шифрование устройств для предотвращения несанкционированного доступа.</span><span class="sxs-lookup"><span data-stu-id="758de-126">Device encryption to help prevent unauthorized access.</span></span>
  - <span data-ttu-id="758de-127">ПИН-код из шести цифр или пароль.</span><span class="sxs-lookup"><span data-stu-id="758de-127">A six-digit PIN or password.</span></span>
  - <span data-ttu-id="758de-128">Период бездействия — время ожидания.</span><span class="sxs-lookup"><span data-stu-id="758de-128">An inactivity-timeout period.</span></span>
  - <span data-ttu-id="758de-129">Защита от вирусов и вредоносных программ, а также обновление подписей с помощью защитника Windows на устройствах с Windows 10.</span><span class="sxs-lookup"><span data-stu-id="758de-129">Antivirus and malware protection, and signature updates with Windows Defender on Windows 10 devices.</span></span>
  - <span data-ttu-id="758de-130">Автоматическое обновление устройств с Windows 10, включающих последние обновления для системы безопасности.</span><span class="sxs-lookup"><span data-stu-id="758de-130">Automatic updates on Windows 10 devices that include the latest security updates.</span></span>
  - <span data-ttu-id="758de-131">Принудительная отправка сертификатов управляемым устройствам.</span><span class="sxs-lookup"><span data-stu-id="758de-131">Pushing certificates to managed devices.</span></span>
  - <span data-ttu-id="758de-p102">Четкое разделение корпоративных и личных данных. Пользователи или администраторы могут выборочно стирать корпоративные данные с устройства, не трогая личные данные, такие как рисунки, личные учетные записи электронной почты и личные файлы.</span><span class="sxs-lookup"><span data-stu-id="758de-p102">A clear separation of business and personal data. Users or admins can selectively wipe corporate data from the device, while leaving personal data such as pictures, personal email accounts, and personal files untouched.</span></span>

<span data-ttu-id="758de-134">Развернутые компьютеры Contoso, а также смартфоны и планшетные компании добавляются в соответствующие группы устройств Intune.</span><span class="sxs-lookup"><span data-stu-id="758de-134">Contoso enrolled deployed PCs and company-owned smartphones and tablets by adding them to the appropriate Intune device groups.</span></span> <span data-ttu-id="758de-135">Они также установили программу BYOD, чтобы сотрудники зарегистрировали персональные устройства.</span><span class="sxs-lookup"><span data-stu-id="758de-135">They also established a BYOD program for employees to enroll their personal devices.</span></span> <span data-ttu-id="758de-136">Зарегистрированные устройства получают политики Intune, что приводит к управляемым и защищенным устройствам и их приложениям.</span><span class="sxs-lookup"><span data-stu-id="758de-136">Enrolled devices receive Intune policies, which results in managed and secured devices and their applications.</span></span> <span data-ttu-id="758de-137">Устройства, которые не зарегистрированы, имеют политики управления мобильными приложениями (MAM), которые определяют разрешенные приложения.</span><span class="sxs-lookup"><span data-stu-id="758de-137">Devices that aren't enrolled have Mobile Application Management (MAM) policies that specify allowed applications.</span></span>

<span data-ttu-id="758de-138">Ниже показана архитектура развертывания управления мобильными устройствами contoso.</span><span class="sxs-lookup"><span data-stu-id="758de-138">Here is the Contoso mobile device management deployment architecture.</span></span>

![Инфраструктура развертывания управления мобильными устройствами contoso](../media/contoso-mdm/contoso-mdm-fig1.png)

## <a name="next-step"></a><span data-ttu-id="758de-140">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="758de-140">Next step</span></span>

<span data-ttu-id="758de-141">Узнайте, как компания Contoso использует [возможности защиты информации](contoso-info-protect.md) в Microsoft 365 для предприятий для классификации, идентификации и защиты важных цифровых ресурсов в Организации.</span><span class="sxs-lookup"><span data-stu-id="758de-141">Learn how Contoso uses the [information protection capabilities](contoso-info-protect.md) of Microsoft 365 for enterprise to classify, identify, and protect crucial digital assets across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="758de-142">Дополнительные ресурсы:</span><span class="sxs-lookup"><span data-stu-id="758de-142">See also</span></span>

[<span data-ttu-id="758de-143">Управление устройствами для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="758de-143">Device management for Microsoft 365</span></span>](device-management-roadmap-microsoft-365.md)

[<span data-ttu-id="758de-144">Обзор Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="758de-144">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="758de-145">Руководства по лаборатории тестирования</span><span class="sxs-lookup"><span data-stu-id="758de-145">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)

