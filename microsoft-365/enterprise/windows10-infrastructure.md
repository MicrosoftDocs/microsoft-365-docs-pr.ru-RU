---
title: Инфраструктура Windows 10 Корпоративная для Microsoft 365 корпоративный
description: Предоставляет высокоуровневое руководство по этапам, необходимым для развертывания Windows 10 Корпоративная на компьютерах в составе Microsoft 365 корпоративный.
keywords: Microsoft 365, Microsoft 365 корпоративный, документация по Microsoft 365, Windows 10 Корпоративная, развертывание
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/28/2019
ms.author: greglin
ms.openlocfilehash: 0b98e48b128eeaea0e0dd5cb9613ece95e991861
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2019
ms.locfileid: "36982750"
---
# <a name="phase-3-windows-10-enterprise"></a><span data-ttu-id="23db1-104">Шаг 3. Windows 10 Корпоративная</span><span class="sxs-lookup"><span data-stu-id="23db1-104">Phase 3: Windows 10 Enterprise</span></span>

![](./media/deploy-foundation-infrastructure/win10enterprise_icon.png)

<span data-ttu-id="23db1-105">Microsoft 365 Enterprise включает Windows 10 Корпоративная, которая предоставляет вам инструменты для большей и надежной безопасности.</span><span class="sxs-lookup"><span data-stu-id="23db1-105">Microsoft 365 Enterprise includes Windows 10 Enterprise, which gives you the tools to do more and stay secure.</span></span> <span data-ttu-id="23db1-106">Windows 10 Корпоративная:</span><span class="sxs-lookup"><span data-stu-id="23db1-106">Windows 10 Enterprise:</span></span>

- <span data-ttu-id="23db1-107">**Интегрировано для простоты** работы облака, чтобы снизить сложность управления современной средой современного ИТ-устройств, независимо от размера.</span><span class="sxs-lookup"><span data-stu-id="23db1-107">**Is integrated for simplicity** - Harness the power of the cloud to help reduce the complexity of managing today's modern IT device environment, no matter the size.</span></span>
- <span data-ttu-id="23db1-108">**Обладает интеллектуальной безопасностью** — это самый безопасный выпуск Windows при использовании интеллектуальных средств обеспечения безопасности, предназначенных для совместной работы, чтобы обеспечить лучшую защиту Организации.</span><span class="sxs-lookup"><span data-stu-id="23db1-108">**Has intelligent security** - It's the most secure release of Windows ever, with intelligent security capabilities that are designed to work together to better protect your organization.</span></span>
- <span data-ttu-id="23db1-109">Удобство **и** совместная работа — разблокировка творческого и командного использования для обеспечения максимальной продуктивности работы и посторонних пользователей.</span><span class="sxs-lookup"><span data-stu-id="23db1-109">**Enables creativity and teamwork** - Unlocks creativity and teamwork to deliver the most productive experience that both users and IT will love.</span></span>

<span data-ttu-id="23db1-110">Вам потребуется ознакомиться с различными способами развертывания операционной системы Windows 10 и выбора подправности для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="23db1-110">You'll need to understand the different ways you can deploy the Windows 10 operating system and choose the right one for your organization.</span></span> <span data-ttu-id="23db1-111">В зависимости от вашей подписки на Microsoft 365 Enterprise существуют также службы и функции безопасности Windows 10, которые необходимо настроить для максимально возможного использования Windows 10.</span><span class="sxs-lookup"><span data-stu-id="23db1-111">Depending on your Microsoft 365 Enterprise subscription, there are also Windows 10 services and security features that you'll need to configure to get the most out of Windows 10.</span></span>

>[!Note]
><span data-ttu-id="23db1-112">Для развертывания Windows 10 Корпоративная и Office 365 профессиональный плюс вместе, а также перехода пользователей на [современные компьютеры](https://www.microsoft.com/microsoft-365/modern-desktop) см. статью [Центр развертывания современных компьютеров](http://aka.ms/howtoshift).</span><span class="sxs-lookup"><span data-stu-id="23db1-112">To deploy both Windows 10 Enterprise and Office 365 ProPlus together and shift to a [modern desktop](https://www.microsoft.com/microsoft-365/modern-desktop), see the [Modern Desktop Deployment Center](http://aka.ms/howtoshift).</span></span>
>

## <a name="windows-10-deployment"></a><span data-ttu-id="23db1-113">Развертывание Windows 10</span><span class="sxs-lookup"><span data-stu-id="23db1-113">Windows 10 deployment</span></span>

<span data-ttu-id="23db1-114">Существует несколько способов развертывания Windows 10 Корпоративная для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="23db1-114">There are multiple ways you can deploy Windows 10 Enterprise for your organization.</span></span> <span data-ttu-id="23db1-115">В этой статье мы рассмотрим, как настраивать и развертывать образ Windows 10 Корпоративная с помощью современных сценариев развертывания.</span><span class="sxs-lookup"><span data-stu-id="23db1-115">Here, we'll focus on how you can configure and deploy a Windows 10 Enterprise image through these modern deployment scenarios.</span></span>

| <span data-ttu-id="23db1-116">Сценарий развертывания</span><span class="sxs-lookup"><span data-stu-id="23db1-116">Deployment scenario</span></span> | <span data-ttu-id="23db1-117">Когда его следует использовать</span><span class="sxs-lookup"><span data-stu-id="23db1-117">When to use it</span></span> |
|:--- |:--- |
| [<span data-ttu-id="23db1-118">Использование System Center Configuration Manager в качестве обновления на месте</span><span class="sxs-lookup"><span data-stu-id="23db1-118">Using System Center Configuration Manager as an in-place upgrade</span></span>](windows10-deploy-inplaceupgrade.md) | <span data-ttu-id="23db1-119">Выберите этот параметр, если необходимо обновить компьютеры с Windows 7 или Windows 8,1 до <a href="https://aka.ms/windows-10-release-information" target="_blank">текущей версии</a> Windows 10 Корпоративная, а компьютеры в настоящее время управляются с помощью <a href="https://aka.ms/introtosccm" target="_blank">System Center Configuration Manager (Текущая ветвь)</a>.</span><span class="sxs-lookup"><span data-stu-id="23db1-119">Select this option if you need to upgrade Windows 7 or Windows 8.1 computers to the <a href="https://aka.ms/windows-10-release-information" target="_blank">current version</a> of Windows 10 Enterprise and your computers are currently managed with <a href="https://aka.ms/introtosccm" target="_blank">System Center Configuration Manager (Current branch)</a>.</span></span> |
| [<span data-ttu-id="23db1-120">Использование автопилота Windows</span><span class="sxs-lookup"><span data-stu-id="23db1-120">Using Windows Autopilot</span></span>](windows10-deploy-autopilot.md) | <span data-ttu-id="23db1-121">Выберите этот вариант, если вы настраиваете новые компьютеры с Windows, на которых установлена операционная система Windows 10 корпоративная версии 1703 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="23db1-121">Select this option if you are setting up new Windows computers that have Windows 10 Enterprise, version 1703 or later pre-installed.</span></span> <span data-ttu-id="23db1-122">Конечные пользователи запускают программу установки, используя нужную конфигурацию, вводя свои учетные данные рабочей или учебной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="23db1-122">End users will initiate setup using your desired configuration by entering their work or school account credentials.</span></span> |

<span data-ttu-id="23db1-123">Если эти сценарии развертывания не соответствуют потребностям вашей организации, вы можете узнать о других сценариях и ознакомиться с возможностями и ограничениями каждого из [сценариев развертывания Windows 10](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios).</span><span class="sxs-lookup"><span data-stu-id="23db1-123">If these deployment scenarios do not fit the needs of your organization, you can learn about other scenarios and understand the capabilities and limitations of each in [Windows 10 deployment scenarios](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios).</span></span> <span data-ttu-id="23db1-124">Вы также можете <a href="https://aka.ms/planforwin10deployment" target="_blank">спланировать развертывание Windows 10</a> самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="23db1-124">You can also <a href="https://aka.ms/planforwin10deployment" target="_blank">plan for Windows 10 deployment</a> on your own.</span></span>

<span data-ttu-id="23db1-125">Подробнее о Windows 10 можно узнать в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="23db1-125">You can learn more about Windows 10 with these articles:</span></span>

- [<span data-ttu-id="23db1-126">Страница продукта Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="23db1-126">Microsoft 365 Enterprise product page</span></span>](https://www.microsoft.com/microsoft-365/enterprise)
- [<span data-ttu-id="23db1-127">Windows 10</span><span class="sxs-lookup"><span data-stu-id="23db1-127">Windows 10</span></span>](https://docs.microsoft.com/windows/windows-10)
- [<span data-ttu-id="23db1-128">Развертывание и обновление Windows 10</span><span class="sxs-lookup"><span data-stu-id="23db1-128">Deploy and update Windows 10</span></span>](https://docs.microsoft.com/windows/deployment/)


## <a name="additional-services-and-features"></a><span data-ttu-id="23db1-129">Дополнительные службы и функции</span><span class="sxs-lookup"><span data-stu-id="23db1-129">Additional services and features</span></span>
<span data-ttu-id="23db1-130">В рамках развертывания Windows 10 Корпоративная вы можете добавить эти дополнительные службы и функции.</span><span class="sxs-lookup"><span data-stu-id="23db1-130">As part of your deployment of Windows 10 Enterprise, you can add these additional services and features.</span></span>

### <a name="windows-analytics"></a><span data-ttu-id="23db1-131">Windows Analytics</span><span class="sxs-lookup"><span data-stu-id="23db1-131">Windows Analytics</span></span>

<span data-ttu-id="23db1-132">В Windows используются диагностические данные для предоставления обширных сведений о действиях, которые помогут вам получить глубокие знания о работоспособности и работоспособности устройств с Windows 10 в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="23db1-132">Windows uses diagnostics data to provide rich, actionable information to help you gain deep insights into operational efficiency and the health of Windows 10 devices in your environment.</span></span>

* <span data-ttu-id="23db1-133">Готовность к обновлению — готовность к обновлению поможет перейти на Windows 10 и оставить новые обновления компонентов Windows 10.</span><span class="sxs-lookup"><span data-stu-id="23db1-133">Upgrade Readiness - Upgrade Readiness will help you move to Windows 10 and stay current with new Windows 10 Feature Updates.</span></span> 
* <span data-ttu-id="23db1-134">Обновление соответствия требованиям обновление предназначено для ИТ-администратора, желающих получить целостное представление всех своих устройств с Windows 10 без каких-либо дополнительных требований к инфраструктуре.</span><span class="sxs-lookup"><span data-stu-id="23db1-134">Update Compliance - Update Compliance is targeted to the IT admin who wants to gain a holistic view of all their Windows 10 devices, without any additional infrastructure requirements.</span></span>
* <span data-ttu-id="23db1-135">Работоспособность устройства — вы можете использовать проверку работоспособности устройств для профилактического обнаружения и устранения проблем, влияющих на пользователей.</span><span class="sxs-lookup"><span data-stu-id="23db1-135">Device Health - You can use Device Health to proactively detect and remediate end-user impacting issues.</span></span>

<span data-ttu-id="23db1-136">Более подробную информацию можно найти в статье [Windows Analytics Overview](https://docs.microsoft.com/windows/deployment/update/windows-analytics-overview) .</span><span class="sxs-lookup"><span data-stu-id="23db1-136">See [Windows Analytics Overview](https://docs.microsoft.com/windows/deployment/update/windows-analytics-overview) for more information.</span></span>

### <a name="windows-security"></a><span data-ttu-id="23db1-137">Безопасность Windows</span><span class="sxs-lookup"><span data-stu-id="23db1-137">Windows security</span></span>

<span data-ttu-id="23db1-138">Windows 10 предоставляет функции, помогающие защититься от угроз, а также обеспечивать безопасность устройств и помощь в управлении доступом.</span><span class="sxs-lookup"><span data-stu-id="23db1-138">Windows 10 provides features to help protect against threats, help you secure your devices, and help with access control.</span></span> <span data-ttu-id="23db1-139">С Windows 10 вы получаете важные функции безопасности, которые защищают ваше устройство от запуска.</span><span class="sxs-lookup"><span data-stu-id="23db1-139">With Windows 10, you get critical security features that protect your device right from the start.</span></span> <span data-ttu-id="23db1-140">Microsoft 365 E3 добавляет функции безопасности, такие как Windows Hello для бизнеса, Управление приложениями защитника Windows и Windows Information Protection.</span><span class="sxs-lookup"><span data-stu-id="23db1-140">Microsoft 365 E3 adds security features such as Windows Hello for Business, Windows Defender Application Control, and Windows Information Protection.</span></span> <span data-ttu-id="23db1-141">С помощью Microsoft 365 а вы получаете все функции защиты от Microsoft 365 E3 Security, а также функции безопасности на основе облака и Advanced Threat Protection в защитнике Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="23db1-141">With Microsoft 365 E5, you get all the protection from Microsoft 365 E3 security plus cloud-based security features and Microsoft Defender Advanced Threat Protection.</span></span> 

<span data-ttu-id="23db1-142">Чтобы узнать больше о возможностях обеспечения безопасности, которые вы получаете в Windows 10 Корпоративная, и ознакомьтесь с указаниями по развертыванию, управлению, настройке и устранению неполадок трех основных функций екурити, описанных в разделе [Шаг 5: развертывание компонентов безопасности Windows 10 Корпоративная](windows10-enable-security-features.md).</span><span class="sxs-lookup"><span data-stu-id="23db1-142">To learn more about the security features that you get with Windows 10 Enterprise and get guidance on how you can deploy, manage, configure, and troubleshoot three key ecurity features, see [Step 5: Deploy Windows 10 Enterprise security features](windows10-enable-security-features.md).</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="23db1-143">Как корпорация Майкрософт реализует Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="23db1-143">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="23db1-144">Изучите Майкрософт и Узнайте, как компания [развернула Windows 10 Корпоративная и использует надежную проверку подлинности, Intune и пакет ATP для защитника Майкрософт](https://www.microsoft.com/en-us/itshowcase/deploying-and-managing-microsoft-365#primaryR6).</span><span class="sxs-lookup"><span data-stu-id="23db1-144">Peek inside Microsoft and learn how the company [deployed Windows 10 Enterprise and is using strong authentication, Intune, and Microsoft Defender ATP](https://www.microsoft.com/en-us/itshowcase/deploying-and-managing-microsoft-365#primaryR6).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="23db1-145">Как корпорация Contoso реализовала Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="23db1-145">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="23db1-146">Узнайте, как Корпорация Contoso, вымышленная, но предопределяющая многонациональная организация, [развернута Windows 10 Корпоративная](contoso-win10.md).</span><span class="sxs-lookup"><span data-stu-id="23db1-146">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed Windows 10 Enterprise](contoso-win10.md).</span></span>

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="23db1-147">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="23db1-147">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="23db1-148">Подготовка Организации к работе с Windows 10 Корпоративная</span><span class="sxs-lookup"><span data-stu-id="23db1-148">Prepare your organization for Windows 10 Enterprise</span></span>](windows10-prepare-your-org.md) |
