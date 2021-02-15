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
description: В этой теме поймут, как Contoso использует Microsoft Intune в Microsoft 365 для предприятий для управления устройствами и приложениями, которые на них работают.
ms.openlocfilehash: 6d7783e8c2d9b78b63bf9eefe761fbc52d0b280f
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754001"
---
# <a name="mobile-device-management-for-contoso"></a><span data-ttu-id="0c15b-103">Управление мобильными устройствами для Contoso</span><span class="sxs-lookup"><span data-stu-id="0c15b-103">Mobile device management for Contoso</span></span>

<span data-ttu-id="0c15b-104">Microsoft 365 для предприятий включает Intune и набор служб Azure, которые поддерживают управление мобильными устройствами, приложениями и безопасностью.</span><span class="sxs-lookup"><span data-stu-id="0c15b-104">Microsoft 365 for enterprise includes Intune and a set of Azure services that support mobile device and application management and security.</span></span>

<span data-ttu-id="0c15b-p101">В компании Contoso имеется много сотрудников с поддержкой мобильных устройств. Некоторые из них имеют офисы в расположениях Contoso, а другие нет. Компании Contoso необходим способ повышения производительности сотрудников, но обеспечить безопасность устройств, данных Contoso, хранимых на этих устройствах, а также поведения приложений.</span><span class="sxs-lookup"><span data-stu-id="0c15b-p101">Contoso has many mobile-enabled employees. Some have offices in Contoso locations, and some have no offices. Contoso needed a way to enable employee productivity but keep the devices, the Contoso data stored on those devices, and application behavior secure.</span></span>

## <a name="plan"></a><span data-ttu-id="0c15b-108">План</span><span class="sxs-lookup"><span data-stu-id="0c15b-108">Plan</span></span>

<span data-ttu-id="0c15b-109">Корпорация Contoso определила следующие случаи использования Intune для управления мобильными устройствами для Microsoft 365 для предприятий:</span><span class="sxs-lookup"><span data-stu-id="0c15b-109">Contoso identified the following Intune use cases of mobile device management for Microsoft 365 for enterprise:</span></span>

- <span data-ttu-id="0c15b-110">Защитите электронную почту и данные Exchange Online, чтобы к ней можно было безопасно получить доступ с мобильных устройств.</span><span class="sxs-lookup"><span data-stu-id="0c15b-110">Protect Exchange Online email and data so it can be safely accessed by mobile devices.</span></span>
- <span data-ttu-id="0c15b-111">Реализуйте программу принеси свое устройство (BYOD) для сотрудников Contoso.</span><span class="sxs-lookup"><span data-stu-id="0c15b-111">Implement a bring-your-own-device (BYOD) program for Contoso employees.</span></span>
- <span data-ttu-id="0c15b-112">Выдают сотрудникам Contoso телефоны, которые принадлежат организации, и общие планшеты с ограниченным использованием.</span><span class="sxs-lookup"><span data-stu-id="0c15b-112">Issue organization-owned phones and limited-use shared tablets to Contoso employees.</span></span>

<span data-ttu-id="0c15b-113">Contoso не использует Intune для:</span><span class="sxs-lookup"><span data-stu-id="0c15b-113">Contoso doesn't use Intune to:</span></span>

- <span data-ttu-id="0c15b-114">Разрешить сотрудникам безопасный доступ к Microsoft 365 из неугодного общего терминала.</span><span class="sxs-lookup"><span data-stu-id="0c15b-114">Allow employees to securely access Microsoft 365 from an unmanaged public kiosk.</span></span>
- <span data-ttu-id="0c15b-115">Защита локальной электронной почты и данных для безопасного доступа с мобильных устройств, так как на них нет локального сервера Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="0c15b-115">Protect on-premises email and data so it can be safely accessed by mobile devices, because there are no on-premises Microsoft Exchange servers.</span></span>

## <a name="deploy"></a><span data-ttu-id="0c15b-116">Развертывание</span><span class="sxs-lookup"><span data-stu-id="0c15b-116">Deploy</span></span>

<span data-ttu-id="0c15b-117">Процедура настройки инфраструктуры управления мобильными устройствами в Contoso:</span><span class="sxs-lookup"><span data-stu-id="0c15b-117">This is how Contoso set up their mobile device management infrastructure:</span></span>

- <span data-ttu-id="0c15b-118">Настройка Intune в качестве органа управления мобильными устройствами (MDM) и использование Intune в Azure для администрирования контента и управления устройствами</span><span class="sxs-lookup"><span data-stu-id="0c15b-118">Set Intune as the Mobile Device Management (MDM) authority, and use Intune on Azure to administer content and manage the devices</span></span>
- <span data-ttu-id="0c15b-119">Создание групп Azure Active Directory (Azure AD) для устройств для регистрации и параметров Intune, а также политик условного доступа на основе устройств</span><span class="sxs-lookup"><span data-stu-id="0c15b-119">Created Azure Active Directory (Azure AD) groups for devices for enrollment and Intune settings and device-based Conditional Access policies</span></span>

  <span data-ttu-id="0c15b-120">Дополнительные сведения см. в [политиках условного доступа Contoso.](contoso-identity.md#conditional-access-policies-for-identity-and-device-access)</span><span class="sxs-lookup"><span data-stu-id="0c15b-120">For more information, see [Contoso Conditional Access policies](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).</span></span>

- <span data-ttu-id="0c15b-121">Включена платформа устройств Apple для поддержки сотрудников с iPad, iMac и iPhone, а также корпоративными устройствами iPhone</span><span class="sxs-lookup"><span data-stu-id="0c15b-121">Enabled the Apple device platform to support employees with iPads, iMacs, and iPhones, and corporate-owned iPhones</span></span>
- <span data-ttu-id="0c15b-122">Создание политик использования применительно к Contoso, которые отображаются во время установки корпоративного портала для Contoso на мобильных устройствах</span><span class="sxs-lookup"><span data-stu-id="0c15b-122">Created Contoso-specific terms and conditions policies, which are seen during the installation of the Company Portal for Contoso on mobile devices</span></span>
- <span data-ttu-id="0c15b-123">Для устройств, которые не зарегистрированы, реализован набор политик управления мобильными приложениями (MAM), чтобы требовать проверку подлинности для доступа к службам Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0c15b-123">For devices that aren't enrolled, implemented a set of Mobile Application Management (MAM) policies to require authentication for access to Microsoft 365 services</span></span>
- <span data-ttu-id="0c15b-124">Создание политик Intune, обеспечивающих следующее:</span><span class="sxs-lookup"><span data-stu-id="0c15b-124">Created Intune policies that enforce:</span></span>
  - <span data-ttu-id="0c15b-125">Разрешенные приложения.</span><span class="sxs-lookup"><span data-stu-id="0c15b-125">Allowed apps.</span></span>
  - <span data-ttu-id="0c15b-126">Шифрование устройства для предотвращения несанкционированного доступа.</span><span class="sxs-lookup"><span data-stu-id="0c15b-126">Device encryption to help prevent unauthorized access.</span></span>
  - <span data-ttu-id="0c15b-127">Шестизначный ПИН-код или пароль.</span><span class="sxs-lookup"><span data-stu-id="0c15b-127">A six-digit PIN or password.</span></span>
  - <span data-ttu-id="0c15b-128">Период неактивности и времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="0c15b-128">An inactivity-timeout period.</span></span>
  - <span data-ttu-id="0c15b-129">Защита от вирусов и вредоносных программ, а также обновления подписей с Защитник Windows на устройствах с Windows 10.</span><span class="sxs-lookup"><span data-stu-id="0c15b-129">Antivirus and malware protection, and signature updates with Windows Defender on Windows 10 devices.</span></span>
  - <span data-ttu-id="0c15b-130">Автоматические обновления на устройствах с Windows 10 с последними обновлениями для системы безопасности.</span><span class="sxs-lookup"><span data-stu-id="0c15b-130">Automatic updates on Windows 10 devices that include the latest security updates.</span></span>
  - <span data-ttu-id="0c15b-131">Pushing certificates to managed devices.</span><span class="sxs-lookup"><span data-stu-id="0c15b-131">Pushing certificates to managed devices.</span></span>
  - <span data-ttu-id="0c15b-p102">Четкое разделение корпоративных и личных данных. Пользователи или администраторы могут выборочно стирать корпоративные данные с устройства, не трогая личные данные, такие как рисунки, личные учетные записи электронной почты и личные файлы.</span><span class="sxs-lookup"><span data-stu-id="0c15b-p102">A clear separation of business and personal data. Users or admins can selectively wipe corporate data from the device, while leaving personal data such as pictures, personal email accounts, and personal files untouched.</span></span>

<span data-ttu-id="0c15b-134">Компания Contoso зарегистрировала развернутые компьютеры и смартфоны и планшеты компании, добавив их в соответствующие группы устройств Intune.</span><span class="sxs-lookup"><span data-stu-id="0c15b-134">Contoso enrolled deployed PCs and company-owned smartphones and tablets by adding them to the appropriate Intune device groups.</span></span> <span data-ttu-id="0c15b-135">Они также создали программу BYOD для сотрудников для регистрации своих личных устройств.</span><span class="sxs-lookup"><span data-stu-id="0c15b-135">They also established a BYOD program for employees to enroll their personal devices.</span></span> <span data-ttu-id="0c15b-136">Зарегистрированные устройства получают политики Intune, в результате чего управляемые и защищенные устройства и их приложения.</span><span class="sxs-lookup"><span data-stu-id="0c15b-136">Enrolled devices receive Intune policies, which results in managed and secured devices and their applications.</span></span> <span data-ttu-id="0c15b-137">Устройства, которые не зарегистрированы, имеют политики управления мобильными приложениями (MAM), которые определяют разрешенные приложения.</span><span class="sxs-lookup"><span data-stu-id="0c15b-137">Devices that aren't enrolled have Mobile Application Management (MAM) policies that specify allowed applications.</span></span>

<span data-ttu-id="0c15b-138">Вот архитектура развертывания управления мобильными устройствами Contoso.</span><span class="sxs-lookup"><span data-stu-id="0c15b-138">Here is the Contoso mobile device management deployment architecture.</span></span>

![Инфраструктура развертывания управления мобильными устройствами Contoso](../media/contoso-mdm/contoso-mdm-fig1.png)

## <a name="next-step"></a><span data-ttu-id="0c15b-140">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="0c15b-140">Next step</span></span>

<span data-ttu-id="0c15b-141">Узнайте, как Contoso использует возможности защиты информации Microsoft 365 для предприятий для классификации, идентификации и защиты важных цифровых активов в организации. [](contoso-info-protect.md)</span><span class="sxs-lookup"><span data-stu-id="0c15b-141">Learn how Contoso uses the [information protection capabilities](contoso-info-protect.md) of Microsoft 365 for enterprise to classify, identify, and protect crucial digital assets across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="0c15b-142">См. также</span><span class="sxs-lookup"><span data-stu-id="0c15b-142">See also</span></span>

[<span data-ttu-id="0c15b-143">Управление устройствами для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0c15b-143">Device management for Microsoft 365</span></span>](device-management-roadmap-microsoft-365.md)

[<span data-ttu-id="0c15b-144">Обзор Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="0c15b-144">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="0c15b-145">Руководства по лаборатории тестирования</span><span class="sxs-lookup"><span data-stu-id="0c15b-145">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)

