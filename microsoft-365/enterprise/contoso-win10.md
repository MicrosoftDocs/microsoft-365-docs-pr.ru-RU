---
title: Развертывание Windows 10 Корпоративная для компании Contoso
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: В этой статье рассказано, как в компании Contoso использовали Microsoft Endpoint Configuration Manager для развертывания обновлений на месте для Windows 10 Корпоративная.
ms.openlocfilehash: a36e933d31ac6d629b649f07d6b8c9a4fe950ec8
ms.sourcegitcommit: 1d376287f6c1bf5174873e89ed4bf7bb15bc13f6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "38627335"
---
# <a name="windows-10-enterprise-deployment-for-contoso"></a><span data-ttu-id="a4cfa-103">Развертывание Windows 10 Корпоративная для компании Contoso</span><span class="sxs-lookup"><span data-stu-id="a4cfa-103">Windows 10 Enterprise deployment for Contoso</span></span>

<span data-ttu-id="a4cfa-104">**Сводка.** В этой статье рассказано, как в компании Contoso использовали Microsoft Endpoint Configuration Manager для развертывания обновлений на месте для Windows 10 Корпоративная.</span><span class="sxs-lookup"><span data-stu-id="a4cfa-104">**Summary:** Understand how Contoso used System Center Configuration Manager to deploy in-place upgrades for Windows 10 Enterprise.</span></span>

<span data-ttu-id="a4cfa-p101">До момента выпуска решения Microsoft 365 корпоративный, доступного широкому кругу пользователей, в компании Contoso использовали ПК и устройства, совместимые с ОС Windows. На них были установлены следующие ОС: Windows 7 (10 %), Windows 8.1 (65 %) и Windows 10 (25 %). В компании хотели обновить ПК, чтобы воспользоваться преимуществами, предоставляемыми Windows 10 Корпоративная. Эти преимущества включают возможность повысить уровень безопасности и уменьшить издержки на ИТ-инфраструктуру благодаря системе автоматизированного развертывания обновлений.</span><span class="sxs-lookup"><span data-stu-id="a4cfa-p101">Prior to the wide rollout of Microsoft 365 Enterprise, Contoso had Windows-compatible PCs and devices running a mixture of Windows 7 (10%), Windows 8.1 (65%), and Windows 10 (25%). Contoso wanted to upgrade their PCs for Windows 10 Enterprise take advantage of advanced security and lowered IT overhead from automated deployments of updates.</span></span> 

<span data-ttu-id="a4cfa-107">Оценив инфраструктуру и бизнес-потребности, специалисты компании Contoso определили перечисленные ниже основные требования к развертыванию.</span><span class="sxs-lookup"><span data-stu-id="a4cfa-107">After assessing their infrastructure and business needs, Contoso identified these key requirements for the deployment:</span></span>

- <span data-ttu-id="a4cfa-108">ОС Windows 10 Корпоративная следует использовать на максимально возможном количестве устройств.</span><span class="sxs-lookup"><span data-stu-id="a4cfa-108">As many PCs and devices as possible should run Windows 10 Enterprise</span></span>
- <span data-ttu-id="a4cfa-109">При развертывании обновлений на месте используется существующая инфраструктура Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="a4cfa-109">Rollout of the in-place upgrades leverages existing System Center Configuration Manager infrastructure</span></span>
- <span data-ttu-id="a4cfa-110">Необходима возможность выбирать версии развертываемой ОС Windows 10 Корпоративная и обновлений с помощью кругов.</span><span class="sxs-lookup"><span data-stu-id="a4cfa-110">Control over which versions of Windows 10 Enterprise to deploy and updates are done through rings</span></span>
- <span data-ttu-id="a4cfa-111">ПК и устройства всегда должны быть в актуальном состоянии, и это должно сопровождаться минимальными издержками на ИТ-администрирование. При этом процесс получения и установки обновлений не должен причинять заметные неудобства пользователям.</span><span class="sxs-lookup"><span data-stu-id="a4cfa-111">PCs and devices should stay up to date with minimal IT administrative costs and with minimal impact to end-users</span></span>

<span data-ttu-id="a4cfa-112">Под актуальным состоянием понимается поддерживаемая версия Windows 10 Корпоративная, которая соответствует бизнес-потребностям компании Contoso. При этом, возможно, не обязательно использовать последнюю версию Windows 10 Корпоративная на всех ПК, совместимых с ОС Windows.</span><span class="sxs-lookup"><span data-stu-id="a4cfa-112">Up to date is defined as the supported version of Windows 10 Enterprise that meets Contoso’s business needs, which can be different from having all Windows-compatible PCs running the latest version of Windows 10 Enterprise.</span></span>

## <a name="deployment-tools"></a><span data-ttu-id="a4cfa-113">Средства развертывания</span><span class="sxs-lookup"><span data-stu-id="a4cfa-113">Deployment tools</span></span>

<span data-ttu-id="a4cfa-114">До обновления Windows 10 Корпоративная на месте и в процессе такого обновления в компании Contoso использовали указанные ниже решения Windows Analytics.</span><span class="sxs-lookup"><span data-stu-id="a4cfa-114">Prior to and during in-place upgrades of Windows 10 Enterprise, Contoso used the following solutions of Windows Analytics:</span></span>

- <span data-ttu-id="a4cfa-115">Проверка готовности к обновлению</span><span class="sxs-lookup"><span data-stu-id="a4cfa-115">Upgrade Readiness</span></span>  

  <span data-ttu-id="a4cfa-116">Это средство собирает данные о системе, приложениях и драйверах для анализа, а затем находит проблемы совместимости, из-за которых, возможно, не удастся выполнить обновление, и предлагает решения этих проблем, известные корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a4cfa-116">Collects system, application, and driver data for analysis, and then identifies compatibility issues that can block an upgrade and suggested fixes the issues are known to Microsoft.</span></span>

- <span data-ttu-id="a4cfa-117">Поддержка обновлений</span><span class="sxs-lookup"><span data-stu-id="a4cfa-117">Update Compliance</span></span>  

  <span data-ttu-id="a4cfa-118">Здесь отображается состояние ваших устройств с учетом обновлений Windows, чтобы вы могли убедиться в том, что ваши устройства имеют наиболее актуальные необходимые обновления.</span><span class="sxs-lookup"><span data-stu-id="a4cfa-118">Shows you the state of your devices with respect to the Windows updates so that you can ensure that they are on the most current updates as appropriate.</span></span>

- <span data-ttu-id="a4cfa-119">Работоспособность устройств</span><span class="sxs-lookup"><span data-stu-id="a4cfa-119">Device Health</span></span>  

  <span data-ttu-id="a4cfa-120">Выявляет устройства, которые часто выходят из строя, и, следовательно, нуждаются в модернизации или замене, а также драйверы устройств, которые вызывают сбои устройств, предлагая альтернативные версии таких драйверов, что может способствовать снижению количества сбоев.</span><span class="sxs-lookup"><span data-stu-id="a4cfa-120">Identifies devices that crash frequently, and therefore might need to be rebuilt or replaced and device drivers that are causing device crashes, with suggestions of alternative versions of those drivers that might reduce the number of crashes.</span></span> <span data-ttu-id="a4cfa-121">Предоставляет уведомление о неправильных конфигурациях Windows Information Protection, которые отправляют запросы пользователям.</span><span class="sxs-lookup"><span data-stu-id="a4cfa-121">Provides notification of Windows Information Protection misconfigurations that send prompts to end users.</span></span>
 
<span data-ttu-id="a4cfa-p103">В компании Contoso уже имеется инфраструктура Configuration Manager (Current Branch). Configuration Manager выполняет масштабирование для крупных сред и обеспечивает всесторонний контроль над установкой, обновлениями и параметрами. Кроме того, он оснащен функциями, которые упрощают и повышают эффективность развертывания ОС Windows 10 Корпоративная и управления ею.</span><span class="sxs-lookup"><span data-stu-id="a4cfa-p103">Contoso has an existing System Center Configuration Manager (Current Branch) infrastructure. Configuration Manager scales for large environments and provides extensive control over installation, updates, and settings. It also has built-in features to make it easier and more efficient to deploy and manage Windows 10 Enterprise.</span></span>

## <a name="planning-process"></a><span data-ttu-id="a4cfa-125">Процесс планирования</span><span class="sxs-lookup"><span data-stu-id="a4cfa-125">Planning process</span></span>

<span data-ttu-id="a4cfa-126">Перед развертыванием в компании Contoso определили указанные ниже круги.</span><span class="sxs-lookup"><span data-stu-id="a4cfa-126">Prior to deployment, Contoso defined the following rings:</span></span>

- <span data-ttu-id="a4cfa-127">Три круга для поэтапного выполнения процессов проверки и развертывания.</span><span class="sxs-lookup"><span data-stu-id="a4cfa-127">Three rings for validation and deployment staging</span></span> 
  - <span data-ttu-id="a4cfa-128">Один круг для сборок ознакомительных версий.</span><span class="sxs-lookup"><span data-stu-id="a4cfa-128">One for preview builds</span></span> 
  - <span data-ttu-id="a4cfa-129">Один круг для сборок новых выпусков.</span><span class="sxs-lookup"><span data-stu-id="a4cfa-129">One for new release builds</span></span>
  - <span data-ttu-id="a4cfa-130">Один круг для предыдущих сборок.</span><span class="sxs-lookup"><span data-stu-id="a4cfa-130">One for a previous build</span></span> 
- <span data-ttu-id="a4cfa-131">Один круг для широкого развертывания Windows 10 Корпоративная на основе данных, полученных в кругах проверки.</span><span class="sxs-lookup"><span data-stu-id="a4cfa-131">One ring for broad deployment of Windows 10 Enterprise based on data from the validation rings</span></span>

<span data-ttu-id="a4cfa-132">Кроме того, с помощью решения "Проверка готовности к обновлению" в Windows Analytics специалисты компании Contoso составили перечень установленных приложений и определили совместимость этих приложений с ОС Windows 10 Корпоративная.</span><span class="sxs-lookup"><span data-stu-id="a4cfa-132">Contoso also used the Upgrade Readiness solution of Windows Analytics to determine the set of installed apps and their compatibility with Windows 10 Enterprise.</span></span>

## <a name="deployment-process"></a><span data-ttu-id="a4cfa-133">Процесс развертывания</span><span class="sxs-lookup"><span data-stu-id="a4cfa-133">Deployment process</span></span>

<span data-ttu-id="a4cfa-134">Чтобы выполнить развертывание обновлений на месте для ОС Windows 10 Корпоративная, в компании Contoso реализовали указанный ниже процесс с использованием рекомендаций корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a4cfa-134">To complete the in-place upgrade deployment of Windows 10 Enterprise, Contoso implemented the following process, which includes best practice recommendations from Microsoft:</span></span>

1. <span data-ttu-id="a4cfa-135">Был включен одноранговый кэш для Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="a4cfa-135">Enabled peer cache for Configuration Manager.</span></span>
2. <span data-ttu-id="a4cfa-136">На основе образов, полученных из Volume Licensing Service Center, были созданы специальные пакеты Windows.</span><span class="sxs-lookup"><span data-stu-id="a4cfa-136">Created customized Windows packages based on images from the Volume Licensing Service Center.</span></span>
3. <span data-ttu-id="a4cfa-137">С помощью Configuration Manager пакеты Windows были развернуты в точках распространения в сети компании. Кроме того, были развернуты сборки в трех кругах поэтапного выполнения процессов проверки и развертывания.</span><span class="sxs-lookup"><span data-stu-id="a4cfa-137">Used Configuration Manager to deploy the Windows packages to distribution points across their network and deployed builds to the three validation and deployment staging rings.</span></span>
4. <span data-ttu-id="a4cfa-138">Была выполнена оценка успешности развертывания для ПК и устройств в трех кругах поэтапного выполнения процессов проверки и развертывания с использованием решений "Работоспособность устройств" и "Поддержка обновлений" в Windows Analytics.</span><span class="sxs-lookup"><span data-stu-id="a4cfa-138">Performed assessment of success for PCs and devices in the three validation and deployment staging rings using the Device Health and Update Compliance solutions of Windows Analytics.</span></span>
5. <span data-ttu-id="a4cfa-139">На основе информации, полученной из Windows Analytics, специалисты компании Contoso выбрали версию Windows 10 Корпоративная, которую необходимо развернуть в круге широкого развертывания.</span><span class="sxs-lookup"><span data-stu-id="a4cfa-139">Based on the Windows Analytics information, Contoso determined the version of Windows 10 Enterprise to deploy to the broad deployment ring.</span></span>
6. <span data-ttu-id="a4cfa-140">Были выполнены задачи развертывания Configuration Manager для развертывания выбранного пакета Windows в круге широкого развертывания.</span><span class="sxs-lookup"><span data-stu-id="a4cfa-140">Ran the Configuration Manager deployment task sequences to deploy the selected Windows package to the broad deployment ring.</span></span>
7. <span data-ttu-id="a4cfa-141">Был выполнен мониторинг ПК и устройств в круге широкого развертывания. Для решения проблем были использованы решения "Работоспособность устройств" и "Поддержка обновлений".</span><span class="sxs-lookup"><span data-stu-id="a4cfa-141">Monitored PCs and devices in the broad deployment ring using the Device Health and Update Compliance solutions to address issues.</span></span>

<span data-ttu-id="a4cfa-142">Здесь показана архитектура развертывания обновлений на месте и текущих обновлений.</span><span class="sxs-lookup"><span data-stu-id="a4cfa-142">Here is Contoso’s in-place upgrade and ongoing updates deployment architecture.</span></span>

![Инфраструктура развертывания ОС Windows 10 Корпоративная в компании Contoso](./media/contoso-win10/contoso-win10-fig1.png)

<span data-ttu-id="a4cfa-144">Эта инфраструктура состоит из указанных ниже элементов.</span><span class="sxs-lookup"><span data-stu-id="a4cfa-144">This infrastructure consists of:</span></span>

- <span data-ttu-id="a4cfa-145">Configuration Manager, который:</span><span class="sxs-lookup"><span data-stu-id="a4cfa-145">System Center Configuration Manager, which:</span></span>
  - <span data-ttu-id="a4cfa-146">Получает образы для пакетов Windows 10 Корпоративная из Microsoft Volume Licensing Center в сети Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a4cfa-146">Obtains images for Windows 10 Enterprise packages from the Microsoft Volume Licensing Center in the Microsoft Network.</span></span>
  - <span data-ttu-id="a4cfa-147">Является центральной точкой администрирования при развертывании пакетов.</span><span class="sxs-lookup"><span data-stu-id="a4cfa-147">Is the central administration point for deployment packages.</span></span>
- <span data-ttu-id="a4cfa-148">Региональные точки распределения, которые обычно расположены в региональных офисах компании Contoso.</span><span class="sxs-lookup"><span data-stu-id="a4cfa-148">Regional distribution points that are typically located in Contoso’s regional hub offices.</span></span>
- <span data-ttu-id="a4cfa-149">Компьютеры и устройства с ОС Windows в различных расположениях, на которых выполняется прием и установка пакетов развертывания для обновления на месте или текущих обновлений на основе членства в круге.</span><span class="sxs-lookup"><span data-stu-id="a4cfa-149">Windows PCs and devices in various locations that receive and install the deployment packages for the in-place upgrade or ongoing updates based on ring membership.</span></span>

## <a name="next-step"></a><span data-ttu-id="a4cfa-150">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="a4cfa-150">Next step</span></span>

<span data-ttu-id="a4cfa-151">[Узнайте,](contoso-o365pp.md) как в компании Contoso используют свою инфраструктуру Configuration Manager для развертывания Office 365 профессиональный плюс в организации и поддержания его в актуальном состоянии.</span><span class="sxs-lookup"><span data-stu-id="a4cfa-151">[Learn](contoso-o365pp.md) how Contoso is leveraging its System Center Configuration Manager infrastructure to deploy and keep current Office 365 ProPlus across its organization.</span></span> 

## <a name="see-also"></a><span data-ttu-id="a4cfa-152">См. также</span><span class="sxs-lookup"><span data-stu-id="a4cfa-152">See also</span></span>

[<span data-ttu-id="a4cfa-153">Windows 10 Корпоративная для Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="a4cfa-153">Windows 10 Enterprise for Microsoft 365 Enterprise</span></span>](windows10-infrastructure.md)

[<span data-ttu-id="a4cfa-154">Руководство по развертыванию</span><span class="sxs-lookup"><span data-stu-id="a4cfa-154">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="a4cfa-155">Руководства по лаборатории тестирования</span><span class="sxs-lookup"><span data-stu-id="a4cfa-155">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
