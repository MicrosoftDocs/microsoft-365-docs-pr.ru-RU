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
description: Поймите, как Contoso использует Microsoft Intune в Microsoft 365 для предприятия для управления своими устройствами и приложениями, которые работают на них.
ms.openlocfilehash: 6d7783e8c2d9b78b63bf9eefe761fbc52d0b280f
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754001"
---
# <a name="mobile-device-management-for-contoso"></a><span data-ttu-id="4c4eb-103">Управление мобильными устройствами для Contoso</span><span class="sxs-lookup"><span data-stu-id="4c4eb-103">Mobile device management for Contoso</span></span>

<span data-ttu-id="4c4eb-104">Microsoft 365 для предприятия включает Intune и набор служб Azure, которые поддерживают управление мобильными устройствами, управление приложениями и безопасность.</span><span class="sxs-lookup"><span data-stu-id="4c4eb-104">Microsoft 365 for enterprise includes Intune and a set of Azure services that support mobile device and application management and security.</span></span>

<span data-ttu-id="4c4eb-105">У Contoso много сотрудников с поддержкой мобильных устройств.</span><span class="sxs-lookup"><span data-stu-id="4c4eb-105">Contoso has many mobile-enabled employees.</span></span> <span data-ttu-id="4c4eb-106">Некоторые из них имеют офисы в расположениях Contoso, а некоторые не имеют офисов.</span><span class="sxs-lookup"><span data-stu-id="4c4eb-106">Some have offices in Contoso locations, and some have no offices.</span></span> <span data-ttu-id="4c4eb-107">Contoso требовался способ обеспечить производительность сотрудников, но обеспечить безопасность устройств, данных Contoso, хранимых на этих устройствах, и поведения приложений.</span><span class="sxs-lookup"><span data-stu-id="4c4eb-107">Contoso needed a way to enable employee productivity but keep the devices, the Contoso data stored on those devices, and application behavior secure.</span></span>

## <a name="plan"></a><span data-ttu-id="4c4eb-108">Планирование</span><span class="sxs-lookup"><span data-stu-id="4c4eb-108">Plan</span></span>

<span data-ttu-id="4c4eb-109">Contoso определила следующие случаи использования Intune для управления мобильными устройствами для Microsoft 365 для предприятия:</span><span class="sxs-lookup"><span data-stu-id="4c4eb-109">Contoso identified the following Intune use cases of mobile device management for Microsoft 365 for enterprise:</span></span>

- <span data-ttu-id="4c4eb-110">Защита Exchange Online электронной почты и данных для безопасного доступа с мобильных устройств.</span><span class="sxs-lookup"><span data-stu-id="4c4eb-110">Protect Exchange Online email and data so it can be safely accessed by mobile devices.</span></span>
- <span data-ttu-id="4c4eb-111">Реализация программы bring-your-own-device (BYOD) для сотрудников Contoso.</span><span class="sxs-lookup"><span data-stu-id="4c4eb-111">Implement a bring-your-own-device (BYOD) program for Contoso employees.</span></span>
- <span data-ttu-id="4c4eb-112">Выпуск телефонов, которые принадлежат организации, и планшеты с ограниченным использованием для сотрудников Contoso.</span><span class="sxs-lookup"><span data-stu-id="4c4eb-112">Issue organization-owned phones and limited-use shared tablets to Contoso employees.</span></span>

<span data-ttu-id="4c4eb-113">Contoso не использует Intune для:</span><span class="sxs-lookup"><span data-stu-id="4c4eb-113">Contoso doesn't use Intune to:</span></span>

- <span data-ttu-id="4c4eb-114">Разрешить сотрудникам безопасный доступ к Microsoft 365 из неугодного публичного киоска.</span><span class="sxs-lookup"><span data-stu-id="4c4eb-114">Allow employees to securely access Microsoft 365 from an unmanaged public kiosk.</span></span>
- <span data-ttu-id="4c4eb-115">Защита локальной электронной почты и данных, чтобы к ней можно было безопасно получить доступ с мобильных устройств, так как на локальном сервере Microsoft Exchange нет.</span><span class="sxs-lookup"><span data-stu-id="4c4eb-115">Protect on-premises email and data so it can be safely accessed by mobile devices, because there are no on-premises Microsoft Exchange servers.</span></span>

## <a name="deploy"></a><span data-ttu-id="4c4eb-116">Развертывание</span><span class="sxs-lookup"><span data-stu-id="4c4eb-116">Deploy</span></span>

<span data-ttu-id="4c4eb-117">Процедура настройки инфраструктуры управления мобильными устройствами в Contoso:</span><span class="sxs-lookup"><span data-stu-id="4c4eb-117">This is how Contoso set up their mobile device management infrastructure:</span></span>

- <span data-ttu-id="4c4eb-118">Установите Intune в качестве органа управления мобильными устройствами (MDM) и используйте Intune в Azure для администрирования контента и управления устройствами</span><span class="sxs-lookup"><span data-stu-id="4c4eb-118">Set Intune as the Mobile Device Management (MDM) authority, and use Intune on Azure to administer content and manage the devices</span></span>
- <span data-ttu-id="4c4eb-119">Созданные Azure Active Directory (Azure AD) группы для устройств для регистрации и параметров Intune и политики условного доступа на основе устройств</span><span class="sxs-lookup"><span data-stu-id="4c4eb-119">Created Azure Active Directory (Azure AD) groups for devices for enrollment and Intune settings and device-based Conditional Access policies</span></span>

  <span data-ttu-id="4c4eb-120">Дополнительные сведения см. в дополнительных сведениях о политиках условного доступа [Contoso.](contoso-identity.md#conditional-access-policies-for-identity-and-device-access)</span><span class="sxs-lookup"><span data-stu-id="4c4eb-120">For more information, see [Contoso Conditional Access policies](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).</span></span>

- <span data-ttu-id="4c4eb-121">Включена платформа устройств Apple для поддержки сотрудников с iPads, iMacs и iPhones, а также корпоративных iPhones.</span><span class="sxs-lookup"><span data-stu-id="4c4eb-121">Enabled the Apple device platform to support employees with iPads, iMacs, and iPhones, and corporate-owned iPhones</span></span>
- <span data-ttu-id="4c4eb-122">Создание политик использования применительно к Contoso, которые отображаются во время установки корпоративного портала для Contoso на мобильных устройствах</span><span class="sxs-lookup"><span data-stu-id="4c4eb-122">Created Contoso-specific terms and conditions policies, which are seen during the installation of the Company Portal for Contoso on mobile devices</span></span>
- <span data-ttu-id="4c4eb-123">Для устройств, которые не зарегистрированы, реализован набор политик управления мобильными приложениями (MAM), которые требуют проверки подлинности для доступа к Microsoft 365 службам</span><span class="sxs-lookup"><span data-stu-id="4c4eb-123">For devices that aren't enrolled, implemented a set of Mobile Application Management (MAM) policies to require authentication for access to Microsoft 365 services</span></span>
- <span data-ttu-id="4c4eb-124">Создание политик Intune, обеспечивающих следующее:</span><span class="sxs-lookup"><span data-stu-id="4c4eb-124">Created Intune policies that enforce:</span></span>
  - <span data-ttu-id="4c4eb-125">Разрешенные приложения.</span><span class="sxs-lookup"><span data-stu-id="4c4eb-125">Allowed apps.</span></span>
  - <span data-ttu-id="4c4eb-126">Шифрование устройств, чтобы предотвратить несанкционированный доступ.</span><span class="sxs-lookup"><span data-stu-id="4c4eb-126">Device encryption to help prevent unauthorized access.</span></span>
  - <span data-ttu-id="4c4eb-127">Шестизначный ПИН-код или пароль.</span><span class="sxs-lookup"><span data-stu-id="4c4eb-127">A six-digit PIN or password.</span></span>
  - <span data-ttu-id="4c4eb-128">Период неактивности и времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="4c4eb-128">An inactivity-timeout period.</span></span>
  - <span data-ttu-id="4c4eb-129">Антивирусная и вредоносная защита, а также обновления подписей с Защитник Windows на Windows 10 устройствах.</span><span class="sxs-lookup"><span data-stu-id="4c4eb-129">Antivirus and malware protection, and signature updates with Windows Defender on Windows 10 devices.</span></span>
  - <span data-ttu-id="4c4eb-130">Автоматические обновления на Windows 10 устройствах с последними обновлениями безопасности.</span><span class="sxs-lookup"><span data-stu-id="4c4eb-130">Automatic updates on Windows 10 devices that include the latest security updates.</span></span>
  - <span data-ttu-id="4c4eb-131">Нажатие сертификатов на управляемые устройства.</span><span class="sxs-lookup"><span data-stu-id="4c4eb-131">Pushing certificates to managed devices.</span></span>
  - <span data-ttu-id="4c4eb-p102">Четкое разделение корпоративных и личных данных. Пользователи или администраторы могут выборочно стирать корпоративные данные с устройства, не трогая личные данные, такие как рисунки, личные учетные записи электронной почты и личные файлы.</span><span class="sxs-lookup"><span data-stu-id="4c4eb-p102">A clear separation of business and personal data. Users or admins can selectively wipe corporate data from the device, while leaving personal data such as pictures, personal email accounts, and personal files untouched.</span></span>

<span data-ttu-id="4c4eb-134">Contoso зарегистрировала развернутые компьютеры и смартфоны и планшеты, добавив их в соответствующие группы устройств Intune.</span><span class="sxs-lookup"><span data-stu-id="4c4eb-134">Contoso enrolled deployed PCs and company-owned smartphones and tablets by adding them to the appropriate Intune device groups.</span></span> <span data-ttu-id="4c4eb-135">Они также создали программу BYOD для сотрудников для регистрации своих личных устройств.</span><span class="sxs-lookup"><span data-stu-id="4c4eb-135">They also established a BYOD program for employees to enroll their personal devices.</span></span> <span data-ttu-id="4c4eb-136">Зарегистрированные устройства получают политики Intune, что приводит к управляемым и защищенным устройствам и их приложениям.</span><span class="sxs-lookup"><span data-stu-id="4c4eb-136">Enrolled devices receive Intune policies, which results in managed and secured devices and their applications.</span></span> <span data-ttu-id="4c4eb-137">Устройства, которые не зарегистрированы, имеют политики управления мобильными приложениями (MAM), которые указывают разрешенные приложения.</span><span class="sxs-lookup"><span data-stu-id="4c4eb-137">Devices that aren't enrolled have Mobile Application Management (MAM) policies that specify allowed applications.</span></span>

<span data-ttu-id="4c4eb-138">Вот архитектура развертывания мобильных устройств Contoso.</span><span class="sxs-lookup"><span data-stu-id="4c4eb-138">Here is the Contoso mobile device management deployment architecture.</span></span>

![Инфраструктура развертывания для управления мобильными устройствами Contoso](../media/contoso-mdm/contoso-mdm-fig1.png)

## <a name="next-step"></a><span data-ttu-id="4c4eb-140">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="4c4eb-140">Next step</span></span>

<span data-ttu-id="4c4eb-141">Узнайте, как Contoso использует возможности защиты информации Microsoft 365 предприятия для классификации, идентификации и защиты важных цифровых активов в организации. [](contoso-info-protect.md)</span><span class="sxs-lookup"><span data-stu-id="4c4eb-141">Learn how Contoso uses the [information protection capabilities](contoso-info-protect.md) of Microsoft 365 for enterprise to classify, identify, and protect crucial digital assets across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="4c4eb-142">См. также</span><span class="sxs-lookup"><span data-stu-id="4c4eb-142">See also</span></span>

[<span data-ttu-id="4c4eb-143">Управление устройствами для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4c4eb-143">Device management for Microsoft 365</span></span>](device-management-roadmap-microsoft-365.md)

[<span data-ttu-id="4c4eb-144">Обзор Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="4c4eb-144">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="4c4eb-145">Руководства по лаборатории тестирования</span><span class="sxs-lookup"><span data-stu-id="4c4eb-145">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)

