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
f1.keywords:
- NOCSH
ms.author: greglin
ms.openlocfilehash: 53c38ba2e915cd439c8d7629bc7f9cd56ebc8647
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636679"
---
# <a name="phase-3-windows-10-enterprise"></a><span data-ttu-id="eb273-104">Этап 3. Windows 10 Корпоративная</span><span class="sxs-lookup"><span data-stu-id="eb273-104">Phase 3: Windows 10 Enterprise</span></span>

![Этап 3. Windows 10 Корпоративная](../media/deploy-foundation-infrastructure/win10enterprise_icon.png)

<span data-ttu-id="eb273-106">Microsoft 365 Enterprise включает Windows 10 Корпоративная, которая предоставляет вам инструменты для большей и надежной безопасности.</span><span class="sxs-lookup"><span data-stu-id="eb273-106">Microsoft 365 Enterprise includes Windows 10 Enterprise, which gives you the tools to do more and stay secure.</span></span> <span data-ttu-id="eb273-107">Windows 10 Корпоративная:</span><span class="sxs-lookup"><span data-stu-id="eb273-107">Windows 10 Enterprise:</span></span>

- <span data-ttu-id="eb273-108">**Интегрировано для простоты** работы облака, чтобы снизить сложность управления современной средой современного ИТ-устройств, независимо от размера.</span><span class="sxs-lookup"><span data-stu-id="eb273-108">**Is integrated for simplicity** - Harness the power of the cloud to help reduce the complexity of managing today's modern IT device environment, no matter the size.</span></span>
- <span data-ttu-id="eb273-109">**Обладает интеллектуальной безопасностью** — это самый безопасный выпуск Windows при использовании интеллектуальных средств обеспечения безопасности, предназначенных для совместной работы, чтобы обеспечить лучшую защиту Организации.</span><span class="sxs-lookup"><span data-stu-id="eb273-109">**Has intelligent security** - It's the most secure release of Windows ever, with intelligent security capabilities that are designed to work together to better protect your organization.</span></span>
- <span data-ttu-id="eb273-110">Удобство **и** совместная работа — разблокировка творческого и командного использования для обеспечения максимальной продуктивности работы и посторонних пользователей.</span><span class="sxs-lookup"><span data-stu-id="eb273-110">**Enables creativity and teamwork** - Unlocks creativity and teamwork to deliver the most productive experience that both users and IT will love.</span></span>

<span data-ttu-id="eb273-111">Вам потребуется ознакомиться с различными способами развертывания операционной системы Windows 10 и выбора подправности для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="eb273-111">You'll need to understand the different ways you can deploy the Windows 10 operating system and choose the right one for your organization.</span></span> <span data-ttu-id="eb273-112">В зависимости от вашей подписки на Microsoft 365 Enterprise существуют также службы и функции безопасности Windows 10, которые необходимо настроить для максимально возможного использования Windows 10.</span><span class="sxs-lookup"><span data-stu-id="eb273-112">Depending on your Microsoft 365 Enterprise subscription, there are also Windows 10 services and security features that you'll need to configure to get the most out of Windows 10.</span></span>

>[!Note]
><span data-ttu-id="eb273-113">Чтобы развернуть приложения Windows 10 Корпоративная и Microsoft 365 для предприятий и перейти на [современный компьютер](https://www.microsoft.com/microsoft-365/modern-desktop), ознакомьтесь со статьей [центр развертывания современных настольных систем](https://aka.ms/howtoshift).</span><span class="sxs-lookup"><span data-stu-id="eb273-113">To deploy both Windows 10 Enterprise and Microsoft 365 Apps for enterprise together and shift to a [modern desktop](https://www.microsoft.com/microsoft-365/modern-desktop), see the [Modern Desktop Deployment Center](https://aka.ms/howtoshift).</span></span>
>

## <a name="windows-10-deployment"></a><span data-ttu-id="eb273-114">Развертывание Windows 10</span><span class="sxs-lookup"><span data-stu-id="eb273-114">Windows 10 deployment</span></span>

<span data-ttu-id="eb273-115">Существует несколько способов развертывания Windows 10 Корпоративная для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="eb273-115">There are multiple ways you can deploy Windows 10 Enterprise for your organization.</span></span> <span data-ttu-id="eb273-116">В этой статье мы рассмотрим, как настраивать и развертывать образ Windows 10 Корпоративная с помощью современных сценариев развертывания.</span><span class="sxs-lookup"><span data-stu-id="eb273-116">Here, we'll focus on how you can configure and deploy a Windows 10 Enterprise image through these modern deployment scenarios.</span></span>

| <span data-ttu-id="eb273-117">Сценарий развертывания</span><span class="sxs-lookup"><span data-stu-id="eb273-117">Deployment scenario</span></span> | <span data-ttu-id="eb273-118">Когда его следует использовать</span><span class="sxs-lookup"><span data-stu-id="eb273-118">When to use it</span></span> |
|:--- |:--- |
| [<span data-ttu-id="eb273-119">Использование диспетчера конфигурации конечных точек Майкрософт в качестве обновления на месте</span><span class="sxs-lookup"><span data-stu-id="eb273-119">Using Microsoft Endpoint Configuration Manager as an in-place upgrade</span></span>](windows10-deploy-inplaceupgrade.md) | <span data-ttu-id="eb273-120">Выберите этот параметр, если необходимо обновить компьютеры с Windows 7 или Windows 8,1 до <a href="https://aka.ms/windows-10-release-information" target="_blank">текущей версии</a> Windows 10 Корпоративная, а компьютеры в настоящее время управляются с помощью <a href="https://docs.microsoft.com/configmgr/core/understand/introduction" target="_blank">Configuration Manager (текущей ветви)</a>.</span><span class="sxs-lookup"><span data-stu-id="eb273-120">Select this option if you need to upgrade Windows 7 or Windows 8.1 computers to the <a href="https://aka.ms/windows-10-release-information" target="_blank">current version</a> of Windows 10 Enterprise and your computers are currently managed with <a href="https://docs.microsoft.com/configmgr/core/understand/introduction" target="_blank">Configuration Manager (Current branch)</a>.</span></span> |
| [<span data-ttu-id="eb273-121">Использование автопилота Windows</span><span class="sxs-lookup"><span data-stu-id="eb273-121">Using Windows Autopilot</span></span>](windows10-deploy-autopilot.md) | <span data-ttu-id="eb273-122">Выберите этот вариант, если вы настраиваете новые компьютеры с Windows, на которых установлена операционная система Windows 10 корпоративная версии 1703 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="eb273-122">Select this option if you are setting up new Windows computers that have Windows 10 Enterprise, version 1703 or later pre-installed.</span></span> <span data-ttu-id="eb273-123">Конечные пользователи запускают программу установки, используя нужную конфигурацию, вводя свои учетные данные рабочей или учебной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="eb273-123">End users will initiate setup using your desired configuration by entering their work or school account credentials.</span></span> |

<span data-ttu-id="eb273-124">Если эти сценарии развертывания не соответствуют потребностям вашей организации, вы можете узнать о других сценариях и ознакомиться с возможностями и ограничениями каждого из [сценариев развертывания Windows 10](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios).</span><span class="sxs-lookup"><span data-stu-id="eb273-124">If these deployment scenarios do not fit the needs of your organization, you can learn about other scenarios and understand the capabilities and limitations of each in [Windows 10 deployment scenarios](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios).</span></span> <span data-ttu-id="eb273-125">Вы также можете <a href="https://aka.ms/planforwin10deployment" target="_blank">планировать развертывание Windows 10</a> самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="eb273-125">You can also <a href="https://aka.ms/planforwin10deployment" target="_blank">plan for Windows 10 deployment</a> on your own.</span></span>

<span data-ttu-id="eb273-126">Подробнее о Windows 10 можно узнать в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="eb273-126">You can learn more about Windows 10 with these articles:</span></span>

- [<span data-ttu-id="eb273-127">Страница продукта Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="eb273-127">Microsoft 365 Enterprise product page</span></span>](https://www.microsoft.com/microsoft-365/enterprise)
- [<span data-ttu-id="eb273-128">Windows 10</span><span class="sxs-lookup"><span data-stu-id="eb273-128">Windows 10</span></span>](https://docs.microsoft.com/windows/windows-10)
- [<span data-ttu-id="eb273-129">Развертывание и обновление Windows 10</span><span class="sxs-lookup"><span data-stu-id="eb273-129">Deploy and update Windows 10</span></span>](https://docs.microsoft.com/windows/deployment/)


## <a name="additional-services-and-features"></a><span data-ttu-id="eb273-130">Дополнительные службы и функции</span><span class="sxs-lookup"><span data-stu-id="eb273-130">Additional services and features</span></span>
<span data-ttu-id="eb273-131">В рамках развертывания Windows 10 Корпоративная вы можете добавить эти дополнительные службы и функции.</span><span class="sxs-lookup"><span data-stu-id="eb273-131">As part of your deployment of Windows 10 Enterprise, you can add these additional services and features.</span></span>

### <a name="windows-analytics"></a><span data-ttu-id="eb273-132">Windows Analytics</span><span class="sxs-lookup"><span data-stu-id="eb273-132">Windows Analytics</span></span>

<span data-ttu-id="eb273-133">В Windows используются диагностические данные для предоставления обширных сведений о действиях, которые помогут вам получить глубокие знания о работоспособности и работоспособности устройств с Windows 10 в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="eb273-133">Windows uses diagnostics data to provide rich, actionable information to help you gain deep insights into operational efficiency and the health of Windows 10 devices in your environment.</span></span>

* <span data-ttu-id="eb273-134">Готовность к обновлению — готовность к обновлению поможет перейти на Windows 10 и оставить новые обновления компонентов Windows 10.</span><span class="sxs-lookup"><span data-stu-id="eb273-134">Upgrade Readiness - Upgrade Readiness will help you move to Windows 10 and stay current with new Windows 10 Feature Updates.</span></span> 
* <span data-ttu-id="eb273-135">Обновление соответствия требованиям обновление предназначено для ИТ-администратора, желающих получить целостное представление всех своих устройств с Windows 10 без каких-либо дополнительных требований к инфраструктуре.</span><span class="sxs-lookup"><span data-stu-id="eb273-135">Update Compliance - Update Compliance is targeted to the IT admin who wants to gain a holistic view of all their Windows 10 devices, without any additional infrastructure requirements.</span></span>
* <span data-ttu-id="eb273-136">Работоспособность устройства — вы можете использовать проверку работоспособности устройств для профилактического обнаружения и устранения проблем, влияющих на пользователей.</span><span class="sxs-lookup"><span data-stu-id="eb273-136">Device Health - You can use Device Health to proactively detect and remediate end-user impacting issues.</span></span>

<span data-ttu-id="eb273-137">Более подробную информацию можно найти в статье [Windows Analytics Overview](https://docs.microsoft.com/windows/deployment/update/windows-analytics-overview) .</span><span class="sxs-lookup"><span data-stu-id="eb273-137">See [Windows Analytics Overview](https://docs.microsoft.com/windows/deployment/update/windows-analytics-overview) for more information.</span></span>

### <a name="windows-security"></a><span data-ttu-id="eb273-138">Безопасность Windows</span><span class="sxs-lookup"><span data-stu-id="eb273-138">Windows security</span></span>

<span data-ttu-id="eb273-139">Windows 10 предоставляет функции, помогающие защититься от угроз, а также обеспечивать безопасность устройств и помощь в управлении доступом.</span><span class="sxs-lookup"><span data-stu-id="eb273-139">Windows 10 provides features to help protect against threats, help you secure your devices, and help with access control.</span></span> <span data-ttu-id="eb273-140">С Windows 10 вы получаете важные функции безопасности, которые защищают ваше устройство от запуска.</span><span class="sxs-lookup"><span data-stu-id="eb273-140">With Windows 10, you get critical security features that protect your device right from the start.</span></span> <span data-ttu-id="eb273-141">Microsoft 365 E3 добавляет функции безопасности, такие как Windows Hello для бизнеса, Управление приложениями защитника Windows и Windows Information Protection.</span><span class="sxs-lookup"><span data-stu-id="eb273-141">Microsoft 365 E3 adds security features such as Windows Hello for Business, Windows Defender Application Control, and Windows Information Protection.</span></span> <span data-ttu-id="eb273-142">С помощью Microsoft 365 а вы получаете все функции защиты от Microsoft 365 E3 Security, а также функции безопасности на основе облака и Advanced Threat Protection в защитнике Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="eb273-142">With Microsoft 365 E5, you get all the protection from Microsoft 365 E3 security plus cloud-based security features and Microsoft Defender Advanced Threat Protection.</span></span> 

<span data-ttu-id="eb273-143">Дополнительные сведения о функциях обеспечения безопасности, которые вы получаете в Windows 10 Корпоративная, и рекомендации по развертыванию, управлению, настройке и устранению неполадок трех ключевых функций безопасности приведены в [шаге 5: развертывание компонентов безопасности Windows 10 Корпоративная](windows10-enable-security-features.md).</span><span class="sxs-lookup"><span data-stu-id="eb273-143">To learn more about the security features that you get with Windows 10 Enterprise and get guidance on how you can deploy, manage, configure, and troubleshoot three key security features, see [Step 5: Deploy Windows 10 Enterprise security features](windows10-enable-security-features.md).</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="eb273-144">Как корпорация Майкрософт реализует Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="eb273-144">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="eb273-145">Изучите Майкрософт и Узнайте, как компания [развернула Windows 10 Корпоративная и использует надежную проверку подлинности, Intune и пакет ATP для защитника Майкрософт](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR6).</span><span class="sxs-lookup"><span data-stu-id="eb273-145">Peek inside Microsoft and learn how the company [deployed Windows 10 Enterprise and is using strong authentication, Intune, and Microsoft Defender ATP](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR6).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="eb273-146">Как корпорация Contoso реализовала Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="eb273-146">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="eb273-147">Узнайте, как Корпорация Contoso, вымышленная, но предопределяющая многонациональная организация, [развернута Windows 10 Корпоративная](contoso-win10.md).</span><span class="sxs-lookup"><span data-stu-id="eb273-147">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed Windows 10 Enterprise](contoso-win10.md).</span></span>

![Корпорация Contoso](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="eb273-149">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="eb273-149">Next step</span></span>

|||
|:-------|:-----|
|![Шаг 1](../media/stepnumbers/Step1.png)| [<span data-ttu-id="eb273-151">Подготовка Организации к работе с Windows 10 Корпоративная</span><span class="sxs-lookup"><span data-stu-id="eb273-151">Prepare your organization for Windows 10 Enterprise</span></span>](windows10-prepare-your-org.md) |
