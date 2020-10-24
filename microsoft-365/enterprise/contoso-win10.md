---
title: Развертывание Windows 10 Корпоративная для компании Contoso
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
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: В этой статье рассказано, как в компании Contoso использовали Microsoft Endpoint Configuration Manager для развертывания обновлений на месте для Windows 10 Корпоративная.
ms.openlocfilehash: 0543f24665048d0679bc1b099fdd0a2d431c1e54
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754255"
---
# <a name="windows-10-enterprise-deployment-for-contoso"></a><span data-ttu-id="dc310-103">Развертывание Windows 10 Корпоративная для компании Contoso</span><span class="sxs-lookup"><span data-stu-id="dc310-103">Windows 10 Enterprise deployment for Contoso</span></span>

<span data-ttu-id="dc310-p101">Перед широким развертыванием Microsoft 365 для предприятий компания Contoso представила компьютеры и устройства, совместимые с Windows, с сочетанием Windows 7 (10%), Windows 8,1 (65%) и Windows 10 (25%). Компания Contoso хотели обновить свои компьютеры для Windows 10 Корпоративная, воспользоваться преимуществами расширенной безопасности и сниженными затратами на ИТ от автоматизированных развертываний обновлений.</span><span class="sxs-lookup"><span data-stu-id="dc310-p101">Prior to the wide rollout of Microsoft 365 for enterprise, Contoso had Windows-compatible PCs and devices running a mixture of Windows 7 (10%), Windows 8.1 (65%), and Windows 10 (25%). Contoso wanted to upgrade their PCs for Windows 10 Enterprise take advantage of advanced security and lowered IT overhead from automated deployments of updates.</span></span> 

<span data-ttu-id="dc310-106">Оценив инфраструктуру и бизнес-потребности, специалисты компании Contoso определили перечисленные ниже основные требования к развертыванию.</span><span class="sxs-lookup"><span data-stu-id="dc310-106">After assessing their infrastructure and business needs, Contoso identified these key requirements for the deployment:</span></span>

- <span data-ttu-id="dc310-107">ОС Windows 10 Корпоративная следует использовать на максимально возможном количестве устройств.</span><span class="sxs-lookup"><span data-stu-id="dc310-107">As many PCs and devices as possible should run Windows 10 Enterprise</span></span>
- <span data-ttu-id="dc310-108">При развертывании обновлений на месте используется существующая инфраструктура Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="dc310-108">Rollout of the in-place upgrades leverages existing Configuration Manager infrastructure</span></span>
- <span data-ttu-id="dc310-109">Необходима возможность выбирать версии развертываемой ОС Windows 10 Корпоративная и обновлений с помощью кругов.</span><span class="sxs-lookup"><span data-stu-id="dc310-109">Control over which versions of Windows 10 Enterprise to deploy and updates are done through rings</span></span>
- <span data-ttu-id="dc310-110">ПК и устройства всегда должны быть в актуальном состоянии, и это должно сопровождаться минимальными издержками на ИТ-администрирование. При этом процесс получения и установки обновлений не должен причинять заметные неудобства пользователям.</span><span class="sxs-lookup"><span data-stu-id="dc310-110">PCs and devices should stay up to date with minimal IT administrative costs and with minimal impact to end-users</span></span>

<span data-ttu-id="dc310-111">Под актуальным состоянием понимается поддерживаемая версия Windows 10 Корпоративная, которая соответствует бизнес-потребностям компании Contoso. При этом, возможно, не обязательно использовать последнюю версию Windows 10 Корпоративная на всех ПК, совместимых с ОС Windows.</span><span class="sxs-lookup"><span data-stu-id="dc310-111">Up to date is defined as the supported version of Windows 10 Enterprise that meets Contoso’s business needs, which can be different from having all Windows-compatible PCs running the latest version of Windows 10 Enterprise.</span></span>

## <a name="deployment-tools"></a><span data-ttu-id="dc310-112">Средства развертывания</span><span class="sxs-lookup"><span data-stu-id="dc310-112">Deployment tools</span></span>

<span data-ttu-id="dc310-113">До обновления Windows 10 Корпоративная на месте и в процессе такого обновления в компании Contoso использовали указанные ниже решения Windows Analytics.</span><span class="sxs-lookup"><span data-stu-id="dc310-113">Prior to and during in-place upgrades of Windows 10 Enterprise, Contoso used the following solutions of Windows Analytics:</span></span>

- <span data-ttu-id="dc310-114">Проверка готовности к обновлению</span><span class="sxs-lookup"><span data-stu-id="dc310-114">Upgrade Readiness</span></span>  

  <span data-ttu-id="dc310-115">Это средство собирает данные о системе, приложениях и драйверах для анализа, а затем находит проблемы совместимости, из-за которых, возможно, не удастся выполнить обновление, и предлагает решения этих проблем, известные корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="dc310-115">Collects system, application, and driver data for analysis, and then identifies compatibility issues that can block an upgrade and suggested fixes the issues are known to Microsoft.</span></span>

- <span data-ttu-id="dc310-116">Поддержка обновлений</span><span class="sxs-lookup"><span data-stu-id="dc310-116">Update Compliance</span></span>  

  <span data-ttu-id="dc310-117">Здесь отображается состояние ваших устройств с учетом обновлений Windows, чтобы вы могли убедиться в том, что ваши устройства имеют наиболее актуальные необходимые обновления.</span><span class="sxs-lookup"><span data-stu-id="dc310-117">Shows you the state of your devices with respect to the Windows updates so that you can ensure that they are on the most current updates as appropriate.</span></span>

- <span data-ttu-id="dc310-118">Работоспособность устройств</span><span class="sxs-lookup"><span data-stu-id="dc310-118">Device Health</span></span>  

  <span data-ttu-id="dc310-119">Выявляет устройства, которые часто выходят из строя, и, следовательно, нуждаются в модернизации или замене, а также драйверы устройств, которые вызывают сбои устройств, предлагая альтернативные версии таких драйверов, что может способствовать снижению количества сбоев.</span><span class="sxs-lookup"><span data-stu-id="dc310-119">Identifies devices that crash frequently, and therefore might need to be rebuilt or replaced and device drivers that are causing device crashes, with suggestions of alternative versions of those drivers that might reduce the number of crashes.</span></span> <span data-ttu-id="dc310-120">Предоставляет уведомление о неправильных конфигурациях Windows Information Protection, которые отправляют запросы пользователям.</span><span class="sxs-lookup"><span data-stu-id="dc310-120">Provides notification of Windows Information Protection misconfigurations that send prompts to end users.</span></span>
 
<span data-ttu-id="dc310-p103">В компании Contoso уже имеется инфраструктура Configuration Manager (Current Branch). Configuration Manager выполняет масштабирование для крупных сред и обеспечивает всесторонний контроль над установкой, обновлениями и параметрами. Кроме того, он оснащен функциями, которые упрощают и повышают эффективность развертывания ОС Windows 10 Корпоративная и управления ею.</span><span class="sxs-lookup"><span data-stu-id="dc310-p103">Contoso has an existing Configuration Manager (Current Branch) infrastructure. Configuration Manager scales for large environments and provides extensive control over installation, updates, and settings. It also has built-in features to make it easier and more efficient to deploy and manage Windows 10 Enterprise.</span></span>

## <a name="planning-process"></a><span data-ttu-id="dc310-124">Процесс планирования</span><span class="sxs-lookup"><span data-stu-id="dc310-124">Planning process</span></span>

<span data-ttu-id="dc310-125">Компания Contoso использовала готовность к обновлению в Windows Analytics, чтобы определить набор установленных приложений и их совместимость с Windows 10 Корпоративная.</span><span class="sxs-lookup"><span data-stu-id="dc310-125">Contoso used the Upgrade Readiness in Windows Analytics to determine the set of installed apps and their compatibility with Windows 10 Enterprise.</span></span>

## <a name="deployment-process"></a><span data-ttu-id="dc310-126">Процесс развертывания</span><span class="sxs-lookup"><span data-stu-id="dc310-126">Deployment process</span></span>

<span data-ttu-id="dc310-127">Чтобы выполнить развертывание обновлений на месте для ОС Windows 10 Корпоративная, в компании Contoso реализовали указанный ниже процесс с использованием рекомендаций корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="dc310-127">To complete the in-place upgrade deployment of Windows 10 Enterprise, Contoso implemented the following process, which includes best practice recommendations from Microsoft:</span></span>

1. <span data-ttu-id="dc310-128">Был включен одноранговый кэш для Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="dc310-128">Enabled peer cache for Configuration Manager.</span></span>
2. <span data-ttu-id="dc310-129">На основе образов, полученных из Volume Licensing Service Center, были созданы специальные пакеты Windows.</span><span class="sxs-lookup"><span data-stu-id="dc310-129">Created customized Windows packages based on images from the Volume Licensing Service Center.</span></span>
3. <span data-ttu-id="dc310-130">Диспетчер конфигураций используется для развертывания пакетов Windows в точках распространения в их сети и развернутых сборках в соответствии с тремя промежуточными группами проверки и развертывания.</span><span class="sxs-lookup"><span data-stu-id="dc310-130">Used Configuration Manager to deploy the Windows packages to distribution points across their network and deployed builds to the three validation and deployment staging groups.</span></span>
4. <span data-ttu-id="dc310-131">Была выполнена оценка успешности развертывания для ПК и устройств в трех кругах поэтапного выполнения процессов проверки и развертывания с использованием решений "Работоспособность устройств" и "Поддержка обновлений" в Windows Analytics.</span><span class="sxs-lookup"><span data-stu-id="dc310-131">Performed assessment of success for PCs and devices in the three validation and deployment staging rings using the Device Health and Update Compliance solutions of Windows Analytics.</span></span>
5. <span data-ttu-id="dc310-132">На основе данных Windows Analytics компания Contoso определила версию Windows 10 Корпоративная для развертывания в обширную группу развертывания.</span><span class="sxs-lookup"><span data-stu-id="dc310-132">Based on the Windows Analytics information, Contoso determined the version of Windows 10 Enterprise to deploy to the broad deployment group.</span></span>
6. <span data-ttu-id="dc310-133">Запустила последовательности задач развертывания Configuration Manager, чтобы развернуть выбранный пакет Windows в обширную группу развертывания.</span><span class="sxs-lookup"><span data-stu-id="dc310-133">Ran the Configuration Manager deployment task sequences to deploy the selected Windows package to the broad deployment group.</span></span>
7. <span data-ttu-id="dc310-134">Мониторинг компьютеров и устройств в обширной группе развертывания с помощью решений по обеспечению работоспособности и обновления соответствия требованиям для устранения проблем.</span><span class="sxs-lookup"><span data-stu-id="dc310-134">Monitored PCs and devices in the broad deployment group using the Device Health and Update Compliance solutions to address issues.</span></span>

<span data-ttu-id="dc310-135">Здесь показана архитектура развертывания обновлений на месте и текущих обновлений.</span><span class="sxs-lookup"><span data-stu-id="dc310-135">Here is Contoso’s in-place upgrade and ongoing updates deployment architecture.</span></span>

![Инфраструктура развертывания ОС Windows 10 Корпоративная в компании Contoso](../media/contoso-win10/contoso-win10-fig1.png)

<span data-ttu-id="dc310-137">Эта инфраструктура состоит из указанных ниже элементов.</span><span class="sxs-lookup"><span data-stu-id="dc310-137">This infrastructure consists of:</span></span>

- <span data-ttu-id="dc310-138">Configuration Manager, который:</span><span class="sxs-lookup"><span data-stu-id="dc310-138">Configuration Manager, which:</span></span>
  - <span data-ttu-id="dc310-139">Получает образы для пакетов Windows 10 Корпоративная из Microsoft Volume Licensing Center в сети Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="dc310-139">Obtains images for Windows 10 Enterprise packages from the Microsoft Volume Licensing Center in the Microsoft Network.</span></span>
  - <span data-ttu-id="dc310-140">Является центральной точкой администрирования при развертывании пакетов.</span><span class="sxs-lookup"><span data-stu-id="dc310-140">Is the central administration point for deployment packages.</span></span>
- <span data-ttu-id="dc310-141">Региональные точки распределения, которые обычно расположены в региональных офисах компании Contoso.</span><span class="sxs-lookup"><span data-stu-id="dc310-141">Regional distribution points that are typically located in Contoso’s regional hub offices.</span></span>
- <span data-ttu-id="dc310-142">Компьютеры и устройства Windows в различных расположениях, которые получают и устанавливают пакеты развертывания для обновления на месте или текущих обновлений в соответствии с членством в группе.</span><span class="sxs-lookup"><span data-stu-id="dc310-142">Windows PCs and devices in various locations that receive and install the deployment packages for the in-place upgrade or ongoing updates based on group membership.</span></span>

## <a name="next-step"></a><span data-ttu-id="dc310-143">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="dc310-143">Next step</span></span>

<span data-ttu-id="dc310-144">Узнайте, как компания Contoso работает с инфраструктурой Configuration Manager, чтобы [развернуть и сохранить текущие приложения Microsoft 365 для предприятий](contoso-o365pp.md) в своей организации.</span><span class="sxs-lookup"><span data-stu-id="dc310-144">Learn how Contoso is leveraging its Configuration Manager infrastructure to [deploy and keep current Microsoft 365 Apps for enterprise](contoso-o365pp.md) across its organization.</span></span> 

## <a name="see-also"></a><span data-ttu-id="dc310-145">Дополнительные ресурсы:</span><span class="sxs-lookup"><span data-stu-id="dc310-145">See also</span></span>

[<span data-ttu-id="dc310-146">Windows 10 Корпоративная</span><span class="sxs-lookup"><span data-stu-id="dc310-146">Windows 10 Enterprise</span></span>](https://docs.microsoft.com/windows/deployment/)

[<span data-ttu-id="dc310-147">Обзор Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="dc310-147">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="dc310-148">Руководства по лаборатории тестирования</span><span class="sxs-lookup"><span data-stu-id="dc310-148">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
